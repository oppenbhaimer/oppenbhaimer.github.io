---
title: "Rust Notes I"
date: 2023-11-30T11:56:17+05:30
categories:
- Programming
tags:
- Rust
slug: "rust-notes-1"
---

Picking up rust, coming from C++ is similar in some ways, and very jarring 
in some. The code is not very different from most bracketed languages, and the 
Hindley-Milner type system makes life very easy. There are a few hiccups, 
though.

## Mutability

Rust is super anal on mutability. I'm told it's for good reason and that it 
reduces bugs. Any reference that changes state has to be marked mut. This 
also extends to impure functions: the parameters of these functions will need 
to be marked mut. Consider this:

```rust
struct Foo {
    a : i32
}

impl Foo {

    fn impure(&mut self) {
        a += 1;
        println!("Look at me, I'm changing state!");
    }

    fn pure(&self) {
        println!("I can't change state :(");
    }
}
```

Changing the state in pure would throw an error, and calling impure on any 
reference not marked with mut would also throw an error.

## Borrow Checker

The borrow checker enforces how many mutable and immutable references you have 
in the same scope. Notably,

1. You can only have one mutable reference per object in the same scope
2. You can have multiple immutable references per object in the same scope
3. You can't have both mutable and immutable references for a given object in 
   the same scope

This looks great and makes sense, but suddenly you can't do trivial stuff. 
Let's say you have a vector of vectors and want to move around some values

```rust
let mut a = vec![
    vec![1, 2, 3],
    vec![4, 5, 6],
    vec![7, 8, 9]
];

a[0].push(a[1].pop().unwrap());
```

This won't work, because a can't be borrowed as mutable multiple times. Both 
push and pop are mutable methods, and even though they work on a's children,
the borrow checker interprets that as modifying a twice. 

Even if you want to append a value without modifying, you can't. Replace the 
last line with 

```rust
a[0].push(a[1][1]);
```

And you now get the last error. a[1][1] is an immutable borrow, and you can't 
have a mutable and immutable borrow in the same scope, even though one is 
evaluated before the other.

This style of programming reminds me of _AI safety_, where the safest option to 
a possibly unsafe request is to do nothing. Sure, the safest gun is a gun that 
refuses to shoot, but that defeats the purpose of having a gun. If C allows 
you to shoot yourself in the foot, C++ makes it harder but takes your foot off,
rust simply disallows you from aiming the gun at your foot.

## Types

Rust is also super anal about types. One of the many side effects of having 
such great type checking. A simple thing to encounter is that you cannot use an
integer to index a vector. You need an element of type usize. 

Next, everything in this language is an Option or Result. And I mean 
Everything. One can't parse an integer in peace without having to unwrap it and 
have an ugly chain of commands come after it. This is an inconvenience for
CP-types like me, but I'm sure it'll be much better when your real-world
projects actually encounter malformed data (my python scripts do this daily,
and roll over like ten pins when they do).

Also, I have yet to come across a language that doesn't have regex as standard. 
Even C allows for formatted scanning using sscanf. Rust requires you to use 
cargo and install the regex crate.

## Other teething problems

- rust-analyzer won't work without a Cargo.toml file. Annoying for multiple 
  reasons. I just want to have a bunch of files I compile using a bash script, 
  but now I'm forced to fit them into Cargo's absurd directory structure.
- Syntax reference. Right now I'm having to ChatGPT everything. Maybe I should 
  use the compiler more, and rustc --explain some stuff.

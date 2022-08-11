---
title: "Type handling"
linkTitle: "Type handling"
date: 2017-01-05
weight: 3
description: >
 Every value in Rust is of a certain data type, which tells Rust what kind of data is being specified so it knows how to work with that data. 
---


### Define a constant 

```Rust

fn main() {
   // Task define a constant
    const USER_LIMIT:i32 = 100;
    const USER_MIN:i32 = 10;
    println!("User limit: {}", USER_LIMIT );
    println!("User min: {}", USER_MIN );
}
```
### Define a variable 

Syntax
The data type is optional while declaring a variable in Rust. The data type is inferred from the value assigned to the variable.

The syntax for declaring a variable is given below.

```
let variable_name = value; // no type specified
let variable_name:dataType = value; //type specified
```

### Define a integer 32

```Rust

// function to determine variable type
fn type_of<T>(_: T) -> &'static str {
    type_name::<T>()
}

fn main() {
    //  Define a integer 32
    let x:i32 = 21;
    println!("type of x {}", type_of(&x));
    println!("variable x {}", x);
}
```

### Define a integer 64

```Rust

fn main() {
    // Task define integer 64
    let x64:i64 = 64;
    println!("type of x64 {}", type_of(&x64));
    println!("variable x64 {}", x);
}
```

### Define unsigned integer types 

```Rust

fn main() {
    // Task define integer 64
    // Task define a unsigned integer
    let xu8:u8 = 8;
    let xu16:u16 = 16;
    let xu32:u32 = 32;
    let xu64:u64 = 64;
    let xu128:u128 = 132;
}
```

### Define floating-point types 

```Rust

fn main() {
    // Task define a unsigned integer
    let xf32:f32 = 32.0;
    let xf64:f64 = 64.0;
    println!("type of xf32 {}", type_of(&xf32));
    println!("variable xf32 {}", xf32);
    println!("type of xf64 {}", type_of(&xf64));
    println!("variable xf64 {}", xf64);
}
```

The String data type in Rust can be classified into the following 

* String Literal(&str)
* String Object(String)

#### String Literal
String literals (&str) are used when the value of a string is known at compile time.

String literals are static by default. This means that string literals are guaranteed to be valid for the duration of the entire program.

```Rust

fn main() {
    // Task define a string
    // string literal
    let company:&str="My company";
    let location:&str = "Australia";
    println!("company is : {} location :{}",company,location);
}
```

#### String Object
The String object type is provided in Standard Library. Unlike string literal, the string object type is not a part of the core language. It is defined as public structure in standard library pub struct String. String is a growable collection. It is mutable and UTF-8 encoded type. The String object type can be used to represent string values that are provided at runtime. String object is allocated in the heap.

Syntax
To create a String object, we can use any of the following syntax −

```
  String::new()
```
The above syntax creates an empty string

```
String::from()
```
This creates a string with some default value passed as parameter to the from() method.

```Rust

fn main() {
    // String object
    let empty_string = String::new();
    let content_string = String::from("Rust is beatiful");
    println!("empty_string the length is {}",empty_string.len());
    println!("content_string the length is {}",content_string.len());
}
```

#### Char type
The char type represents a single character. More specifically, since ‘character’ isn’t a well-defined concept in Unicode, char is a ‘Unicode scalar value’.

```Rust

fn main() {
    // task char type
    let letter:char = 'a';
    println!("type of letter {}", type_of(&letter));
    println!("variable letter {}", letter);
}
```

### Concatenation

```Rust

fn main() {
   let mut greeting = "Hi ".to_string();
    greeting.push_str("Rust");
    println!("greeting = {}",greeting);
}
```
### Boolean

```Rust

fn main() {
   let isValid:bool = true;
   println!("type of isValid {}", type_of(&isValid));
   println!("variable isValid {}", isValid);
}
```
### Enumerated type
n Rust programming, when we have to select a value from a list of possible variants we use enumeration data types. An enumerated type is declared using the enum keyword

```Rust

fn main() {

  #[derive(Debug)]
  enum GenderCategory {
      Male,Female
  }

  let male = GenderCategory::Male;
  let female = GenderCategory::Female;
}
```
### Pointer

Working with raw pointers in Rust is uncommon, typically limited to a few patterns. Raw pointers can be unaligned or null. However, when a raw pointer is dereferenced (using the * operator), it must be non-null and aligned.

```Rust

fn main() {

  let x = 5;
  let raw = &x as *const i32;
  let points_at = unsafe { *raw };
  println!("raw points at {}", points_at);
}
```
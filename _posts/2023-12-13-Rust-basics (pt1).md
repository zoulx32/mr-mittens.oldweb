# Rust Basics Cheat Sheet 📦

## Variables and Types

Variables hold information. They can be changed (mutable) or stay the same (immutable).

```rust
// This is a variable that can change.
let mut apples = 5;

// This one cannot change its value.
let oranges = 10;
```



## Constants

Constants are values that cannot change throughout the program.

```rust
const PI: f64 = 3.14159; // Declaring a constant PI with a value.

fn main() {
    println!("The value of PI is: {}", PI);
}
```

- Constants are declared using the `const` keyword.
- Their names are written in all capital letters by convention.
- Constants must have explicit type annotations.
- They can be accessed anywhere in the program.

---
---
## Things to familiarize.

- ### Comments

Comments are like little notes to yourself or others reading your code.

```rust
// This is a comment! It won't affect the code.
// It's just here to explain things.
```
- ### Scope

In Rust, a scope defines the visibility and lifetime of variables and other items.

```rust
fn main() {
    let a = 10; // Variable 'a' is valid within the 'main' function scope.

    {
        let b = 20; // Variable 'b' is valid within this inner scope.
        println!("Inside inner scope: {}", b);
    }

    println!("Outside inner scope: {}", a);
    
    // println!("Outside inner scope: {}", b); // Uncommenting will result in an error.
}
```

- **Scope**: Defines where a variable or item is accessible and valid.
- **Inner Scopes**: Variables declared in inner scopes are only accessible within that scope.
- **Lifetime**: Variables are only valid within their defined scope.

- ### `::` Operator

The `::` operator is used to access items within a scope, such as modules, functions, or constants.

```rust
mod my_module {
    pub const MY_CONSTANT: i32 = 42;
    
    pub fn my_function() {
        println!("Hello from my function!");
    }
}

fn main() {
    println!("The constant is: {}", my_module::MY_CONSTANT); // Accessing constant
    my_module::my_function(); // Accessing function
}
```

- **`::` Operator**: Used to access items within a specific scope (like modules or functions).
- **Namespace Access**: Helps access items like functions, constants, or modules.

- ### Shadowing

Shadowing allows reusing the same variable name while changing its value or type.

```rust
fn main() {
    let speed = 50; // Declaring a variable.

    let speed = speed + 10; // Shadowing the variable with a new value.

    let speed = "fast"; // Shadowing again with a different type.

    println!("The speed is: {}", speed);
}
```

- Shadowing creates a new variable with the same name as an existing one.
- It can change the value or type of the variable.
- The new variable exists only within its scope (block or function).



- ### Benefits of Shadowing

1. **Clarity**: Helps make code clearer by reusing names for different purposes.
2. **Fine-tuning**: Allows adjustments or transformations without creating new variables.
3. **Type Changes**: Enables changing a variable's type, which is not possible with mutability.

Remember, constants are fixed values throughout the program, while shadowing allows reusing a variable name for different purposes within a limited scope. Both concepts are powerful tools in Rust for managing and manipulating data. 


- ### What is the Prelude?

The Rust Prelude is a collection of types, traits, and functions that Rust automatically imports into every Rust program.

### Common Items in the Prelude

### Core Types

```rust
// Common types available in the prelude.
let number: i32 = 42;
let text: &str = "Hello, Rust!";
let boolean: bool = true;
```

- Basic types like integers (`i32`, `i64`), strings (`&str`), and booleans (`bool`) are included.

### Functions

```rust
// Common functions available in the prelude.
fn main() {
    println!("Hello, Rust!"); // Prints text to the console.
    let number = 42;
    println!("The answer is: {}", number); // Prints formatted text.
}
```

- Functions like `println!` for printing and formatting text are automatically available.

### Common Traits

```rust
// Common traits available in the prelude.
fn example<T: ToString>(value: T) {
    println!("Converted: {}", value.to_string()); // Uses trait ToString.
}
```

- Traits like `ToString` for converting types to strings are part of the prelude.

### Macros

```rust
// Common macros available in the prelude.
fn main() {
    let my_vec = vec![1, 2, 3]; // Creates a vector with elements.
    assert_eq!(my_vec.len(), 3); // Assertion macro for testing.
}
```

- Macros like `vec!` for creating vectors and `assert_eq!` for assertions are included.

### Importance of the Prelude

- **Convenience**: It saves time by importing commonly used items automatically.
- **Consistency**: Provides a consistent environment for Rust programs.
- **Ease of Use**: Enables writing concise and readable code by having essential items readily available.

Remember, the Rust Prelude is imported by default into every Rust program, making these types, traits, functions, and macros immediately accessible without explicit imports. 

---
---

## Basic Data Types

Rust has different types of information it can handle, like numbers and words.

```rust
// Numbers
let number = 42;  // This is a whole number.
let pi = 3.14;    // This is a number with a decimal.

// Words and Characters
let hello = "Hello, Rust!"; // This is a bunch of letters.
let letter = 'A';           // This is just one letter.
```

## Functions

Functions are like magic spells. You tell them what to do, and they do it!

```rust
// This is a magic spell called "add".
fn add(a: i32, b: i32) -> i32 {
    return a + b; // It adds two numbers and gives the answer back.
}
```

## Conditions and Loops

Rust can make decisions and do things many times!

```rust
// If statement: making a choice
if apples > oranges {
    println!("We have more apples!");
} else {
    println!("We have more oranges!");
}

// Loop: doing something many times
let mut counter = 0;
loop {
    println!("I'm doing something!");
    counter += 1;
    if counter == 5 {
        break; // Stop the loop after 5 times.
    }
}
```



## Ownership and Borrowing

In Rust, each piece of information has an owner. Sometimes we let others borrow it.

```rust
// Ownership: This variable owns the information.
let name = String::from("Rusty");

// Borrowing: We can borrow the information.
let borrowed_name = &name;
```

Remember, learning Rust is like learning a new game. Practice, ask questions, and have fun exploring! 
```

This cheat sheet covers the basics of Rust maybe it will be updated later on made for refreshing btw!
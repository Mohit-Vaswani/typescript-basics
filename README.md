# Typescript basics
A Guide for Beginners Learning Typescript

# Variables, Data Types, and Type Annotations:

    // Variable declaration with type annotation
    let message: string = "Hello, TypeScript!";

    // Data types
    let count: number = 10;
    let isDone: boolean = false;
    let names: string[] = ["John", "Doe"];
    let person: { name: string; age: number } = { name: "Alice", age: 25 };

    // Type inference - TypeScript can infer types in some cases
    let inferredString = "This is a string"; // TypeScript infers type as string

    // TypeScript also supports the 'any' type
    let anyVariable: any = "This can be any type";

# Functions and Arrow Functions:

    // Function with type annotations
    function addNumbers(x: number, y: number): number {
        return x + y;
    }

    // Arrow function
    const multiplyNumbers = (x: number, y: number): number => x * y;

    // Optional and default parameters
    function greet(name: string, greeting: string = "Hello"): string {
        return `${greeting}, ${name}!`;
    }

    // Function with rest parameter
    function concatenateStrings(...args: string[]): string {
        return args.join(" ");
    }

    // Function invocation
    let result1 = addNumbers(5, 3);
    let result2 = multiplyNumbers(4, 6);
    let greetingMessage = greet("Alice");
    let concatenatedString = concatenateStrings("Hello", "World", "!");

# Interfaces and Type Aliases:

  Interfaces:
  An interface is like a rulebook that tells us what properties something should have. Imagine you have a friend named "Person," and you made a list saying, "A person must have a first name, last 
  name, and age." Now, anyone claiming to be a person needs to follow that rulebook.

    // Interface definition
    interface Person {
        firstName: string;
        lastName: string;
        age: number;
    }
    
    // Object adhering to the interface
    let user: Person = {
        firstName: "John",
        lastName: "Doe",
        age: 30,
    };
    
    // Interface with optional properties
    interface Car {
        brand: string;
        model: string;
        year?: number; // Optional property
    }

    // Using the interface
    let car: Car = { brand: "Toyota", model: "Camry" };

  Type Aliases:
  A type alias is like giving a nickname to a friend. Instead of saying their full name every time, you give them a shortcut name. Similarly, a type alias gives a shortcut name to a particular 
  shape or structure of something.

    // Type alias
    type Point = { x: number; y: number };
    
    // Function using type alias
    function calculateDistance(point1: Point, point2: Point): number {
        return Math.sqrt(Math.pow(point2.x - point1.x, 2) + Math.pow(point2.y - point1.y, 2));
    }
    
    // Using the type alias
    let distance = calculateDistance({ x: 0, y: 0 }, { x: 3, y: 4 });


# Union and Intersection Types

- Union Types: A union type allows a variable to have multiple types. It's like saying the value could be one thing or another.

- Intersection Types: An intersection type combines multiple types into one. It's like saying the value should have properties of all the combined types.

        // Union Type
        let username: string | number;
        username = "Alice"; // Valid
        username = 123;      // Valid
        // username = true;   // Invalid, as it's not a string or a number
        
        // Intersection Type
        type Car = {
            brand: string;
            model: string;
        };
        
        type ElectricCar = {
            batteryLife: number;
        };
        
        type ElectricCarWithBrand = Car & ElectricCar;
        
        let myCar: ElectricCarWithBrand = {
            brand: "Tesla",
            model: "Model 3",
            batteryLife: 300,
        };

When to Use:

- Union Types: When a variable can have more than one type, and you want to express that flexibility.

- Intersection Types: When you want an object to have properties from multiple types, creating a new type with the combined properties.

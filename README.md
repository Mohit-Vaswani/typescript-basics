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

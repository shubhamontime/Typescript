# TypeScript

## What is TypeScript?

**TypeScript = JavaScript + Type System**

TypeScript is a programming language built on top of JavaScript. It adds a type system to JavaScript, which helps developers detect many errors while writing code.

TypeScript:

```ts
let age: number = 20;
age = "hello"; // Error
```
**agar nahi bataga too any type mein chal jaye ga.**

## Installing TypeScript

To install TypeScript globally on your system, use:

```bash
npm i -g typescript(ak bar he install hota hai computer mein)
```

## Compile a TypeScript File

To compile a TypeScript file into JavaScript, use:

```bash
tsc app.ts
```

TypeScript Compiler (`tsc`) converts it into:

```text
app.js
```
Then you can run the JavaScript file with Node.js:

```bash
node app.js
```

### Flow

```text
app.ts
   ↓
 tsc app.ts
   ↓
app.js
   ↓
node app.js
```

> **`tsc` = TypeScript Compiler**
> It checks and compiles TypeScript code into JavaScript.


## TypeScript File Scope

Suppose the same folder contains:

```text
project/
├── app.ts
└── app.js
```

And both files contain a variable with the same name:
--jab ak he folder mein ts file or js file hota hai or variable same hota hai too error show kar sakta hai two method hai error ko remove karna ka-- 


There are two common ways to solve this.

## Method 1: Add `export {}`

Add this at the end of the `.ts` file:

```ts
let name = "Shubham";

export {};
```

## Method 2: Use `tsconfig.json`

Create a `tsconfig.json` file:

## `tsc app.ts --noEmit`

Agar hume TypeScript code ko **check** karna hai, lekin JavaScript file generate nahi karni, to use:

```bash
tsc app.ts --noEmit
```
## `tsc --watch`

Agar hum chahte hain ki TypeScript **automatically changes ko detect kare aur dobara compile kare**, to `--watch` use karte hain:

```bash
tsc --watch
```

Short form:

```bash
tsc -w
```

## `tsconfig.json`

`tsconfig.json` is the **configuration file for a TypeScript project**.

It tells the TypeScript Compiler (`tsc`) **how to compile and check your TypeScript code**.

### Create `tsconfig.json`

You can create it using:

```bash
tsc --init
```

This creates:

```text
tsconfig.json
```

### Why do we need it?

Without `tsconfig.json`, we may have to give options every time:


TypeScript reads the settings from `tsconfig.json` and compiles the project accordingly.

### Example

A simple `tsconfig.json`:

```json
{
  "compilerOptions": {
    "target": "ES2020",
    "module": "commonjs",
    "strict": true,
    "outDir": "./dist"
    "noImplicitAny": true
  }
}
```

### Common Options

* `target` → Which JavaScript version should be generated
* `module` → Which module system to use
* `strict` → Enables strict type checking
* `outDir` → Where generated JavaScript files should be placed
* `rootDir` → Where TypeScript source files are located
* `moduleDetection` → Controls how TypeScript determines whether a file is a script or module
* noImplicitAny: true -- Agar TypeScript kisi variable/parameter ka type khud determine nahi kar pa raha aur any ban raha hai, to error do.


## `sourceMap: true`

* sourceMap: true TypeScript ka ek debugging option hai.
* Source map browser ko batata hai ki generated JavaScript ka kaunsa part original TypeScript ke kis part se aaya hai.
Add it inside `compilerOptions` in `tsconfig.json`:

```json
{
  "compilerOptions": {
    "sourceMap": true
  }
}



---

# CVMpp

Hey there! Welcome to **CVMpp**, a lightweight, custom scripting language built from scratch in C++.

If you've ever read *Crafting Interpreters*, this architecture will feel right at home. It follows the classic compiler pipeline to take raw text and turn it into running code:

1. **The Scanner:** Chops up your raw source code into clean, manageable tokens.
2. **The Parser:** Organizes those tokens into an Abstract Syntax Tree (AST) using recursive descent.
3. **The Compiler:** Translates that AST into a stream of custom bytecode instructions.
4. **The VM:** A stack-based Virtual Machine (powered by `std::vector<std::any>`) that steps through the bytecode and executes it.

## What can it do?

Don't let its size fool you—CVMpp comes packed with all the essentials you need for a functional scripting language:

* **Data Types:** Full support for numbers, booleans, and strings.
* **Math & Logic:** Standard arithmetic (`+`, `-`, `*`, `/`) and comparison operators (`==`, `!=`, `<`, `<=`, `>`, `>=`).
* **Variables:** Declare variables using `let`, read their values, and reassign them later.
* **I/O:** Built-in `print` and `input` statements to talk to the console.
* **Control Flow:** Scope your code with blocks `{ ... }`, make decisions with `if/else`, and run loops with `while`.
* **Dev Tools:** Includes a built-in CLI REPL, a file runner, and handy debug modes to dump the AST and bytecode so you can see exactly what's happening under the hood.

---

## Getting Started

### How to Build

You've got two easy ways to compile the project, depending on your preference.

**Option 1: Quick and dirty with g++**

```bash
g++ -std=c++17 -I include src/main.cpp src/token.cpp src/scanner.cpp src/parser.cpp src/compiler.cpp src/vm.cpp -o cvm

```

**Option 2: The clean way with CMake**

```bash
cmake -S . -B build
cmake --build build

```

---

### Running the Language

Once built, you can jump straight into an interactive sandbox (REPL) by running:

```bash
./cvm

```

Or, you can pass a source file directly to the executable to run a script:

**On Linux/macOS:**

```bash
./cvm SampleTest/whileLoop.cvm

```

**On Windows (PowerShell):**

```powershell
.\cvm.exe SampleTest/whileLoop.cvm

```

---

## See It in Action

Want to see what the syntax looks like? Here is a simple loop counting to three:

```c
let i = 0;

while (i < 3) {
    print i;
    i = i + 1;
}

```

**Expected Output:**

```text
0
1
2

```
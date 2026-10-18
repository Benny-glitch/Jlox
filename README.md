# jlox

![Java](https://img.shields.io/badge/Java-21%2B-orange?logo=openjdk&logoColor=white)
![Build](https://img.shields.io/badge/build-Maven-blue?logo=apachemaven)
![Status](https://img.shields.io/badge/status-work%20in%20progress-yellow)
![License](https://img.shields.io/badge/license-MIT-green)

A tree-walk interpreter for the **Lox** programming language, written in Java
while working through [*Crafting Interpreters*](https://craftinginterpreters.com/)
by Robert Nystrom.

This is a learning project. I'm building the interpreter one chapter at a time
to understand what really happens between source code and a running program:
how text becomes tokens, tokens become a syntax tree, and a syntax tree becomes
behavior.

---

## What is Lox?

Lox is a small, dynamically typed scripting language designed for the book.
It has a C-like syntax, first-class functions, closures and classes with
single inheritance:

```lox
class Greeter {
  init(name) {
    this.name = name;
  }

  greet() {
    print "Hello, " + this.name + "!";
  }
}

fun makeCounter() {
  var count = 0;
  fun increment() {
    count = count + 1;
    return count;
  }
  return increment;
}

Greeter("Lox").greet();   // Hello, Lox!

var counter = makeCounter();
counter();                // 1
counter();                // 2
```

> Not all of this runs yet: see the roadmap below for what is implemented.

---

## Roadmap

| Chapter | Topic                  | Status |
|:-------:|------------------------|:------:|
| 4       | Scanning               | 🚧     |
| 5       | Representing Code      | ⬜     |
| 6       | Parsing Expressions    | ⬜     |
| 7       | Evaluating Expressions | ⬜     |
| 8       | Statements and State   | ⬜     |
| 9       | Control Flow           | ⬜     |
| 10      | Functions              | ⬜     |
| 11      | Resolving and Binding  | ⬜     |
| 12      | Classes                | ⬜     |
| 13      | Inheritance            | ⬜     |

✅ done · 🚧 in progress · ⬜ not started

---

## Getting started

### Requirements

- JDK 21 or newer

No Maven installation is needed: the project ships with the Maven Wrapper.

### Build

```bash
./mvnw package
```

On Windows, use `mvnw.cmd` instead of `./mvnw`.

### Run

Start the interactive prompt (REPL):

```bash
java -cp target/classes com.craftinginterpreters.lox.Lox
```

Run a script:

```bash
java -cp target/classes com.craftinginterpreters.lox.Lox path/to/script.lox
```

---

## Project structure

```
jlox/
├── pom.xml
└── src/main/java/com/craftinginterpreters/lox/
    ├── Lox.java          # entry point: REPL, file runner, error reporting
    ├── Scanner.java      # source code → tokens
    ├── Token.java        # a single lexeme with its type and position
    └── TokenType.java    # every kind of token Lox knows about
```

---

## Challenges and notes

Each chapter of the book ends with a set of challenges. I'll keep track here of
the ones I solve and of anything I do differently from the book.

- *Nothing yet. Check back soon!*

---

## Acknowledgments

This project follows [*Crafting Interpreters*](https://craftinginterpreters.com/)
by [Robert Nystrom](https://github.com/munificent). The book is free to read
online, and the reference implementation lives at
[munificent/craftinginterpreters](https://github.com/munificent/craftinginterpreters).

## License

Released under the [MIT License](LICENSE).

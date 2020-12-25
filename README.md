<!-- PROJECT SHIELDS -->
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
<br />

  <p align="center">
    <br />
    <a href="https://github.com/Gyanig/Lox/NOTES.md"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    ·
    <a href="https://github.com/Gyanig/Lox/issues">Report Bug</a>
  </p>

# LOX : Interpreter with Indian Text support

Building an Interpreter using Java to support Hindi language.
- Add support for Indian Language words as Syntax
- improve on basic Interpreter design
- maybe build a text editor to support syntax and debugging (next)
- Build from cmake also

This project started as a learning from [craftinginterpreter](http://www.craftinginterpreters.com). Later, I started implementing my own ideas about adding Indian language text support.

<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
  </ol>
</details>


## Getting Started

This is version of Lox ( will be renamed to be 'parz' ) support writing statement adn check if has proper control flow.
There is a lot of the interpreter missing like the writing the control flow, allow functions, classes and inheritance. 
- Scanning 
- Parsing 
- Static and Dynamic Typing 
- Control Flow
- Hindi Langauge support
- Function
- Classes
- Debugging
- Inheritance
- Compiling
- Hash Table
- Garbage Collection
- Superclasses
- Optimization

* [Notes and Study](NOTES.md)

### Prerequisites

To run this version, you need to build it.
To build it, download a Java Based IDE.
- IntelliJ IDEA
- Latest JDK version
- build environment for Java

If you want to know more - checkout * [NOTES.md](NOTES.md)

### Installing

```
mkdir Lox
cd Lox
git clone https://github.com/Gyanig/Lox
```
- Open IntelliJ IDE
- Open folder from your pwd
- Build
- Run
```
print "one";
print true;
print 2 + 1;
```
## Roadmap
See the *[open issues](https://github.com/Gyanig/Lox/issues) for a list of proposed features (and known issues).

### And coding style tests

Example codes to test
```
(0 / 0) == (0 / 0)
//direct statements
```
```
var a;
print a;

var a = 1;
var b = 2;
print a + b;
```

## Built With

* [IntelliJ IDEA](https://jetbrains.com/idea/download/) - The Java IDEA used
* [JDK](https://www.oracle.com/java/technologies/javase-downloads.html) - Dependency Management

## Contributing

Please read [CONTRIBUTING.md](https://github.com/Gyanig/Lox/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Authors

* **Gyanig Kumar** - *Initial work* - [Developer](https://github.com/Gyanig)
See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.
- Currently none

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

[forks-shield]: https://img.shields.io/github/forks/Gyanig/Lox.svg?style=for-the-badge
[forks-url]: https://github.com/Gyanig/Lox/forks
[stars-shield]: https://img.shields.io/github/stars/Gyanig/Lox.svg?style=for-the-badge
[stars-url]: https://github.com/Gyanig/Lox/stargazers
[issues-shield]: https://img.shields.io/github/issues/Gyanig/Lox.svg?style=for-the-badge
[issues-url]: https://github.com/Gyanig/Lox/issues


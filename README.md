# csBigInteger.cpp

## csBigInteger for C++

This project is part of the [csBigInteger](https://github.com/neoresearch/csBigInteger) macro project, a C# BigInteger implementation on C++ (portable format desired)

This project is an ongoing port of csBigInteger.js project: https://github.com/neoresearch/csBigInteger.js



### Why chosing C/C++ language for that?
Existing frameworks use high-level languages that may not be suitable for very lightweight architectures,
such as microcontrollers with very limited computing capabilities.

C/C++ is interoperable with nearly all existing languages, so the idea is to provide modules that can be
reused on other projects (on other languages too).

## Build Instructions
You will need GNU GMP library for `BigInteger.cpp` implementation of `BigInteger.h`.
On debian-based systems (or ubuntu), just type `make vendor`. 

It will also configure test library (as long as you cloned this project with `--submodules` too).
To test, just run `make test`.


#### C++ Standard
Currently, C++11 is adopted, in order to keep the best compatibility between conversors and compilers. However, it is recommended to migrate to C++17 as soon as possible, if this does not break compatibility with any existing modules and tools.

Let's please follow the [CppCoreGuidelines](https://github.com/isocpp/CppCoreGuidelines).

#### vscode IDE
If using vscode IDE, it is recommended to install the following extensions:
* C/C++ (currently 0.23.0-insiders2)
* C++ Intellisense (currently 0.2.2)
* GoogleTest Adapter (currently 1.8.3)

#### C++ Format Style
The currently adopted style for C++ is `Mozilla`, with indentation level set to 3.
Recommended configuration for vscode:
```json
{
    "[cpp]": {
        "editor.tabSize" : 3,
        "editor.detectIndentation": false
    },
    "C_Cpp.clang_format_fallbackStyle": "{ BasedOnStyle : Mozilla , ColumnLimit : 0, IndentWidth: 3, AccessModifierOffset: -3}"
}
```

#### Variable Naming Style
The naming style for variables and methods is based on `C#` language. 
So, CamelCase is used and `public` variables start with upper-case letters, while `private` and `local` variables start with lower-case.
The idea is to preseve maximum compatibility with reference project (which is on C#).

Anything that is beyond the scope of the reference project can use classic CamelCase `C++` naming (for example, starting variables with lower-case).

### License

Code follows `MIT License`, **except** by file `BigInteger.cpp` (class implementation of standard `BigInteger.h`), which is `LGPLv3`. The reason is that the current **implementation** depends on GNU MP Bignum Library (licensed LGPLv3 since version 6), what means that all modifications of `BigInteger.cpp`, or usage of its code (even partially) on other projects should also adopt `LGPLv3` (not MIT License). However, the binary generated by this project `csbiginteger.so` can be freely used on other projects, regardless of license.

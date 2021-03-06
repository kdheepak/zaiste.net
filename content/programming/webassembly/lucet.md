
+++

+++
# Lucet: Fastly's WebAssembly Compiler & Runtime

Mozilla and other web browser makers introduced WebAssembly in 2017 as a new way to create application that can run in most browsers. WebAssembly, however, can be also used to run applications outside of browsers.

WebAssembly started as a way to write softwre that runs in the browser using programming languages other than JavaScript

WebAssembly is supported by several languages including Rust, TypeScript, C and C++.

Lucet aims to take WebAssembly beyond the browser.

Lucet is designed to execute on a single HTTP request, i.e. creating a WebAssembly instance in a single process. Such constrain requires a low runtime footprint.

Lucet can instantiate WebAssembly modules in under 50 microseconds with a few kilobytes of memory overhead. By comparison, V8 engine needs around 5 milliseconds and tens of megabytes of memory to start either JavaScript or WebAssembly programs.

Lucet allows to execute tens of thousands of WebAssembly programs simultaneously in the same process without compromising security.

Lucet comes with a compiler, which compiles WebAssembly modules to native code and a runtime, which manages resources. Lucet uses AOT (ahead-of-time) compilation for transforming WebAssembly into native code.

Lucet is built on top of the Cranelift project started by Mozilla.

Lucet supports the WebAssembly System Interface (WASI), a standard for safely exposing low-level interfaces to the filesystem, networking and other system facilities to WebAssembly programs.

Lucet team works in cooperation with Mozilla.

Lucet started in 2017 and became public in march 2019.

Lucet is written in Rust.

## Lucet code example

```bash 
git clone --recurse-submodules https://github.com/fastly/lucet
```

```bash 
cd lucet
source devenv_setenv.sh
```

```c 
#include <stdio.h>
int main(int argc, char* argv[])
{
    if (argc > 1) {
            printf("Hello from Lucet, %s!\n", argv[1]);
    } else {
            puts("Hello, world!");
    }
    return 0;
}
```

```bash 
wasm32-unknown-wasi-clang hello.c -o hello.wasm
```

Compile WebAssembly to native code using the Lucet compiler:

```bash 
lucetc-wasi hello.wasm -o hello.so
```

Execute the native code using the Lucet runtime:

```bash 
lucet-wasi hello.so
```


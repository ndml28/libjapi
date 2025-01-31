# libjapi

libjapi is a universal JSON to C API library. It receives newline-delimited
JSON (NDJSON) messages via TCP and calls registered C functions. A JSON
response is returned for each request. Furthermore, it is also possible to
create push services, which asynchronously push JSON messages to the clients
subscribed to them.

## Documentation
The documentation can be found [here](https://fraunhofer-iis.github.io/libjapi/).

## Packages
Prebuild packages for CentOS 7 can be downloaded from the [latest package Action](https://github.com/Fraunhofer-IIS/libjapi/actions/workflows/package.yml).

## Features
* Synchronous communication (request, response)
* Asynchronous communication (register, push)
* Multi-client support

## Getting started

### Prerequisites
* [json-c](https://github.com/json-c/json-c)
* [cmake version 3.6](https://cmake.org/)

### Installation
Clone the git repository and it's submodules:

    $ git clone --recurse-submodules git@github.com:Fraunhofer-IIS/libjapi.git

Create a build directory and call *cmake* in that directory.

    $ mkdir build
    $ cd build/
    $ cmake ../

A Makefile is generated. Run 'make' to build the libjapi libraries.

    $ make

A shared and a static library is built.

To run the internal tests run

    $ make run_test

## Demo
You can clone the [demo project](https://git01.iis.fhg.de/ks-ip-lib/software/libjapi-demo), with examples for all features from the repository listed below:

    $ git clone --recurse-submodules git@git01.iis.fhg.de:ks-ip-lib/software/libjapi-demo.git

## References
* https://github.com/json-c/json-c
* http://json-c.github.io/json-c/
* https://en.wikipedia.org/wiki/JSON
* https://alan-mushi.github.io/2014/10/28/json-c-tutorial-part-1.html

## Contributing

### Pre-commit hooks
When contributing to this project, automatic formatting of changes is strongly encouraged, so that formatting is getting more consistent over time.

To do so, ensure you have [`pre-commit`](https://pre-commit.com/) installed and do the following

```console
$ pre-commit install
pre-commit installed at .git/hooks/pre-commit
```

This will run `clang-format` on all *changes* you commit, gradually reformatting the code base to a more consistent state.

### Code Coverage
To test which part of the code is called by tests, use the coverage tool.

To do so, make sure you have lcov installed and do the following

    $ mkdir build
    $ cd build/
    $ cmake -DCMAKE_BUILD_TYPE=Debug ../
    $ make coverage

The result ist displayed in the console. Additionally a report is created at "build/coverage/index.html".
You can also find it [here](https://fraunhofer-iis.github.io/libjapi/coverage/index.html).

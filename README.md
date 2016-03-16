expected lite - expected objects for C++11 and later&ensp;[![Build Status](https://travis-ci.org/martinmoene/expected-lite.png?branch=master)](https://travis-ci.org/martinmoene/expected-lite)
============================================

*expected lite* is a single-file header-only library for objects that either present a valid value or an error that you can pass by value. It is intended for use with C++11 and later. The library is based on the std:&#58;experimental:&#58;expected proposal [1] .

**Contents**  
- [Example usage](#example-usage)
- [In a nutshell](#in-a-nutshell)
- [License](#license)
- [Dependencies](#dependencies)
- [Installation](#installation)
- [Synopsis](#synopsis)
- [Comparison of std:&#58;experimental:&#58;expected, expected lite and ...](#comparison)
- [Reported to work with](#reported-to-work-with)
- [Implementation notes](#implementation-notes)
- [Notes and references](#notes-and-references)
- [Appendix](#appendix)


Example usage
-------------
```C++
#include "expected.hpp"
```
### Compile and run
```
...
```

In a nutshell
---------------

License
-------
*expected lite* uses the [MIT](LICENSE) license.


Dependencies
------------
*expected lite* has no other dependencies than the [C++ standard library](http://en.cppreference.com/w/cpp/header).


Installation
------------

*expected lite* is a single-file header-only library. Put `expected.hpp` directly into the project source tree or somewhere reachable from your project.


Synopsis
--------

**Contents**  
- [Configuration macros](#configuration-macros)
- [Types in namespace nonstd](#types-in-namespace-nonstd)  
- [Interface of *expected lite*](#interface-of-expected-lite)  
- [Algorithms for *expected lite*](#algorithms-for-expected-lite)  

### Configuration macros

\-D<b>nsel\_CONFIG\_CONFIRMS\_COMPILATION\_ERRORS</b>=0  
Define this macro to 1 to experience the by-design compile-time errors of the library in the test suite. Default is 0.

### Types in namespace nonstd

### Interface of *expected lite*

### Algorithms for *expected lite*


<a id="comparison"></a>
Comparison of std:&#58;experimental:&#58;expected, expected lite and ...
-------------------------------------------------------------


Reported to work with
---------------------


Implementation notes
--------------------


Notes and references
--------------------

[1] Vicente J. Botet Escriba. [Dxxxxr0 - A proposal to add a utility class to represent expected monad (Revision 2)](https://github.com/viboes/std-make/blob/master/doc/proposal/expected/DXXXXR0_expected.pdf) (PDF).

Appendix
--------
### A.1 expected lite test specification

```
unexpected_type<>: Disallows default construction
unexpected_type<>: Disallows default construction, std::exception_ptr specialization
unexpected_type<>: Allows to copy-construct from error_type
unexpected_type<>: Allows to copy-construct from error_type, std::exception_ptr specialization
unexpected_type<>: Allows to move-construct from error_type
unexpected_type<>: Allows to move-construct from error_type, std::exception_ptr specialization
unexpected_type<>: Allows to copy-construct from an exception, std::exception_ptr specialization
unexpected_type<>: Allows to observe its value
unexpected_type<>: Allows to observe its value, std::exception_ptr specialization
unexpected_type<>: Allows to modify its value
unexpected_type<>: Allows to modify its value, std::exception_ptr specialization
unexpected_type<>: Provides relational operators
unexpected_type<>: Supports relational operators, std::exception_ptr specialization
is_unexpected<X>: Is true for unexpected_type
is_unexpected<X>: Is false for non-unexpected_type (int)
make_unexpected(): Allows to create an unexpected_type<E> from an E
make_unexpected_from_current_exception(): Allows to create an unexpected_type<std::exception_ptr> from the current excep
tion
bad_expected_access<>: Disallows default construction
bad_expected_access<>: Allows construction from error_type
bad_expected_access<>: Allows to observe its error
bad_expected_access<>: Allows to change its error
expected<>: Allows default construction
expected<>: Allows to copy-construct from value_type
expected<>: Allows to move-construct from value_type
expected<>: Allows to copy-construct from expected<>
expected<>: Allows to move-construct from expected<>
expected<>: Allows to in-place-construct value_type
expected<>: Allows to copy-construct from unexpected_type<>
expected<>: Allows to move-construct from unexpected_type<>
expected<>: Allows to in-place-construct unexpected_type<>
expected<>: Allows to copy-assign from expected<>
expected<>: Allows to move-assign from expected<>
expected<>: Allows to copy-assign from unexpected_type<>
expected<>: Allows to move-assign from unexpected_type<>
expected<>: Allows to copy-assign from type convertible to value_type
expected<>: Allows to move-assign from type convertible to value_type
expected<>: Allows to emplace a value_type
expected<>: Allows to be swapped
expected<>: Allows to observe its value via a pointer
expected<>: Allows to modify its value via a pointer
expected<>: Allows to observe its value via a reference
expected<>: Allows to observe its value via a r-value reference
expected<>: Allows to modify its value via a reference
expected<>: Allows to observe if it contains a value (or error)
expected<>: Allows to observe its value
expected<>: Allows to modify its value
expected<>: Allows to move its value
expected<>: Allows to observe its error
expected<>: Allows to modify its error
expected<>: Allows to move its error
expected<>: Allows to observe its error as unexpected<>
expected<>: Allows to observe its value if avialable, or obtain a specified value otherwise
expected<>: Allows to move its value if avialable, or obtain a specified value otherwise
expected<>: Provides relational operators
...
```

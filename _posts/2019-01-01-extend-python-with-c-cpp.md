---
layout: post
title: "How to extend Python with C/C++ Code"
date: 2019-01-01
author: Matthias Bitzer
categories: [python, programming, performance]
excerpt: "Learn how to write Python extensions in C/C++ to boost performance for compute-intensive operations."
---

*Python's simplicity comes at a performance cost. Learn how to extend Python with C/C++ for critical code paths.*

## Introduction

Python is beloved for its readability and ease of use, but interpreted languages have inherent performance limitations. When you need maximum speed for compute-intensive operations, extending Python with C or C++ is a powerful solution.

## When to Use C Extensions

- **CPU-bound computations**: Mathematical operations, algorithms
- **Interfacing with C libraries**: Using existing C/C++ code
- **Performance-critical paths**: When Python becomes a bottleneck
- **Memory-intensive operations**: More control over memory management

## Method 1: Python C API

The traditional approach using Python's C API:

### Example: A simple add function

```c
#include <Python.h>

static PyObject* add(PyObject* self, PyObject* args) {
    int a, b;
    if (!PyArg_ParseTuple(args, "ii", &a, &b)) {
        return NULL;
    }
    return PyLong_FromLong(a + b);
}

static PyMethodDef methods[] = {
    {"add", add, METH_VARARGS, "Add two integers"},
    {NULL, NULL, 0, NULL}
};

static struct PyModuleDef module = {
    PyModuleDef_HEAD_INIT,
    "mymodule",
    NULL,
    -1,
    methods
};

PyMODINIT_FUNC PyInit_mymodule(void) {
    return PyModule_Create(&module);
}
```

### Build with setup.py

```python
from setuptools import setup, Extension

module = Extension('mymodule', sources=['mymodule.c'])

setup(
    name='mymodule',
    ext_modules=[module]
)
```

```bash
python setup.py build_ext --inplace
```

## Method 2: Cython

Cython provides a more Pythonic approach:

### cython_example.pyx

```cython
def add(int a, int b):
    return a + b

def fast_sum(double[:] arr):
    cdef double total = 0
    cdef int i
    for i in range(arr.shape[0]):
        total += arr[i]
    return total
```

### setup.py for Cython

```python
from setuptools import setup
from Cython.Build import cythonize

setup(
    ext_modules=cythonize("cython_example.pyx")
)
```

## Method 3: ctypes

For interfacing with existing shared libraries:

```python
import ctypes

# Load the library
lib = ctypes.CDLL('./mylib.so')

# Define argument and return types
lib.add.argtypes = [ctypes.c_int, ctypes.c_int]
lib.add.restype = ctypes.c_int

# Call the function
result = lib.add(5, 3)
```

## Method 4: pybind11

Modern C++ binding with pybind11:

```cpp
#include <pybind11/pybind11.h>

int add(int a, int b) {
    return a + b;
}

PYBIND11_MODULE(mymodule, m) {
    m.def("add", &add, "Add two integers");
}
```

## Performance Comparison

| Method | Ease of Use | Performance | Use Case |
|--------|-------------|-------------|----------|
| Python C API | Low | Highest | Full control |
| Cython | Medium | High | Numeric code |
| ctypes | High | Medium | Existing libs |
| pybind11 | High | High | C++ integration |

## Conclusion

Choose the right tool based on your needs:

- **pybind11**: Best for new C++ code
- **Cython**: Great for optimizing Python code
- **ctypes**: Quick integration with existing libraries
- **C API**: Maximum control and performance

---

*This is a placeholder article. Replace with your full content from Medium.*

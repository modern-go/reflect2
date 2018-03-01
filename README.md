# reflect2

[![Sourcegraph](https://sourcegraph.com/github.com/modern-go/reflect2/-/badge.svg)](https://sourcegraph.com/github.com/modern-go/reflect2?badge)
[![GoDoc](http://img.shields.io/badge/go-documentation-blue.svg?style=flat-square)](http://godoc.org/github.com/modern-go/reflect2)
[![Build Status](https://travis-ci.org/modern-go/reflect2.svg?branch=master)](https://travis-ci.org/modern-go/reflect2)
[![codecov](https://codecov.io/gh/modern-go/reflect2/branch/master/graph/badge.svg)](https://codecov.io/gh/modern-go/reflect2)
[![rcard](https://goreportcard.com/badge/github.com/modern-go/reflect2)](https://goreportcard.com/report/github.com/modern-go/reflect2)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://raw.githubusercontent.com/modern-go/reflect2/master/LICENSE)

reflect api that avoids runtime reflect.Value cost

* reflect get/set interface{}, with type checking
* reflect get/set unsafe.Pointer, without type checking
* `reflect2.TypeByName` works like `Class.forName` found in java

[json-iterator](https://github.com/json-iterator/go) use this package to save runtime dispatching cost.
This package is designed for low level libraries to optimize reflection performance.
General application should still use reflect standard library.

# reflect2.TypeByName

```go
// given package is github.com/your/awesome-package
type MyStruct struct {
	// ...
}

// will return the type
reflect2.TypeByName("awesome-package.MyStruct")
// however, if the type has not been used
// it will be eliminated by compiler, so we can not get it in runtime
```

# reflect2 get/set interface{}

```go
valType := reflect2.TypeOf(1)
i := 1
j := 10
valType.Set(&i, &j)
// i will be 10
```

# reflect2 get/set unsafe.Pointer

```go
valType := reflect2.TypeOf(1)
i := 1
j := 10
valType.UnsafeSet(unsfae.Pointer(&i), unsafe.Pointer(&j))
// i will be 10
```
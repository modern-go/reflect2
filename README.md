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

[json-iterator](https://github.com/json-iterator/go) use this package to save runtime dispatching cost.
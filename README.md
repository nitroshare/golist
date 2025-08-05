## golist

[![Build Status](https://github.com/nitroshare/golist/actions/workflows/test.yml/badge.svg)](https://github.com/nitroshare/golist/actions/workflows/test.yml)
[![Coverage Status](https://coveralls.io/repos/github/nitroshare/golist/badge.svg?branch=main)](https://coveralls.io/github/nitroshare/golist?branch=main)
[![Go Reference](https://pkg.go.dev/badge/github.com/nitroshare/golist.svg)](https://pkg.go.dev/github.com/nitroshare/golist)
[![MIT License](https://img.shields.io/badge/license-MIT-9370d8.svg?style=flat)](https://opensource.org/licenses/MIT)

This package provides a simple doubly-linked list with generics. The goal is to keep this package as simple as possible:

```golang
import "github.com/nitroshare/golist"

// Zero value for List is ready for use
l := &List[string]{}

// Add item (returning Element for newly inserted value)
e := l.Add("test")

// Show length of list
fmt.Printf("List length: %d\n", l.Len)

// Iterate over items
for e := l.Front; e != nil; e = e.Next {
    fmt.Println(e.Value)

    // Remove an item during iteration
    l.Remove(e)

    // e.Next will still point to what was going to be the next item
}

// Remove and return the first element (useful for a queue)
e := l.PopFront()

// Remove and return the last element (useful for a stack)
e := l.PopBack()
```

# Generic Heap Package

A flexible and customizable generic heap package for Go that empowers you to create heaps
with any type of values, providing the freedom to customize the heap structure based on
your specific requirements.


## Installation

```sh
go get github.com/Prthmesh6/heap
```

## Reference Video

Watch this [YouTube video](https://www.youtube.com/watch?v=HqPJF2L5h9U) for a detailed
understanding of heap


## Example : 
```go 
package main

import (
	"fmt"

	"github.com/Prthmesh6/heap"
)

type Rank struct {
	Name  string
	Score int
}

func main() {

	minHeapFunc := func(heap []Rank, parent, child int) bool {
		return heap[parent].Score < heap[child].Score
	}

	minHeap := heap.New[Rank](minHeapFunc)

	minHeap.Push(Rank{
		Name:  "ABC",
		Score: 30,
	})

	minHeap.Push(Rank{
		Name: "EFG",
		Score: 20,
	})

	fmt.Println(minHeap.Pop())
	fmt.Println(minHeap.Pop())
	fmt.Println(minHeap.Pop())
}
```
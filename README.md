### what I do for fun:

```
package main

import "fmt"

func main() {
	firstChan := make(chan rune)
	secondChan := make(chan rune)
	thirdChan := make(chan rune)
	go func() {
		defer close(firstChan)
		for _, f := range "ccrcieaoa t " {
			firstChan <- f
		}
	}()
	go func() {
		defer close(secondChan)
		for _, f := range "oueyngtnnda" {
			secondChan <- f
		}
	}()
	go func() {
		defer close(thirdChan)
		for _, f := range "nrn tri da" {
			thirdChan <- f
		}
	}()
	const numberOfRunes = len("ccrcieaoa toueyngtnndanrn tri da")
	for i := 0; i < numberOfRunes; i++ {
		fmt.Printf("%s", string(<-firstChan))
		fmt.Printf("%s", string(<-secondChan))
		fmt.Printf("%s", string(<-thirdChan))
	}
	fmt.Printf("%s", "\n")
}
```

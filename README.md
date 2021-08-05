### what I do for fun:

```
package main

import "fmt"

func whatIdo(s string, out chan rune) {
	defer close(out)
	for _, f := range s {
		out <- f
	}
}

func main() {
	const length = 33
	firstChan := make(chan rune)
	secondChan := make(chan rune)
	thirdChan := make(chan rune)
	go whatIdo("ccrcieaoa t ", firstChan)
	go whatIdo("oueyngtnnda", secondChan)
	go whatIdo("nrn tri da", thirdChan)
	for i := 0; i < length; i++ {
		fmt.Printf("%s", string(<-firstChan))
		fmt.Printf("%s", string(<-secondChan))
		fmt.Printf("%s", string(<-thirdChan))
	}
	fmt.Printf("%s", "\n")
}

```

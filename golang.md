##Basics

###Sample program
```go
package main

import(
	"fmt")

func main(){
	fmt.Println("Hello World")
}
```
###Imports
	import "fmt"
##### for multiple
	import(
		"fmt" "math"
		)
Note: Any exported name must begin in caps
#####Ex:
		fmt.Println("hi")

###Functions
	func add(x,y int) int {
		return x+y
	}

###Variables
	var num int
##### or
	var num int= 7
#####Short declaration
	num:= 7
It decides the type from the value

###Type conversion
	var i int = 7
	var f float32 = float32(i)

###Constants
	const num= 14


##Control flow

###For loop
	for i=0;i<5;i++{
		fmt.Println("*")
	}

### If condition
	if a%2==0{
		fmt.Println("Even")
	}

### Switch condition
	switch os{
	case "Windows":
		fmt.Println("Windows")
	case "Linux":
		fmt.Println("Linux")
	}
##### Without a conditon, Switch can be cascading if-else
	switch{
		case i%2==0: fmt.Println("Even")
		case i%2!=0: fmt.Println("Odd")
	}

###Defer statements
Defers excution of statement till surrounding functions executes

	defer fmt.Println("I am")
	fmt.Println("Shruti")

Multiple Defers are stored in a stack and follow LIFO during execution


# Pointers

指针



```go
var <pointername> *<Datatype>

var mpointers *int	//声明mpointers是个地址，指向int类型的数值
var num = 12				
mpointers = & num   //把num的地址作为value 给 mpointers
* mpointers  				//把mpointers的值作为地址取该地址的值，返回

// & 取变量储存地址	取得的是个地址
// *	取值，把当前变量名对应的值作为地址

```



Uses

- Save memory space

- Used for file handling

- Passing argument

- Used in data structures, makes it easier in handling Arrays and Structures

  







# Structures

User-defined Datatype





```go
//Syntax

package main
import "fmt"

func main(){
  
    type Employee struct {
      ID int
      Name string
      Salary float32
  
	}
  
  emp1: = {
    ID: 1,
    Name: "John"
    Salary: 100000.00
    
  }
  
  fmt.Println("Employee ID: ", emp1.ID)
  
  
  
}
```



# Strings



```go
var str = "One Percent"
str: = 1Percent

import "fmt"
import "strings"
```



Go has a lot of Inbuilt String Methods that can be used to perform String based operations



| Fuction     | Description                             | Example                     |
| ----------- | --------------------------------------- | --------------------------- |
| len()       | return the length                       |                             |
| Compare()   | return the diff                         |                             |
| Cotains()   |                                         | strings.Cotains(str, “one”) |
| Count()     | count the times a character is repeated | strings.Count(str, “e”)     |
|             |                                         |                             |
| HasPrefix() |                                         |                             |
| HasSuffix() |                                         |                             |
| Index()     | return the index in a string            | string.Index(str, “x”)      |
| Join()      |                                         |                             |
| Repeat()    |                                         |                             |
| Replace()   |                                         |                             |
| Split()     | 把长的string按照特定符号分开            | string.Split(str, “-”)      |
| ToLower()   |                                         |                             |
| ToUpper()   |                                         |                             |
|             |                                         |                             |
|             |                                         |                             |
| Trim()      | remove specfied characters              | string.Trim(str, “!”)       |
| Trimspace() | remove WhiteSpaces from string          | string.TrimSpace(str)       |
|             |                                         |                             |





# Math



```go
package main
import "fmt"
import "math"

func main(){
  
}

```



| Fuction | Example                                     |                   |
| ------- | ------------------------------------------- | ----------------- |
| abs()   | Absolute Value                              |                   |
| sqrt()  |                                             |                   |
| Pow()   | returns an e raised to the power of x (e^x) | math.Pow(10,2)    |
| Round() | returns the nearest Interger                | math.Round (75.4) |
| Sin()   |                                             |                   |
| Cos()   |                                             |                   |
| Tan()   |                                             |                   |
| Asin()  |                                             |                   |
| Acos()  |                                             |                   |
| Atan()  |                                             |                   |
| Sinh()  |                                             |                   |
| Cosh()  |                                             |                   |
| Tanh()  |                                             |                   |
| Log()   | natural logarithm of a number               |                   |
| Log10() | Decimal Logarithm                           |                   |
| Exp()   | e raised to the power of x                  |                   |
|         |                                             |                   |





# Exception handling



## Error type



| Error Type    | Cause                                     | Example                     |
| ------------- | ----------------------------------------- | --------------------------- |
| Syntax Error  | 打错啦 mistake in the syntax of the code  | fmt.Print() 打成fmt.print() |
| RunTime Error | Error during the Execution of the program | /0                          |
| Logical Error | flaw in the Logic of the program          | age > 18                    |





## recover()

```go
defer func(){
  fmt.Println("Error: ", recover())
}

```

**recover() returns <nil>  if  there is no error**







## defer Keyword



- defer keyword is used for cleaning purpose
- postpones the execution of a function til the end of program
- make sure the rest of the program runs smoothly





```go
//syntax
defer <FunctionName>{
}

//Example
package main
import "fmt"
func Function1{
  
}
func main{
  defer Function1()
  Function2()
  
}
//先执行2，再执行1

```





# Maps



- unordered collection of Key and Value
- Similiar to Array except than the Index is replaced by Key(you can set your own)

```go
// var <MapName> map [<KeyType>] <ValueType>

// Example

Capitals := map[string]string {"India": "New Delhi", "USA": "Washington"}

fmt.Println("Capital of USA: ", Capitals["USA"])
```



*Insert into Maps*

- 如果对应的Key值没有过， 直接声明就加进去了

- 因为Key是自己加的，没有顺序， 所以不能for loop展示，直接用Key引用或者maps名全部打印出来

```go
Marks["Akash"] = 90

```



*Update Maps*

- 直接重新用key值赋值



*Delete From Map*

```go
delete(Capitals, "China")
```

- 调用delete函数删除， 删除key值



# Date time

| Time Class Fuc |              |      |
| -------------- | ------------ | ---- |
| time.Now()     | current time |      |
| time.Tick      |              |      |
|                |              |      |









```go
import "time"

time.Now().Year()
time.Now().Month()
time.Now().Day()
time.Now().Hour()
time.Now().Minute()
time.Now().Second()
time.Now().Weekday()
time.Now().Location()



```





# Concurrency



- run more tasks simultaneously
- Known as Concurrency
- Concurrency can be achieved in Go uring Goroutines and Channels



## Goroutine



*Goroutine is a function capable of running simultaneously with other functions*

```go
package main

import "fmt"
import "time"
import "math/rand"

func print(n int) {

 // Looping thorugh every call 3 times
 for i := 0; i < 3; i++ {

  // Prints N and I Value
  fmt.Println(n, ":", i)

  // Random number is Generated
  randomNum := time.Duration(rand.Intn(250))

  // The random number is the number of Milliseconds the Loop would sleep
  time.Sleep(time.Millisecond * randomNum)
 }

  

  
  
}

func main() {
 // Calling Goroutine 3 times
 for i := 0; i < 3; i++ {

  // A normal Function would NOT execute simultaneously. Try calling the function without "go"
  go print(i)
 }

 // Used to Exit the Loop
 var input string
 fmt.Scanln(&input)
}
```







```go
package main

import "fmt"
import "time"

func hello(data string, channelCall chan string) {
 fmt.Println("Channel Called")

 // 4. Changing Data
 data = data + " Club"
 fmt.Println("Data Changed")

 // 5. Sleeping for 2 Seconds
 fmt.Println("Channel Sleeping for 2 Seconds")
 time.Sleep(2 * time.Second)
 fmt.Println("Channel Awake")

 // 6. Sending Data
 channelCall <- data
 fmt.Println("Channel Message Sent : ", data)

}

func main() {
 // 1. Defined Data
 data := "OnePercent"

 // 2. Defined Channel
 channelCall := make(chan string)
 fmt.Println("Main Method : Before Calling Channel")

 // 3. Calling CHannel
 go hello(data, channelCall)

 // 7. Rceived Data
 ReceivedData := <-channelCall

 // 8. Printed Data
 fmt.Println("Received Message : ", ReceivedData)
}
```
















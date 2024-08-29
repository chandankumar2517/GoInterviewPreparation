# GoInterviewPreparation
This series is designed to help you prepare for your Golang interview.



Golang Interview Preparation

1)	Introduce yourself. 


2)	Choosing between Java and Golang for backend development.

Here's a comparison to help you decide:

 Java

Mature Ecosystem: Java has been around since 1995, offering a vast ecosystem with extensive libraries and frameworks¹.

Object-Oriented: Java is object-oriented, which can be beneficial for large-scale enterprise applications².

Performance: While Java is robust, it can be more memory-intensive compared to Golang³.

Community Support: Java has a large, mature community, making it easier to find resources and support¹.

Golang (Go)

Simplicity: Golang is known for its simplicity and ease of use, making it a good choice for developers who prefer a straightforward syntax¹.

Concurrency: Golang excels in handling concurrent tasks, which is ideal for high-performance applications².

Performance: Go is lightweight and performs well, especially in microservices architectures³.

Growing Community: Although newer, Golang's community is rapidly growing, providing increasing support and resources¹.

When to Choose Java
•	Large-scale enterprise applications
•	Projects requiring extensive libraries and frameworks.
•	Applications where object-oriented programming is beneficial.

When to Choose Golang
•	High-performance, concurrent applications
•	Microservices architectures
•	Projects where simplicity and speed are priorities.

Ultimately, the best choice depends on your project's specific needs and your team's expertise. Do you have a particular project in mind that you're considering these technologies for?

3)	Encapsulation: Achieved using structs and methods.
Composition: Achieved by embedding structs within other structs.
Polymorphism: Achieved using interfaces, allowing different types to be treated uniformly based on the methods they implement.

4)	What is Golang?
Golang is a statically typed, compiled programming language designed at Google by Robert Gries Emer, Rob Pike, and Ken Thompson. Golang was designed at Google in 2007 to improve programming productivity in an era of multicore, networked machines, and large codebases.

5)	What are Pros & Cons of Golang?
a.	Pros:

i.	Ease of use
ii.	A Smart Standard library
iii.	Strong security built-in
iv.	Garbage collected language.
v.	Minimalism & Readability
vi.	Concurrency
vii.	Fast compilation
viii.	Efficient memory management

b.	Cons:

i.	No generics
ii.	Error-handling boilerplate & lack of compile-time checks unhandled errors.
iii.	Shortage of high-level parallelism and concurrency features

6)	What kind of Project are suitable to be built in Golang?
a.	Cloud Services
b.	Media Platforms
c.	Broadcast Receivers
d.	Projects with microservices architectures

7)	How Golang is know as security built in?
a.	Memory Safety
i.	Go include garbage collection and strongly typed pointers which helps to prevent memory-related vulnerability like buffer overflow.

b.	Concurrency Safety
i.	Go concurrency safety based on goroutine and channels, helps to avoid race conditions.
c.	Cryptography 
i.	Go provides robust library like secure hashing, encryption & decryption.
d.	Vulnerability Scan 
i.	Tools like gvulnscan can scan code to know any vulnerable and it seamlessly can be integrated with CI/CD.
e.	Secure Coding Practice
i.	It encourages the use of secure coding practices, such as using html/template to prevent XSS attacks.

8)	How to handle circular dependencies between packages?
a.	Refactor Code
b.	Dependency Injection
9)	What are tools or linters to detects circular dependencies?
a.	Madge
b.	dpdm

10)	Is Golang an object-oriented language?
Golang has type and method and allows object-oriented style of programming, there is no type of hierarchy. Golang has some properties of object-oriented programming like Encapsulation, Composition, but it does not have inheritance, class, and function overloading.

11)	Encapsulation in Golang?
a.	You can encapsulate to restrict struct to be export or to be used within same package.
b.	If struct name starts with lowercase 
i.	Ex: type account structs {} as here account starts with lower letter this mean this struct can only be accessed within package so it helps that this struct variable cannot be accessed outside and avoid un-necessary modification.
12)	Composition in Golang?
a.	It helps of code modularity. 
b.	Code reusability
c.	Flexibility
i.	Ex:  
















In above example of composition, you can see how Details struct has been used within Game struct and then in main function it is used to show all details value.
13)	What is the data type in Golang?

a.	Basic – Integer, Strings and Booleans
b.	Aggregator – Arrays & structs.
c.	Referential – maps, slices, Pointer, functions, and channels.
d.	Interface type

14)	Can you return multiple values from a function?
a.	Yes, A Go functions can return multiple values, each separated by commas in the return statements.





	
15)	What is goroutine?
Goroutine is incredible lightweight “threads” managed by the go runtime. They enable us to create asynchronous parallel program that can execute some tasks far quicker than if they were written in a sequential manner. It is designed to handle concurrent task efficiently.

a.	Key feature 
i.	Lightweight: Goroutine is much lighter than traditional threads. They start with a small stack, which grows and shrinks as needed, making them very memory efficient.
ii.	Concurrency: Goroutines allow you to run functions concurrently with other functions. This mean multiple goroutines can executes simultaneously, making it easier to write concurrent program.
iii.	Easy to use you can create a goroutine by simply prefixing a function call with the go keyword. For ex:  go someMethodName()
iv.	Managed by Runtime: The go runtime handles the scheduling of goroutines, distributing them across available CPU cores. This helps achieving efficient parallel executions.

b.	Benefit: 
i.	Scalability: goroutine can scale to handle thousands or even millions of concurrent task.
ii.	Simplicity: Writing concurrent code with goroutines is straightforward and avoids the complexity of traditional thread management.

16)	How does go manage synchronization between goroutines?
a.	WaitGroup
i.	The sync.WaitGroup type is used to wait for a collection of goroutine to finish executing. It provides three main methods:
1.	Add (delta int) – increment the counter by the specified delta.
2.	Done() – Decrement the counter by ones.
3.	Wait() – Blocks until the counter becomes zero.

























b.	Mutex: The sync.Mutex that provides a locking mechanism to protect shared resources from concurrent access. It ensures that only one goroutine can access the resources at a time.
















c.	RWMutex: The sync.RWMutex type is a reader-writer lock that allows multiple readers or a single writer. It is useful when you have more read operations than write operations.

				























d.	Channel: Channels provide a way for goroutines to communicate and synchronize by passing data. They can be used to signal completion, pass data, or coordinate actions.


17)	What is nil in Golang?
nil is predefined which represent zero value for Pointers, channel, maps, slices and function type.

18)	What is the difference between array and slice?
Array	Slice
It has fixed collection of data	Much more flexible, powerful, and convenient than arrays, 
Once length is set it cannot be changed	Slice can be resized using built in append function
It is value type mean when you assign one array to another array whole value will be copied to the assigned array ex: arr1 = [3]int {1,2,3}
arr2 = arr1 // arr2 is copy of arr1	It is reference type.
slice1 := []int{1, 2, 3}
slice2 := slice1 // slice2 refers to the same underlying array as slice1 
Memory of array is allocated at the time of declaration and size is fixed	It does not allocate memory for their elements. Instead, they reference an underlying array.  The make function can be used to create slice with a specified length and capacity
Ex: arr := [4]int{3, 2, 5, 4}	Ex: slicee:= make([]Type, length, capacity)

19)	How does a go complier work?
a.	Lexical Analysis (Scanning) 
i.	Convert source code into token.
b.	Syntax Analysis (Parsing)
i.	Constructs an Abstract Syntax tree (AST) from token.
c.	Semantic Analysis 
i.	Checks for semantic errors.
d.	Intermediate Representation 
i.	Generate an IR of the code.
e.	Optimization
i.	Optimizes the IR.
f.	Code Generation
i.	Translates the IR into machine code and produces an executable binary.

20)	What is an interface and why do we use it?
	Interfaces can make code clearer, shorter, more readable, and they can provide a good API between packages, or clients (users) and servers (providers).








21)	What is concurrency and Parralism and what is the difference between both?
Concurrency	Parralism
Dealing with multiple things at once.	Parallelism is about doing lots of things at once
A Composition of independently executing processes.
(Example: suppose there are two tasks A and B, the way this work is A task done 70% meanwhile it has to wait for something, so it picks up task B and try to complete if suppose B task has to wait at 60%, for something then it picks up A task them completes it and comes back to B)	It is the simultaneous execution of (possibly related) computations. 
(Example: suppose there are two tasks A and B, it takes both tasks and try to complete both together)
	
22)	Difference between goroutine and thread?
Goroutine	Thread
Lightweight	Heavy
Managed by go runtime	Managed by OS
Growable stack	Fixed stack
Communicate using channel	Communicate through various synchronization mechanism
Scheduled by go runtime	Scheduled by OS

23)	How does goroutine handle thread safety?
a.	Using mutex (sync.mutex) lock and unlock access to shared resources ensure that only one goroutine can access at a time.
24)	What is channel?
25)	What is buffered channel?
26)	What is closure?
A closure is a programming function that retain access to its lexical scope, even when the function is executed outside that scope. This means that a “closure” remembers the environment in which it was created, including any variables that were in scope at the time of its creation.

27)	What is pitfall of closure function?
a.	Unintended variable capture
b.	Memory leak
c.	debugging complexity

28)	How can we avoid Unintended capture variable? 
a.	Use Function Parameters
b.	Use Structs or custom Types.
c.	Be mindful of loop variables.

29)	How can I avoid memory leak in closure?
a.	Avoid capturing Unnecessary Variables
b.	Release resources Explicitly
c.	Use short-lived closure.
d.	Be mindful with goroutines.

30)	Go garbage collection strategies?
a.	Tracing garbage collection
b.	Concurrent collection
i.	Go garbage collection designed to run concurrently with the application, minimizing “stop-the-world” pauses. This mean application can continue running while garbage collection is working. Which helps to maintain low latency and high throughput.
c.	Write barrier.
i.	Ensure data integrity.

31)	What are runtime and runtime package?
The runtime library implements garbage collection, concurrency, stack memory management and other critical feature of Go lang.

32)	How can you get how many cores your computer has?
With the help of runtime package and command is runtime.NumCPU()

33)	How would you tell a goroutine to tell use less core than you have?
To limit the number of CPU cores that your Go program uses, you can use the runtime.GOMAXPROCS function. This function sets the maximum number of operating system threads that can execute user-level Go code simultaneously. By default, GOMAXPROCS is set to the number of CPU cores available on your machine, but you can adjust it to use fewer cores.

34)	How would you determine the type of a variable and Which package to use for it?

a.	There are three different ways to find type of variable in Golang.

i.	reflect.TypeOf Function: Using the Golang inbuilt package reflect we can find the Type of variable
ii.	reflect.ValueOf.Kind() Function : Using the Golang inbuilt package reflect we can find the Type of variable
iii.	%T with Printf: You can use Printf also to find value of variable

35)	What all types can map store?

a.	Value - The Value type of a map can be anything, including another map.
b.	Key - The key type of Map can only be values that can be compared i.e. - Boolean, numeric, string, pointer, channel, and interface types, and structs or arrays, that excludes - slices, maps, and functions.


36)	What are microservices?
Microservices is an architectural style that structures an application as a collection of services that are: -
i.	Highly maintainable and testable
ii.	Loosely coupled.
iii.	Independently deployable
iv.	Organized around business capabilities.
v.	Owned by a small team.

37)	What is an interface?
An interface is a set of methods which can be implemented with type, where type here specify any structs, primitive type. Interface does not define the data type it holds or the exact implementation of methods.

a.	Polymorphism: interface enables polymorphism in Go. A Single function can accept different type if all of them implement the same interface.

38)	What is an empty interface?
a.	An empty interface does not hold any method. Benefit of empty interface is that if you pass this as parameter into any function that can have any data type. To know the data type it hold you need to use assertion, where assertion is a mechanism in go that is used to retrieve the dynamic value from an interface variable. When you have an interface variable, you know it’s just an interface, but you don’t know what concrete type it hold.
39)	What are the benefits of using Go compared to other languages?
40)	Can you explain the Go memory model and how it impacts performance?
41)	How do you handle error management in Go?
42)	What are goroutines and how do they differ from threads?   -- Concurrency
43)	How do you manage synchronization between goroutines?
44)	Explain the use of channels in Go and provide an example.
45)	What is the select statement and how is it used in Go?
46)	How do you implement a concurrent-safe map in Go? -- DSA
47)	What are slices in Go and how do they differ from arrays?
48)	Explain the concept of interfaces in Go and how they are used.
49)	What is reflection in Go and when would you use it? – Advanced Topic
50)	How does Go handle garbage collection?
51)	Discuss the implementation and use of context in Go.
52)	Write a function to reverse a string in Go. – Practice Program
53)	Implement a worker pool in Go using goroutines and channels.
54)	How would you optimize a Go application for performance?

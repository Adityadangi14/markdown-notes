# **Golang: Data Types & Memory Management** 🚀  

This guide covers **primitive types, structs, slices, maps, interfaces, pointers, and memory allocation** in Go.  

---

## **1. Primitive Data Types** 🛠️  
Go has built-in **numeric, string, and boolean** types.  

### **🔹 Numeric Types**  
| Type | Description | Example |
|------|-------------|---------|
| `int`, `int8`, `int16`, `int32`, `int64` | Signed integers | `var x int = 10` |
| `uint`, `uint8`, `uint16`, `uint32`, `uint64` | Unsigned integers | `var y uint = 20` |
| `float32`, `float64` | Floating-point numbers | `var f float64 = 3.14` |
| `complex64`, `complex128` | Complex numbers | `var c complex128 = 1 + 2i` |
| `byte` | Alias for `uint8` | `var b byte = 'A'` |
| `rune` | Alias for `int32`, represents a Unicode character | `var r rune = '你'` |

### **🔹 String & Boolean**  
| Type | Description | Example |
|------|-------------|---------|
| `string` | Immutable sequence of characters | `var s string = "Hello"` |
| `bool` | Boolean type (`true` or `false`) | `var flag bool = true` |

#### **String Operations**  
```go
s1 := "Hello"
s2 := " World"
s3 := s1 + s2 // "Hello World"
length := len(s3) // Get string length
```

---

## **2. Composite Data Types** 🎯  

### **🔹 Structs (User-defined Types)**  
A `struct` is a collection of fields.  
```go
type Person struct {
    Name string
    Age  int
}

p := Person{Name: "Alice", Age: 25}
fmt.Println(p.Name) // Alice
```

### **🔹 Slices (Dynamic Arrays)**  
Slices provide a more flexible way to handle collections.  
```go
nums := []int{1, 2, 3}
nums = append(nums, 4, 5) // [1, 2, 3, 4, 5]
fmt.Println(len(nums), cap(nums)) // Length & capacity
```

### **🔹 Maps (Key-Value Store)**  
```go
m := make(map[string]int)
m["Alice"] = 25
fmt.Println(m["Alice"]) // 25
```

### **🔹 Interfaces (Dynamic Behavior)**  
Interfaces define behavior without implementation.  
```go
type Animal interface {
    Speak() string
}

type Dog struct{}

func (d Dog) Speak() string {
    return "Woof!"
}

var a Animal = Dog()
fmt.Println(a.Speak()) // Woof!
```

---

## **3. Pointers & Memory Management** 🧠  

### **🔹 Pointers**  
A pointer holds the memory address of a value.  

#### **Declaring a Pointer**  
```go
var x int = 42
var p *int = &x // p points to x
fmt.Println(*p) // Dereferencing (output: 42)
```

#### **Modifying a Value Using a Pointer**  
```go
*p = 100
fmt.Println(x) // 100
```

---

## **4. Memory Allocation 🏗️**  
Go has `new` and `make` for memory allocation.  

### **🔹 Using `new` (Allocates Zeroed Memory)**  
Returns a pointer to a zero-initialized value.  
```go
p := new(int) // *int, initialized to 0
fmt.Println(*p) // 0
```

### **🔹 Using `make` (Allocates Memory for Slices, Maps, Channels)**  
```go
s := make([]int, 5) // Slice of length 5
m := make(map[string]int) // Empty map
ch := make(chan int) // Channel
```

---

## **5. Garbage Collection 🗑️**  
Go has automatic garbage collection, meaning you **don’t need to manually free memory**.  

### **✅ Best Practices for Memory Management**  
- **Use pointers** for large structures to avoid unnecessary copying.  
- **Prefer slices over arrays** for dynamic collections.  
- **Set unused maps/slices to `nil`** to free memory.  

---

## **🔹 Summary** 🎯  

✅ **Primitive Types** – `int`, `float64`, `string`, `bool`, `complex128`  
✅ **Structs, Slices, Maps, Interfaces** – Essential for Go data structures  
✅ **Pointers** – Memory-efficient data manipulation  
✅ **Memory Allocation** – `new` (values) vs `make` (slices, maps, channels)  


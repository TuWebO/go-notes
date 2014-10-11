# go-notes

Go Language learning notes

## Variables and declaration sintax
[Go declaration sintax](http://blog.golang.org/gos-declaration-syntax)

[Useful C sintax reading - The Clockwise/Spiral Rule](http://c-faq.com/decl/spiral.anderson.html)

###Variables
1. Basic types  
   ```
   bool

   string

   int  int8  int16  int32  int64
   uint uint8 uint16 uint32 uint64 uintptr

   byte // alias for uint8

   rune // alias for int32
        // represents a Unicode code point

   float32 float64

   complex64 complex128
   ```  
2. A var statement can be at package or function level.  
3. The var statement declares a list of variables; as in function argument lists, the type is last.  
   Also note that variable declarations may be "factored" into blocks
   ```Go
   
   var c, python, java bool  
   var (
	  ToBe   bool       = false
	  MaxInt uint64     = 1<<64 - 1
	  z      complex128 = cmplx.Sqrt(-5 + 12i)
   )
   
   ```  
4. A var declaration can include initializers, one per variable. If an initializer is present, the type can be omitted; the variable will take the type of the initializer.  
   ```Go
   
   var i, j int = 1, 2  
   var c, python, java = true, false, "no!"
   ```  
5. Inside a function, the **:= short assignment** statement can be used in place of a var declaration with implicit type.  
   Outside a function, every statement begins with a keyword (var, func, and so on) and so the := construct is not available.  
   Constants cannot be declared using the := syntax.  
   ```Go
   
   var i, j int = 1, 2  
   k := 3  
   c, python, java := true, false, "no!"
   ```

###Arrays & slices
[Go slices usage and internals](http://blog.golang.org/go-slices-usage-and-internals)  
1. An array type definition specifies a length and an element type.  
   Unlike an array type, a slice type has no specified length.  
   ```Go
   
   // An array literal can be specified like so:  
   b := [2]string{"Penn", "Teller"}  
   Or  
   b := [...]string{"Penn", "Teller"}
   ```  
   ```Go
   
   // A slice literal is declared just like an array literal, except you leave out the element count:    
   letters := []string{"a", "b", "c", "d"}  
   // A slice can be created with the built-in function called make, which has the signature,  
   func make([]T, len, cap) []T  
   // The make function takes a type, a length, and an optional capacity. When called, make allocates an array and returns a slice that refers to that array.  
   var s []byte
   s = make([]byte, 5, 5)
   // s == []byte{0, 0, 0, 0, 0}
   ```  

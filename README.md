# go-notes

Go Language learning notes

##Declaration sintax
[Go declaration sintax](http://blog.golang.org/gos-declaration-syntax)

[Useful C sintax reading - The Clockwise/Spiral Rule](http://c-faq.com/decl/spiral.anderson.html)

###Variables
1. A var statement can be at package or function level.
2. The var statement declares a list of variables; as in function argument lists, the type is last.  
   ```go
   var c, python, java bool
   ```
3. A var declaration can include initializers, one per variable. If an initializer is present, the type can be omitted; the variable will take the type of the initializer.  
   ```go
   var i, j int = 1, 2
   
   var c, python, java = true, false, "no!"
   ```


# Classes

**Classes are a template for creating objects.**  
They encapsulate data with code to work on that data. Classes in JS are built on prototypes.  

Classes are in fact **special functions**, and just as you can define **function expressions** and **function declarations**,  
the class syntax has two components: **class expressions** and **class declarations**.

```
class User {
  constructor(name) { this.name = name; }
  sayHi() { alert(this.name); }
}
```
Вот что на самом деле делает конструкция class User {...}:  
1. Создаёт функцию с именем User, которая становится результатом объявления класса.  
Код функции берётся из метода constructor (она будет пустой, если такого метода нет).
2. Сохраняет все методы, такие как sayHi, в User.prototype.


## Class declarations

To declare a class, you use the class keyword with the name of the class ("Rectangle" here).
```
class Rectangle {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
}
```

**Hoisting**  

classes must be defined before they can be constructed. Code like the following will throw a ReferenceError:  
```
const p = new Rectangle(); // ReferenceError
class Rectangle {}
```  
This occurs because while the class is hoisted its values are not initialized.

## Class expressions

Class expressions can be named or unnamed. The name given to a named class expression is local to the class's body.  
However, it can be accessed via the name property.
``` 
// unnamed
let Rectangle = class {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
};
console.log(Rectangle.name);
// output: "Rectangle"

// named
let Rectangle = class Rectangle2 {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
};
console.log(Rectangle.name);
// output: "Rectangle2"
``` 


**Hoisting** the same as **class declarations**

**Constructor**

The constructor method is a special method for creating and initializing an object created with a class.
```
constructor(height, width) {
    this.height = height;
    this.width = width;
  }
```

**Static methods and properties**  

The static keyword defines a static method or property for a class.  
Static members (properties and methods) are called without instantiating their class and cannot be called through a class instance.

**Super class calls with super**

The super keyword is used to call corresponding methods of super class. This is one advantage over prototype-based inheritance.

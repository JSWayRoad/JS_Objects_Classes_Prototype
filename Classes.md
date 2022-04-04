# Classes

**Classes are a template for creating objects.**  
They encapsulate data with code to work on that data. Classes in JS are built on prototypes.  
![Screenshot_32](https://user-images.githubusercontent.com/66359081/161511810-114bb720-14d2-4c4d-91ab-1770c035aaef.png)
![Screenshot_34](https://user-images.githubusercontent.com/66359081/161513415-39b24031-cde9-4b49-9216-7d5df035d5f4.png)
![Screenshot_35](https://user-images.githubusercontent.com/66359081/161513926-4bddb481-7843-40c9-a677-fbef1bcf2975.png)
![image](https://user-images.githubusercontent.com/66359081/161514178-9447db6c-d919-47e3-9c0a-b2473ba5e5ec.png)
В основном он используется, когда мы хотим получить доступ к переменной, методу или конструктору в базовом классе из производного класса

## Static properties and methods

We can also assign a method to the class as a whole. Such methods are called static.  
In a class declaration, they are prepended by static keyword, like this:  
```
class User {
  static staticMethod() {
    alert(this === User);
  }
}

User.staticMethod(); // true
```  
Static properties are used when we’d like to store class-level data, also not bound to an instance.  
The **instanceof** operator allows to check whether an object belongs to a certain class. It also takes inheritance into account.  

**Mixin** – is a generic object-oriented programming term: a class that contains methods for other classes.


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

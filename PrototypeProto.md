https://learn.javascript.ru/prototypes  
https://github.com/radomir-radionov/closures_and_objects#9  

**the prototype chain** - последовательная связь между объектами.


# [[Prototype]]

 JavaScript, objects have a special hidden property [[Prototype]] (as named in the specification),  
 that is either null or references another object. That object is called “a prototype”:

![Screenshot_23](https://user-images.githubusercontent.com/66359081/161436113-d935089b-a225-48fa-adf1-8cebd98dda26.png)

When we read a property from object, and it’s missing, JavaScript automatically takes it from the prototype.  
In programming, this is called **prototypal inheritance**.

## Наследование

В плане наследования JavaScript работает лишь с одной сущностью: объектами. Каждый объект имеет внутреннюю ссылку на другой объект, называемый его прототипом. У объекта-прототипа также есть свой собственный прототип и так далее до тех пор, пока цепочка не завершится объектом, у которого свойство [[Prototype]] равно null.

The property **[[Prototype]]** is internal and hidden, but there are many ways to set it.

One of them is to use the special name __proto__, like this:  
```
let animal = {
  eats: true
};
let rabbit = {
  jumps: true
};

rabbit.__proto__ = animal; // sets rabbit.[[Prototype]] = animal
``` 
Now if we read a property from rabbit, and it’s missing, JavaScript will automatically take it from animal.
![Screenshot_24](https://user-images.githubusercontent.com/66359081/161436430-771e494f-c621-4b4c-9f32-d247c3e6eeba.png)
Here we can say that "animal is the prototype of rabbit" or "rabbit prototypically inherits from animal".

The __proto__ property is a bit outdated. It exists for historical reasons, modern  
JavaScript suggests that we should use **Object.getPrototypeOf/Object.setPrototypeOf** functions instead that get/set the prototype.  

**Object.create()**  
The Object.create() method creates a new object, using an existing object as the prototype of the newly created object.

The prototype is only used for reading properties.  
Write/delete operations work directly with the object.

**for…in loop**  
The for..in loop iterates over inherited properties too.

# F.prototype

Remember, new objects can be created with a constructor function, like **new F()**.  
If F.prototype is an object, then the new operator uses it to set [[Prototype]] for the new object.  

Please note that **F.prototype** here means a regular property named "prototype" on F
![Screenshot_25](https://user-images.githubusercontent.com/66359081/161437368-91181bca-4def-4b70-94fd-464dacd5dddd.png)
Setting Rabbit.prototype = animal literally states the following: "When a new Rabbit is created, assign its [[Prototype]] to animal".
![Screenshot_26](https://user-images.githubusercontent.com/66359081/161437744-c9631b27-2814-4ea5-a1ef-96beeb25ecc5.png)  
On the picture, "prototype" is a horizontal arrow, meaning a regular property, and [[Prototype]] is vertical, meaning the inheritance of rabbit from animal.

F.prototype property is only used when new F is called, it assigns [[Prototype]] of the new object.

## Default F.prototype, constructor property

Every function has the "prototype" property even if we don’t supply it.  
The default "prototype" is an object with the only property constructor that points back to the function itself.  
Like this:
![Screenshot_27](https://user-images.githubusercontent.com/66359081/161437952-36782e67-4415-45d6-99fd-e2be09ac0618.png)  
https://javascript.info/function-prototype  

**The value of F.prototype should be either an object or null: other values won’t work.**  
**The "prototype" property only has such a special effect when set on a constructor function, and invoked with new.**

# Native prototypes

https://javascript.info/native-prototypes

Short notation obj = {} is the same as obj = new Object(), where Object is a built-in object constructor function,  
with its own prototype referencing a huge object with toString and other methods.

Here’s what’s going on:
![Screenshot_28](https://user-images.githubusercontent.com/66359081/161501015-0765615e-c006-4cde-8272-e309a5e932e1.png)
![Screenshot_29](https://user-images.githubusercontent.com/66359081/161501153-91eb8607-d8ab-4b3a-9bb0-f526dc9a45b6.png)
![Screenshot_30](https://user-images.githubusercontent.com/66359081/161501414-1fb19908-0a4d-4d8a-9ecc-5e59f9e1a2a7.png)

# Prototype methods, objects without __proto__
![Screenshot_31](https://user-images.githubusercontent.com/66359081/161508417-d9240b6c-f42a-42eb-b68c-52b8a3da564a.png)

**prototype?**  

prototype является свойством объекта Name. Это прототип объектов, построенных этой функцией.  

The Object.create() method creates a new object, using an existing object as the prototype of the newly created object.  
const me = Object.create(person);








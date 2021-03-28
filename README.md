# Mission 10x Your Js

Looking for the best guide on JavaScript interview questions?

Forget all your worries, you have landed on the Repository that will cover all the frequently asked JavaScript interview questions for freshers and advanced learners. 

This interview preparation guide includes all the major concepts of JavaScript language that will help you to crack your upcoming JavaScript interview. 

## 1. [What are the Some ways to create objects in JavaScript??](#)

**My connecting** flight to Bangalore was delayed by 5  hours, and i was sitting in New Delhi airport, lazily watching the hustle and bustle of passengers.

Among my fellow passengers was one gentleman, who was sitting beside me. 

We were talking for the last 15 minutes. And he suddenly Asked, What Really Happened to Malaysian Airline flight MH370…

Let’s discover 3 ways to create object and find out what happened to MH370.

(i)- Using the Object Literal Notation:-

To Create JavaScript Object with Object Literal Notation, you have to simply define the property and their values inside curly braces.

 ```javascript
 var flight = {
   name: 'MH370', 
   maker:'Boeing', 
   model:'777',
   crashDate: '8.March.2014',
   location: 'Indian Ocean',
   cause:'Pilot Suicide' };

// You can access the properties by dot notation or bracket notation 

console.log(flight.model);
console.log(flight['cause']);
// Expected output = '777'
// Expected output = 'Pilot Suicide'

//you can change or add new property by dot notation

flight.cause = 'unknown'; 
flight.pilotName = 'Zaharie Ahmad Shah'; 
console.log(flight.cause);
console.log(flight.pilotName);
//Expected output = 'unknown'
//Expected output = 'Zaharie Ahmad Shah'

 ```
 (ii)- Using the Object Constructor:-
 
 To Create Javascript Object with a constructor function you need a ‘new’ keyword only.
 
 ```javascript
 var pilot = {
   name: 'Zaharie Ahmad Shah',
   age: 55,
};

var pilotWife = new Object(); 
   pilotWife.name = 'Faizah Shah';
   pilotWife.age = 45;
   console.log(pilotWife);

// Expected output = age: 45,
// Expected output = name: "Faizah Shah"
 ```
 



 (iii) - Using the Object.create() :-
 
The only difference between constructor and Object.create is that it allows you to create an object with attributes. Let’s see below.

 ```javascript
 var pilot = {
   name: 'Zaharie Ahmad Shah',
   age: 55,
};

var pilotWife = Object.create(null); 
   pilotWife.name = 'Faizah Shah';
   pilotWife.age = 45;
   console.log(pilotWife);

// Expected output = age: 45,
// Expected output = name: "Faizah Shah"  

 ```

Learn More at [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)

## 2. [What is prototypal Inheritance?](#)


A lot of inheritance blog on internet uses all kinds of crazy examples with trees and babies to make you understand inheritance. I think it’s better just to directly say what inheritance does :-

#### When You have a class, And you have another class, And when you can go and get access to the properties and methods on that other class it’s called Inheritance.

Before we look at how prototypes are used to inherit functionality.

First Let’s Create a user-defined object using function and than Create an instance of the object using new keyword.

#### (i)- Create Function Object Using new Keyword

```javascript 
let's create a new function, i'll call it family

function family(father, mother, wife, daughter, sister) {
    this.father = father;
    this.mother = mother;
    this.wife   = wife;
    this.daughter = daughter;
    this.sister  = sister;
} 
// Now i'm going to create/instance two object john and syam using new keyword.

const John = new family('rob', 'Margie', 'Alicia', 'Ellie', 'lara')

const Syam = new family('Nath', 'Seema', 'Sara', 'Priya', 'anita') 

console.log(John); 

// Expected Output of john :-

family { father: "rob", 
         mother: "Margie", 
         wife: "Alicia", 
         daughter: "Ellie", 
         sister: "lara" }

console.log(Syam); 

// Expected Output of syam:-

family { father: "Nath", 
         mother: "Seema", 
         wife: "Sara", 
         daughter: "Priya", 
         sister: "anita"}
```

After creating the function we have used new keyword to create a new Object John and syam. And this variable inside function family is pointing to the newly created object john and syam.

if you want to learn how this keyword works under the hood, read my post on this keyword This Keyword In JavaScript with 3 Easy Examples

Since ECMAScript 2015 release, We can use Class based Inheritance In JavaScript, Which are primarily a syntactical sugar over JavaScript’s existing prototype-based inheritance.

So, Now let’s look at another easy example of how ECMAScript classes are used to Create an Object

#### (ii)- Create class using new keyword

```javascript 

class family {
  constructor(father, mother, wife, daughter, sister) {
  
    this.father = father;
    this.mother = mother;
    this.wife   = wife;
    this.daughter = daughter;
    this.sister  = sister;
}}
// Now i'm going to create two new object federico and jorge using new keyword.

const federico = new family('rob', 'Margie', 'Alicia', 'Ellie', 'lara')

const jorge = new family('Nath', 'Seema', 'Sara', 'Priya', 'anita') 

console.log(federico); 

// Expected Output of federico :-

family { father: "rob", 
         mother: "Margie", 
         wife: "Alicia", 
         daughter: "Ellie", 
         sister: "lara" }

console.log(jorge); 

// Expected Output of jorge:-

family { father: "Nath", 
         mother: "Seema", 
         wife: "Sara", 
         daughter: "Priya", 
         sister: "anita"}
```

In the example above we have used the constructor method which is a special method for creating and initialising an object created within a class.

I’ll repeat again, The class syntax does not introduce a new object-oriented inheritance model to JavaScript, its just a syntactical sugar over JavaScript’s existing prototype-based inheritance

So, far in 2 examples above we’ve talked about creating object using new keyword , Now let’s look at how prototypes are used to inherit functionality.

#### (iii) Prototypal Inheritance Using Class

```javascript 
// let's create a function object, I'll again call it family

function Family(father, mother, wife, daughter, sister) {
    this.father = father;
    this.mother = mother;
    this.wife   = wife;
    this.daughter = daughter;
    this.sister  = sister;
    
} 

// let's create another function object, I'll again call it family2

function Family2(father, mother, wife, daughter, sister, brother) {
   // inheritence by call method
  Family.call(this, father, mother, wife, daughter, sister)
  this.brother = brother;  
} 

const jon = new Family('rob', 'Margie', 'Alicia', 'Ellie', 'lara');


const ron = new Family2('Nath', 'Seema', 'Sara', 'Priya', 'anita', 'Trump');

console.log(jon);

// Expected Output -

Family {father: "rob", mother: "Margie", wife: "Alicia", daughter: "Ellie", sister: "lara"}

console.log(ron);.

// Expected Output - 

Family2 {father: "Nath", mother: "Seema", wife: "Sara", daughter: "Priya", sister: "anita", …}
```

In the example 4 we’ll see how we can use prototype chain is used to inherit functionality. So before that What is Prototype Chain ?

When an attribute is called on an object, the object is first checked for that attribute, and if it doesn’t exist, then each link in its prototype chain is traversed until the attribute is found

#### (iV) - Prototypal inheritance using Prototype Chaining

```javascript 
function PrintMyPassport(myPassport) {
this.documents = myPassport;
}

// We add the print () method to PrintMyPassport prototype property so that other instances (objects) can inherit it:

PrintMyPassport.prototype.print = function() {
console.log(this.documents);
}

// Create a new object with the PrintMyPassport () constructor, thus allowing this newPass object to inherit PrintMyPassport's properties and methods.

var newPass = new PrintMyPassport("I am a new Object and I can print your passport.");

// newPass inherited all the properties and methods, including the print method, from the PrintMyPassport function. Now newPass can call print directly, even though we never created a print () method on it.

newPass.print(); //I am a new Object and I can print.
```

## 3 - [What's the diffrence between Var vs Let vs Const ? ](#)

Variable declared using var keyword inside the function is available throughout that function as well as to nested function, see example below

```javascript
function multiplyNum() {
     var a = 20
     var b = 30
     var captain = true

     if(captain) {
       var multiply = a * b
       console.log('multiply with captain',multiply )
     }

     console.log('multiply without captain',multiply )
}

multiplyNum()
// output for both multiply with or without captain will be 600 and 600, and that's the reason it's called function scoped
```

Variable declared using const keyword inside the function is available only to that function, see example below

```javascript
function multiplyNum() {
     const a = 20
     const b = 30
     const captain = true

     if(captain) {
       const multiply = a * b
       console.log('multiply with captain',multiply )
     }

     console.log('multiply without captain',multiply )
}

multiplyNum()
// output for multiply with captain will be 600 but multiply without captain will throw an error called sum is not defined, and that's the reason it's called block scoped
```

Variable declared using let keyword behaves same wrt. scope, only diffrence is all const declarations must be intialized and once initialized you cannot reassign to a new value.



# ES6 Experimentation

The official ES5 Specification http://www.ecma-international.org/publications/files/ECMA-ST/Ecma-262.pdf

Support across browsers and platforms: http://kangax.github.io/compat-table/es6/

ES4 previously tried to add to and enhance Javascript features but it was abandoned.

ES6 (started with codename : Harmony) is the biggest change to Javascript in over a decade.

# Variables and Parameters

New features: let, const, destructuring, default parameter values, rest paraemters, template literals, spread operator.

### let Keyword

'let' is the new 'var'

Normal variables in JS usually either have global or functional scope.
'Let' changes this by applying scope within conditional statements too.

Let will replace var as it allows proper 'block scoping'.

Example
https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=%0A%0Avar%20es6Add%20%3D%20(x%2C%20y)%20%3D%3E%20x%2By%3B%0A%0Avar%20add%20%3D%20function%20(x%2C%20y)%20%7B%0A%20%20return%20x%2B%20y%3B%0A%7D%0A%20%20%20%20

### const

Constant values - read only values. Cannot be overwritten, just like other structured languages.

### Destructuring

[x,y] = [y,x] - This will overwrite the values of x and y with the values of y and x

Example
https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=%0A%0Avar%20doWork%20%3D%20function%20()%20%7B%0A%20%20return%20%5B1%2C%202%2C%203%5D%0A%7D%3B%0A%0Alet%20%5Bx%2Cy%2Cz%5D%20%3D%20doWork()%3B%0A%0A%0A%2F%2F%20Returns%203%0Aconsole.log(z)%3B%0A%0Avar%20doMoreWork%20%3D%20function%20()%20%7B%0A%20%20return%20%7B%0A%20%20%20%20firstName%20%3A%20'Fintan'%2C%0A%20%20%20%20lastName%20%3A%20'Kearney'%2C%0A%20%20%20%20age%20%3A%2028%0A%20%20%7D%0A%7D%0A%0Alet%20%7B%20firstName%20%3A%20name%2C%20age%20%3A%20age%20%7D%20%3D%20doMoreWork()%3B%0A%0Aconsole.log(name)%3B%0A%0A%20%20%20%20

### Default Parameters

Previously in Javscript you would need to use a conditional statement within a function to check if the variable was empty in order to set a default. This is not the case with ES6.
You can set default parameter values in the function name just like C# or JAVA.

Example
https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=%0A%0Alet%20doWorkOld%20%3D%20function%20(name)%20%7B%0A%20%20name%20%3D%20name%20%7C%7C%20%22Old%20default%20parameter%20value%22%3B%0A%20%20return%20name%3B%0A%7D%0A%0Alet%20doWorkNew%20%3D%20function%20(name%3D%22New%20default%20parameter%20value%22)%20%7B%0A%20%20return%20name%3B%0A%7D%0A%0A%2F%2F%20Call%20the%20functions%0Aconsole.log(doWorkOld())%3B%0Aconsole.log(doWorkNew())%3B%0A%0A%20%20%20%20

### Rest Parameters

Rest parameters are always the last parameters in a function and will accept any unhandled arguments passed to a function

https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=let%20sum%20%3D%20function%20(...numbers)%20%7B%0A%20%20let%20result%20%3D%200%3B%0A%20%20for%20(let%20i%20%3D%200%3B%20i%20%3C%20numbers.length%3B%20i%2B%2B)%20%7B%0A%20%20%20%20result%20%2B%3D%20numbers%5Bi%5D%3B%0A%20%20%7D%0A%20%20return%20result%3B%0A%7D%0A%0Alet%20result%20%3D%20sum(1%2C2%2C3)%3B%0A%0A%2F%2F%206%0Aconsole.log(result)%3B%0A%0A%20%20%20%20

### Spread Operator

Using the spread operator '...x' you can pass an array into another

https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=%0Avar%20a%20%3D%20%5B4%2C5%2C6%5D%3B%0Avar%20b%20%3D%20%5B1%2C%202%2C%203%2C%20...a%2C%207%20%2C8%2C%209%5D%3B%0A%0Aconsole.log(a)%3B%0A%0A%20%20%20%20


### Template Literals

Template literals allow you to be smarter about how you can defined strings and pass in parameters in Javscript. You can put variable names in the string definition and it will be updated.

String however must be defined using `` instead of "" or '' and variables are defined using a ${name} syntax.

Example
https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=let%20category%20%3D%20%22music%22%3B%0Alet%20id%20%3D%20123%3B%0A%0Alet%20url%20%3D%20%60http%3A%2F%2Fourwebsite.com%2F%24%7Bcategory%7D%2F%24%7Bid%7D%60%3B%0A%0Aconsole.log(url)%3B%0A%0A%0A%20%20%20%20

# Classes

Classes are now available in the Javascript syntax. Prototypes are no longer needed.

A class keyword is now available so we can create a blueprint for our objects.

Example of ES6 class being transpiled
https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=class%20OurClass%20%7B%0A%20%20doSomething()%20%7B%0A%20%20%20%20return%20%22Hello%20World%22%3B%0A%20%20%7D%0A%7D%0A%0A%0A%20%20%20%20

### Magic Methods

constructor() - Allows you to use the 'this keyword'
https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=class%20Person%20%7B%0A%20%20%0A%20%20constructor%20(name)%20%7B%0A%20%20%20%20this._name%20%3D%20name%3B%0A%20%20%7D%0A%20%20%0A%20%20doWork()%20%7B%0A%20%20%20%20return%20%22Done!%22%0A%20%20%7D%0A%20%20%0A%20%20getName()%20%7B%0A%20%20%20%20return%20this._name%3B%0A%20%20%7D%0A%7D%0A%0Alet%20p1%20%3D%20new%20Person(%22Alan%22)%3B%0Alet%20p2%20%3D%20new%20Person(%22Steve%22)%3B%0A%0Aconsole.log(p1.getName())%3B%0Aconsole.log(p2.getName())%3B%0A%20%20%20%20


### Getters and Setters

You can now access properties in objects directly without calling a function by definining setters and getters to allow access
https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=%20%20class%20Person%20%7B%0D%0A%20%20%20%20%20%20constructor%20(name)%20%7B%0D%0A%20%20%20%20%20%20%20%20this.name%20%3D%20name%3B%0D%0A%20%20%20%20%20%20%7D%0D%0A%20%20%20%20%20%20%0D%0A%20%20%20%20%20%20doWork()%20%7B%0D%0A%20%20%20%20%20%20%20%20return%20%22Done!%22%0D%0A%20%20%20%20%20%20%7D%0D%0A%20%20%20%20%20%20%0D%0A%20%20%20%20%20%20get%20name()%20%7B%0D%0A%20%20%20%20%20%20%20%20return%20this._name.toUpperCase()%3B%0D%0A%20%20%20%20%20%20%7D%0D%0A%20%20%20%20%20%20%0D%0A%20%20%20%20%20%20set%20name(value)%20%7B%0D%0A%20%20%20%20%20%20%20%20this._name%20%3D%20value%3B%0D%0A%20%20%20%20%20%20%7D%0D%0A%20%20%7D%0D%0A%0D%0Alet%20p1%20%3D%20new%20Person(%22Alan%22)%3B%0D%0Aconsole.log(p1.name)%3B%0D%0A%0D%0Ap1.name%20%3D%20%22Steve%22%3B%0D%0Aconsole.log(p1.name)%3B%0D%0A%20%20%20%20


### Inheritance

Object Inheritance is now permitted like other popular obkect oriented languages. It was possible using libaries and prototypes but not part of the base syntax.

Example
https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=%20%20class%20Person%20%7B%0D%0A%20%20%20%20%20%20constructor%20(name)%20%7B%0D%0A%20%20%20%20%20%20%20%20this.name%20%3D%20name%3B%0D%0A%20%20%20%20%20%20%7D%0D%0A%20%20%20%20%20%20%0D%0A%20%20%20%20%20%20doWork()%20%7B%0D%0A%20%20%20%20%20%20%20%20return%20%22Done!%22%0D%0A%20%20%20%20%20%20%7D%0D%0A%20%20%20%20%20%20%0D%0A%20%20%20%20%20%20get%20name()%20%7B%0D%0A%20%20%20%20%20%20%20%20return%20this._name.toUpperCase()%3B%0D%0A%20%20%20%20%20%20%7D%0D%0A%20%20%20%20%20%20%0D%0A%20%20%20%20%20%20set%20name(value)%20%7B%0D%0A%20%20%20%20%20%20%20%20this._name%20%3D%20value%3B%0D%0A%20%20%20%20%20%20%7D%0D%0A%20%20%7D%0D%0A%0D%0Alet%20p1%20%3D%20new%20Person(%22Alan%22)%3B%0D%0Aconsole.log(p1.name)%3B%0D%0A%0D%0Ap1.name%20%3D%20%22Steve%22%3B%0D%0Aconsole.log(p1.name)%3B%0D%0A%0D%0A%0D%0Aclass%20Employee%20extends%20Person%20%7B%0D%0A%20%20%0D%0A%7D%0D%0A%0D%0Alet%20e1%20%3D%20new%20Employee()%3B%0D%0Ae1.name%20%3D%20%22Fintan%22%3B%0D%0A%0D%0Aconsole.log(e1.name)%3B%0D%0A%20%20%20%20


#### Super keyword for Inheritance

You can call functions defined on the parent class using the super keyword.

Example
https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=%20%20class%20Person%20%7B%0D%0A%20%20%20%20%20%20constructor%20(name)%20%7B%0D%0A%20%20%20%20%20%20%20%20this.name%20%3D%20name%3B%0D%0A%20%20%20%20%20%20%7D%0D%0A%20%20%20%20%20%20%0D%0A%20%20%20%20%20%20doWork()%20%7B%0D%0A%20%20%20%20%20%20%20%20return%20%22Done!%22%0D%0A%20%20%20%20%20%20%7D%0D%0A%20%20%20%20%20%20%0D%0A%20%20%20%20%20%20get%20name()%20%7B%0D%0A%20%20%20%20%20%20%20%20return%20this._name.toUpperCase()%3B%0D%0A%20%20%20%20%20%20%7D%0D%0A%20%20%20%20%20%20%0D%0A%20%20%20%20%20%20set%20name(value)%20%7B%0D%0A%20%20%20%20%20%20%20%20this._name%20%3D%20value%3B%0D%0A%20%20%20%20%20%20%7D%0D%0A%20%20%7D%0D%0A%0D%0Alet%20p1%20%3D%20new%20Person(%22Alan%22)%3B%0D%0Aconsole.log(p1.name)%3B%0D%0A%0D%0Ap1.name%20%3D%20%22Steve%22%3B%0D%0Aconsole.log(p1.name)%3B%0D%0A%0D%0A%0D%0Aclass%20Employee%20extends%20Person%20%7B%0D%0A%20%20%20%20%20%20constructor%20(name)%20%7B%0D%0A%20%20%20%20%20%20%20%20super(name)%3B%0D%0A%20%20%20%20%20%20%7D%0D%0A%7D%0D%0A%0D%0Alet%20e1%20%3D%20new%20Employee(%22Fintan%22)%3B%0D%0A%0D%0Aconsole.log(e1.name)%3B%0D%0A%20%20%20%20


### Overrides

You can override functions parent classes be defining the same method within the child class (like JAVA / C#)
https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=%20%20class%20Person%20%7B%0D%0A%20%20%20%20%20%20constructor%20(name)%20%7B%0D%0A%20%20%20%20%20%20%20%20this.name%20%3D%20name%3B%0D%0A%20%20%20%20%20%20%7D%0D%0A%20%20%20%20%20%20%0D%0A%20%20%20%20%20%20doWork()%20%7B%0D%0A%20%20%20%20%20%20%20%20return%20%22Done!%22%0D%0A%20%20%20%20%20%20%7D%0D%0A%20%20%20%20%20%20%0D%0A%20%20%20%20%20%20get%20name()%20%7B%0D%0A%20%20%20%20%20%20%20%20return%20this._name.toUpperCase()%3B%0D%0A%20%20%20%20%20%20%7D%0D%0A%20%20%20%20%20%20%0D%0A%20%20%20%20%20%20set%20name(value)%20%7B%0D%0A%20%20%20%20%20%20%20%20this._name%20%3D%20value%3B%0D%0A%20%20%20%20%20%20%7D%0D%0A%20%20%20%20%20%20%0D%0A%20%20%20%20%20%20toString()%20%7B%0D%0A%20%20%20%20%20%20%20%20return%20this.name%3B%0D%0A%20%20%20%20%20%20%7D%0D%0A%7D%0D%0A%0D%0Aclass%20Employee%20extends%20Person%20%7B%0D%0A%20%20%20%20%20%20constructor%20(name)%20%7B%0D%0A%20%20%20%20%20%20%20%20super(name)%3B%0D%0A%20%20%20%20%20%20%7D%0D%0A%20%20%20%20%20%20%0D%0A%20%20%20%20%20%20toString()%20%7B%0D%0A%20%20%20%20%20%20%20%20return%20%22Override%22%3B%0D%0A%20%20%20%20%20%20%7D%0D%0A%7D%0D%0A%0D%0Alet%20e1%20%3D%20new%20Employee(%22Fintan%22)%3B%0D%0A%0D%0Aconsole.log(e1.toString())%3B%0D%0A%0D%0A%20%20%20%20


## Functional Javascript

Javascript has always been a functional programming language. There are now more features however.

### Arrow functions

Shorthand syntax for declaring functions and returning values. 

Example
https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=let%20add%20%3D%20(x%2C%20y)%20%3D%3E%20x%2By%3B%0D%0A%0D%0Aconsole.log(add(5%2C5))%3B%0D%0A%20%20%20%20


### Iterables and Iterators

Iterators have been available in other languages but are now just arriving. 
Again libraries and frameworks were used to previously provide this functionality.

Iterables were supported before.

Example
https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=%0D%0Alet%20sum%20%3D%200%3B%0D%0Alet%20numbers%20%3D%20%5B1%2C2%2C3%2C4%5D%0D%0A%20%20%20%20%0D%0Asum%20%3D%200%3B%0D%0Afor%20(let%20i%20%3D%200%3B%20i%20%3C%20numbers.length%3B%20i%2B%2B)%20%7B%0D%0A%20%20sum%20%2B%3D%20numbers%5Bi%5D%3B%0D%0A%7D%0D%0A%0D%0A%2F%2F%2010%0D%0Aconsole.log(10)%3B%0D%0A%0D%0Asum%20%3D%200%3B%0D%0Afor%20(let%20i%20in%20numbers)%20%7B%0D%0A%20%20sum%20%2B%3D%20numbers%5Bi%5D%3B%0D%0A%7D%0D%0A%0D%0A%2F%2F%2010%0D%0Aconsole.log(sum)%3B%0D%0A%0D%0Asum%20%3D%200%3B%0D%0A%0D%0Alet%20iterator%20%3D%20numbers.values()%3B%0D%0Alet%20next%20%3D%20iterator.next()%3B%0D%0A%0D%0Awhile%20(!next.done)%20%7B%0D%0A%20%20sum%20%2B%3D%20next.value%3B%0D%0A%20%20next%20%3D%20iterator.next()%3B%0D%0A%7D%0D%0A%0D%0A%2F%2F%2010%0D%0Aconsole.log(sum)%3B

### For of

A handy iterable.

Example
https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=%0D%0Alet%20sum%20%3D%200%3B%0D%0Alet%20numbers%20%3D%20%5B1%2C2%2C3%2C4%5D%0D%0A%20%20%20%20%0D%0Afor%20(let%20n%20of%20numbers)%20%7B%0D%0A%20%20sum%20%2B%3D%20n%3B%0D%0A%7D%0D%0A%0D%0Aconsole.log(sum)%3B%0D%0A%0D%0A

# Built in objects

There are brand new built in objects for Javascript e.g. Map

### Number

Woring with numbers example
https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=%2F%2F%20Parse%20binary%20number%0D%0Avar%20number%20%3D%20Number(%220b101%22)%3B%0D%0Aconsole.log(%22Parse%20Binary%20Number%3A%20%22%20%2B%20%20number)%3B%0D%0A%0D%0A%2F%2F%20Parse%20Integer%0D%0Avar%20number%20%3D%20Number.parseInt(%223%22)%3B%0D%0Aconsole.log(%22Parse%20Integer%3A%20%22%20%2B%20number)%3B%0D%0A%0D%0A%2F%2F%20Parse%20Float%0D%0Avar%20number%20%3D%20Number.parseFloat(%223.56%22)%3B%0D%0Aconsole.log(%22Parse%20Float%3A%20%22%20%2B%20number)%3B%0D%0A%0D%0A%2F%2F%20Check%20if%20a%20number%20is%20finite%0D%0Aconsole.log(%22Global%20Finite%20Check%3A%20%22%20%2B%20isFinite(%221%22))%3B%0D%0Aconsole.log(%22Number%20Object%20Finite%20Check%3A%20%22%20%2B%20Number.isFinite(%221%22))%3B%0D%0A%0D%0A%2F%2F%20Check%20if%20provided%20values%20are%20not%20numbers%0D%0Aconsole.log(%22Global%20%3A%20Is%20NaN%20a%20number%3F%20%3A%20%22%20%2B%20isFinite(%22Nan%22))%3B%0D%0Aconsole.log(%22Is%20NaN%20a%20number%3F%20%3A%20%22%20%2B%20Number.isFinite(%22Nan%22))%3B%0D%0A%0D%0A


## Asynchronous Javscript

Promises like the ones supported by Angular are to be made part of ES6.

The main benefit that promises provide is removing the complexity of normal callbacks and the error handling for all the exceptions that come with them. No more "Callback hell".

![Promises in ES6](http://image.slidesharecdn.com/es6-introduction-151202131610-lva1-app6891/95/introduction-into-es6-javascript-30-638.jpg?cb=1449062282)

### Promises

Basic example of promoises with resolve and exceptions
https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&code=var%20promise%20%3D%20new%20Promise(function(resolve%2C%20reject)%7B%0D%0A%20%20resolve(%22Resolved!%22)%3B%0D%0A%7D)%3B%0D%0A%0D%0Apromise.then(function(data)%7B%0D%0A%20%20console.log(data)%3B%0D%0A%20%20done()%3B%0D%0A%7D)%3B%0D%0A%0D%0Apromise%20%3D%20new%20Promise(function(resolve%2C%20reject)%7B%0D%0A%20%20reject(%22Rejected!%22)%3B%0D%0A%7D)%3B%0D%0A%0D%0Apromise.catch(function(error)%7B%0D%0A%20%20console.log(error)%3B%0D%0A%20%20done()%3B%0D%0A%7D)%3B%0D%0A%0D%0A%0D%0A%0D%0A%0D%0A%0D%0A%0D%0A%0D%0A%0D%0A

### Generators

https://medium.com/@dtothefp/why-can-t-anyone-write-a-simple-es6-generators-tutorial-ec2bbdf6ff45#.asr59j9wb - ;)


## Modules in Javascript  (TBC)

A module system has not been previously supported. Many libaries have been written to support this functionality in Javascript but ES6 aims to support this logic out of the box.

## Tools

In order to support ES6 on older platforms there are tools called 'transpilers' which compile your ES6 into ES5.

Babel: To transpile ES6 into ES5 for static builds
Babelify: To incorporate babel into your Gulp, Grunt, or npm run build process
Traceur compiler: ES6 features > ES5. Includes classes, generators, promises, destructuring patterns, default parameters & more.
es6ify: Traceur compiler wrapped as a Browserify v2 transform

https://lightrains.com/blogs/es6-transpilers

## Other References

http://es6-features.org/
https://github.com/lukehoban/es6features












# Javascript 2

This is a repo used for notes on the javascript 2 lecture.

## Arrays

Arrays are ordered lists in javascript that are zero based indexed. The length of an array is dynamic and can hold however many items that our list needs to hold. Since an array is zero based index, the index value of the first item is 0.

```javascript
let myArray = ['this', 'is', 'my', 'array'];
```

### Bracket Notation

We can access values inside of an array by using `bracket notation` and passing in the index value of the element we want to select.

```javascript
let myArray = ['this', 'is', 'my', 'array'];

console.log(myArray[2]);
```

The above code uses bracket notation to access the third item in the array. We pass in the number 2 inside the brackets so we can select the third item since it is zero based indexed.

### Array Methods

There are built in methods javasceript for the `Array` datatype. These methods are what we can use to manipulate our arrays and what is inside of them.

`.push()` - push is the method we can use on arrays push or append items to the end of our array

```javascript
let myArray = ['this', 'is', 'my', 'array'];

myArray.push('new item');

console.log(myArray) // => ['this', 'is', 'my', 'array', 'new item'];
```

`.pop()` - pop is the array method we can use to remove the last item from an array and return that item

```javascript
let myArray = ['this', 'is', 'my', 'array'];

let arrayItem = myArray.pop();

console.log(myArray) // => ['this', 'is', 'my']
console.log(arrayItem) // => 'array'
```

`.shift()` - shift is the array method that we can use to remove the first element from an array and return that element

```javascript
let myArray = ['this', 'is', 'my', 'array'];

let arrayItem = myArray.shift();

console.log(myArray) // => ['is', 'my', 'array']
console.log(arrayItem) // => 'this'
```

`.unshift()` - unshift is the method we can use to add an item to the beggining of our array

```javascript
let myArray = ['this', 'is', 'my', 'array'];

myArray.unshift('new item');

console.log(myArray) // => ['new item', 'this', 'is', 'my', 'array'];
```

`.slice()` - slice is the method we can use to return a shallow copy of the array

It will take in two arguments, a start index and an end index. If the end index is not provided it will go to the end of the array

NOTE: slice does not mutate the original array

```javascript
let myArray = ['this', 'is', 'my', 'array'];

let shallowCopy = myArray.slice(1,3)

console.log(myArray) // => ['this', 'is', 'my', 'array']
console.log(shallowCopy) // => ['is', 'my']
```

`.splice()` - splice is the method we can use to alter our original array by removing elements. It will also return the elements that are removed.

It will take in two arguments, the beggining index of where to start removing and a number determining how many items to remove. If the end is never provided, it will go until the end of the array.

NOTE: This will mutate our original array

```javascript
let myArray = ['this', 'is', 'my', 'array'];

let missingValues = myArray.splice(1,2);

console.log(myArray) // => ['this', 'array'];
console.log(missingValues) // => ['is', 'my'];
```

splice is also a method that can add items to our array. If we pass third and fourth arguments to the splice it will add the 3rd argument and so on into our array starting at the index value of the item we removed.

```javascript
const myNewArray = [1,2,3,4,5];

myNewArray.splice(1,1, 'hello', 'world')

console.log(myNewArray) // => [ 1, 'hello', 'world', 3, 4, 5 ]
```

`.length` - length is not a method, but a property on an `Array` datatype. Length will give us a number value for how manby elements are inside of an array.

```javascript
const myNewArray = [1,2,3,4,5];

console.log(myNewArray.length) // => 5
```


## For Loops

Looping in javascript is very powerful because it allows us to perform some logic a repeated amount of times. 

Syntax:
```javascript
for(let i = 0; i <= 10; i++){
    // perform logic in here
}
```

There three parts of the for loop are:

`the loop initialization` - this is where we declare our counter variable that we can use to determine the iteration we are currently on.

```javascript
let i = 0
```

`the test statement` - the test statement is where we check for a certain condition to be true before performing the logic inside the code block of the for loop. Once this runs false, our loop will kill of and stop iterating.

```javascript
i <= 10
```

`the iteration statement` - this is where we can either increase or decrease our counter

```javascript
i++
```

### Using A For Loop To Iterate Through An Array

It's also very convienent to use when it come to iterating through arrays.

```javascript
let myArray = ['this', 'is', 'my', 'array'];

for(let i = 0; i < myArray.length; i++){
    console.log(myArray[i]);
};
```

Notice how we can use a for loop to iterate through an array by looping to the length of the array. Then inside of the code block for each iteration we are logging the current value for the iteration in the array by using our counter to decide what value we are accessing in the array since the counter will align with the iteration of the for loop.

We can also iterate through an array backwards.

```javascript
let myArray = ['this', 'is', 'my', 'array'];

for(let i = myArray.length - 1; i >= 0; i--){
    console.log(myArray[i]);
};
```

## Objects

Objects are an unordered collection of key / value pairs. Objects are often used to describe real world like objects: house, person, dog, etc.

```javascript
let myCar = {
    make: 'Tesla',
    model: 'Model X',
    year: 2019
}
```

### Accesing Objects

We can access the values from properties on an object by using `dot notation` or `bracket notation`

### Dot Notation

We can use `dot notation` to access values by suffixing the reference to the object with a period followed by the property name.

```javascript
let myCar = {
    make: 'Tesla',
    model: 'Model X',
    year: 2019
}

console.log(myCar.model) // => 'Model X'
```

We can also create new properties on an object using `dot notation`.

```javascript
let myCar = {
    make: 'Tesla',
    model: 'Model X',
    year: 2019
}

myCar.color = 'white'
```

Above we just created a property on our car object called color with the value of the string 'white'.

### Bracket Notation

We can use `bracket notation` to access value on our object.

```javascript
let myCar = {
    make: 'Tesla',
    model: 'Model X',
    year: 2019
}

console.log(myCar['model']) // => 'Model X'
```

Notice that this looks extremely similar to arrays. However, we will use a string inside of our bracket to select our property inside of our object.

We can also create new properties using `bracket notation`.

```javascript
let myCar = {
    make: 'Tesla',
    model: 'Model X',
    year: 2019
}

myCar.['color'] = 'white'
```

### Methods

`Methods` are functions that exist as a property on an object.

```javascript
let myCar = {
    make: 'Tesla',
    model: 'Model X',
    year: 2019,
    honk: function(){
        console.log('beep beep')
    }
}
```

Using `dot notation` we can access our object and invoke the method

```javascript
let myCar = {
    make: 'Tesla',
    model: 'Model X',
    year: 2019,
    honk: function(){
        console.log('beep beep')
    }
}

myCar.honk();
```

## Ternary Operator

A ternary operator is another way to write an if statement.

> condition ? true : false

```javascript
let myCar = {
    make: 'Tesla',
    model: 'Model X',
    year: 2019,
    honk: function(){
        console.log('beep beep')
    }
}

myCar.year > 2018 ? console.log('your car is brand new') : console.log('your car is getting old');
```

First we have the condition that we check for, that is followed by a `?`. It's easy to think about it like we are asking a question. If the condition is true, the first expression on the right side of the `?` will run, but if it is false it will run the expression that is on the right side of the `:`.

## CallBacks

A callback is a function that is passed into another function as an argument. The callback is then invoked inside of the function.

```javascript
function callback(name){
    console.log(name)
}

function sayName(cb){
    cb('tayte stokes')
}

sayName(callback);
```

Notice how we first create a function `callback` that we will later pass as an argument to `sayName`. In the `sayName` function, we invoke the the `callback` function that we passed in as an argument which can be referenced as `cb`.
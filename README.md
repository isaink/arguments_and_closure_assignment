# Exercises

1. Create two functions: `double` and `square`.
`double` should take a number and return the number times two.
`square` should take a number and return the number squared.

```js
const double = (num) => {
  return num = num + num;
};
console.log(double(4));
```

 * Create a third function `doubleSquare` that uses both of the functions to return a number that is first doubled and then squared.

 ```js
 const square = (num) => {
   return Math.pow(num, 2)
 };
 console.log(square(3))
 ```

2. Create a function `classyGreeting` that takes as input the strings `firstName`  and `lastName`,
and returns a string with a greeting using the two.

```js
const classyGreeting = (firstName, lastName) => {
  return "Hello there " + firstName + " " + lastName;
  //return `Hello, ${firstName}!`
}
console.log(classyGreeting ("isa", "alvarado"));

//and with Default Values

const classyGreeting = (firstName = "isa", lastName = "alvarado" ) => {
  return "Hello there " + firstName + " " + lastName;
  return `Hello, ${firstName}!`
}
console.log(classyGreeting());

//another way
const greeting = (...args) => `Hello ${args[0]} ${args[1]}!`
console.log(greeting("Isa", "Alvarado"));
```

  * Create a second function `yell`  that takes string as input and returns the string in all capitalized letters.

```js
const yell = (str) => {
  return str.toUpperCase()
};
console.log(yell("lala"))

//another way
const yell = str => str.toUpperCase();
console.log(yell("studio"));
```

  * Create a third function  `yellGreeting`  that will take the `firstName`  and `lastName`  as inputs and yell a greeting using the two.

```js
const greeting = (...args) => `Hello ${args[0]} ${args[1]}!`

const yell = str => str.toUpperCase();

const yellGreeting = (...args) => yell(greeting(args[0], args[1]));

console.log(yellGreeting("Isa", "Alvarado"));
```

3. The [concat](https://www.w3schools.com/jsreF/jsref_concat_array.asp) array method is used to merge two (or more) arrays.

Write a `removeDupes` function that takes an array as an argument and returns a copy without any duplicate elements.

```js
  // let arr = [1, 2, 3]
  // arr.includes(1)
  // ==> true

  const removeDupes = (arr) => {
    let outPut = [];
    let obj = {};
    for (let i = 0; i < arr.length; i++){ // Look thru each items index of the array.
      if (!obj[arr[i]]){ //If arr index doesn't included (doesn't have the same item) inside of the Obj index added to the arr.
        obj[arr[i]] = 1; // Add/create one element.
        outPut.push(arr[i]); // Pushed inside the arguments that value is a array.
    };
  };
  return outPut // Return  the new array
  };
  console.log(removeDupes(["1", "2","1", "4", "a", "a", "4", "2"]));
// [ '1', '2', '4', 'a' ]
```

Then, write a function `concatAndRemoveDupes` that combines two arrays and removes any duplicates.

```js
const removeDupes = (arr) => {
    let outPut = [];
    let obj = {};
    for (let i = 0; i < arr.length; i++){
      if (!obj[arr[i]]){
        obj[arr[i]] = 1;
        outPut.push(arr[i]);
    };
  };
  return outPut
  };

function concatAndRemoveDupes(arr1, arr2){
  let arr3 = [...arr1, ...arr2];
  return removeDupes(arr3)
}
console.log(concatAndRemoveDupes([1,2,3], [3,4,5,6]));
//[ 1, 2, 3, 4, 5, 6 ] concat
```

  _Hint:_ Use the array method `includes`, an object, or a Set. Or the spread operator instead of concat.  

4. Given a list of grades, we can get the median grade by sorting the list and taking the middle element, or the average of the two middle elements.
Create the functions `sort` and `middleElement`, and then use them to create the functions `median`.

let grades = [91, 85, 100, 92, 88];

console.log(median(grades)); // Should log 91

```js
const sorted = arr => arr.sort((a,b) => a - b);
// b - a => descendiente
// a - b => aascendiente
const midElem = arr => {
  let middle = Math.floor(arr.length / 2);
    return [arr.length % 2] ? (arr[middle]) : (arr[middle] + arr[middle -1])/2;
}// length = odd ? arr[middle]:(arr[middle]+arr[middle -1])/2 ;
console.log(midElem([4, 8, 12, 18]));

let grades = [91, 85, 100, 92, 88];
const median = grades => midElem(sorted(grades));
console.log(median(grades));

```

5. Write a function called `repeat` that takes in a string and numberOfTimes. The function should log to the screen the string however
many times as numberOfTimes. If the user does not enter a numberOfTimes it should default to 2.

```js
const repeat = (str, numTimes = 2){
  for(let i = 1; i = numTimes; i++){
    console.log(str);
  }
}
repeat("a",3)
```

6. Using the spread operator, write a function that can take any number of arguments and return the sum of all of them.

```js
const getSum = (...args) => {
  let sum = 0;
  for (let i = 0; i < args.length; i++){
    sum += args[i];
  };
   return sum;
};
console.log(getSum(1,2,3,4));
```

7. Write a function called `adder` takes in one number and returns a function that will add that number with another number.
Using `adder` create an `add5` and an `add9` function. Hint: Closures!

```js
const adder = (...arg) => arg[0] += arg[1];
console.log(adder(1,2));

const add5 = a => adder(a, 5);
console.log(add5(2));

const add9 = b => adder(b, 9)
console.log(add9(2));
```

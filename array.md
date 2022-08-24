# JavaScript Arrays

An array is an object that can store multiple values at once.

 For example,

 ```JavaScript
 const words = ['hello', 'world', 'welcome'];
 ```

 Here, words is an array. The array is storing 3 values.

 ___

 ## Create an Array

 You can create an array using two ways:

 1. __Using an array literal__

    The easiest way to create an array is by using an array literal []. For example,

    ```JavaScript
    const array1 = ["eat", "sleep"];
    ```

2. __Using the new keyword__

    You can also create an array using JavaScript's new keyword.
    ```JavaScript
    const array2 = new Array("eat", "sleep");
    ```

    In both of the above examples, we have created an array having two elements.

    >Note: It is recommended to use array literal to create an array.

Here are more examples of arrays:

```JavaScript
// empty array
const myList = [ ];

// array of numbers
const numberArray = [ 2, 4, 6, 8];

// array of strings
const stringArray = [ 'eat', 'work', 'sleep'];

// array with mixed data types
const newData = ['work', 'exercise', 1, true];
```

You can also store arrays, functions and other objects inside an array. For example,

```JavaScript
const newData = [
    {'task1': 'exercise'},
    [1, 2 ,3],
    function hello() { console.log('hello')}
];
```

## Access Elements of an Array

You can access elements of an array using indices (0, 1, 2 …). For example,

```JavaScript
const myArray = ['h', 'e', 'l', 'l', 'o'];

// first element
console.log(myArray[0]);  // "h"

// second element
console.log(myArray[1]); // "e"
```

> Note: Array's index starts with 0, not 1.

## Add an Element to an Array

You can use the built-in method push() and unshift() to add elements to an array.

The push() method adds an element at the end of the array. For example,

```JavaScript
let dailyActivities = ['eat', 'sleep'];

// add an element at the end
dailyActivities.push('exercise');

console.log(dailyActivities); //  ['eat', 'sleep', 'exercise']
```

The unshift() method adds an element at the beginning of the array. For example,

```JavaScript
let dailyActivities = ['eat', 'sleep'];

//add an element at the start
dailyActivities.unshift('work'); 

console.log(dailyActivities); // ['work', 'eat', 'sleep']
```

## Change the Elements of an Array

You can also add elements or change the elements by accessing the index value.

```JavaScript
let dailyActivities = [ 'eat', 'sleep'];

// this will add the new element 'exercise' at the 2 index
dailyActivities[2] = 'exercise';

console.log(dailyActivities); // ['eat', 'sleep', 'exercise']
```

Suppose, an array has two elements. If you try to add an element at index 3 (fourth element), the third element will be undefined. For example,

```JavaScript
let dailyActivities = [ 'eat', 'sleep'];

// this will add the new element 'exercise' at the 3 index
dailyActivities[3] = 'exercise';

console.log(dailyActivities); // ["eat", "sleep", undefined, "exercise"]
```

Basically, if you try to add elements to high indices, the indices in between will have undefined value.

## Remove an Element from an Array

You can use the pop() method to remove the last element from an array. The pop() method also returns the returned value. For example,

```JavaScript
let dailyActivities = ['work', 'eat', 'sleep', 'exercise'];

// remove the last element
dailyActivities.pop();
console.log(dailyActivities); // ['work', 'eat', 'sleep']

// remove the last element from ['work', 'eat', 'sleep']
const removedElement = dailyActivities.pop();

//get removed element
console.log(removedElement); // 'sleep'
console.log(dailyActivities);  // ['work', 'eat']
```
If you need to remove the first element, you can use the shift() method. The shift() method removes the first element and also returns the removed element. For example,

```JavaScript
let dailyActivities = ['work', 'eat', 'sleep'];

// remove the first element
dailyActivities.shift();

console.log(dailyActivities); // ['eat', 'sleep']
```
## Array length

You can find the length of an element (the number of elements in an array) using the length property. For example,

```JavaScript
const dailyActivities = [ 'eat', 'sleep'];

// this gives the total number of elements in an array
console.log(dailyActivities.length); // 2
```

## Array reverse()

The reverse() method returns the array in reverse order.

Example

```JavaScript
let numbers = [1, 2, 3, 4, 5];

// reversing the numbers array
let reversedArray = numbers.reverse();

console.log(reversedArray);

// Output: [ 5, 4, 3, 2, 1 ]
```
> Note: The reverse() method reverses the order of elements in place, it means the method changes the original array.

__Example 1: Using reverse() Method__
```JavaScript
let languages = ["JavaScript", "Python", "C++", "Java", "Lua"];

// reversing the order of languages array
let reversedArray = languages.reverse();

console.log("Reversed Array: ", reversedArray);

// modifies the original array
console.log("Original Array: ", languages);
```

Output

```JavaScript
Reversed Array: [ 'Lua', 'Java', 'C++', 'Python', 'JavaScript' ]
Original Array: [ 'Lua', 'Java', 'C++', 'Python', 'JavaScript' ]
```

In the above example, we have used the reverse() method to reverse the languages array.

languages.reverse() reverses the order of each element in the array and returns the reversed array.

Since the method modifies the original array, both languages and reversedArray hold the same value.

__Example 2: reverse() Method with Spread Operator__

In Example 1, we saw how the reverse() method modifies the original array.

But if we use the spread operator(...) in the array along with the reverse() method, it does not modify the original array. For example:

```JavaScript
let languages = ["JavaScript", "Python", "C++", "Java", "Lua"];

// using spread operator to reverse the array
let reversedArray = [...languages].reverse();

console.log("Reversed Array:", reversedArray);

// modifies the original array
console.log("Original Array:", languages);
```
Output

```JavaScript
Reversed Array: [ 'Lua', 'Java', 'C++', 'Python', 'JavaScript' ]
Original Array: [ 'JavaScript', 'Python', 'C++', 'Java', 'Lua' ]
```
## Array sort()

The sort() method sorts the items of an array in a specific order (ascending or descending).

Example

```JavaScript
let city = ["California", "Barcelona", "Paris", "Kathmandu"];

// sort the city array in ascending order
let sortedArray = city.sort();
console.log(sortedArray);

// Output: [ 'Barcelona', 'California', 'Kathmandu', 'Paris' ]
```

__sort() Parameters__

The sort() method takes in:

compareFunction (optional) - It is used to define a custom sort order.

__sort() Return Value__

Returns the array after sorting the elements of the array in place (meaning that it changes the original array and no copy is made).

__Example 1: Sorting the Elements of an Array__

When compareFunction is not passed,

- All non-undefined array elements are first converted to strings.

- These strings are then compared using their UTF-16 code point value.

- The sorting is done in ascending order.

- All undefined elements are sorted to the end of the array.

```JavaScript
// sorting an array of strings
var names = ["Adam", "Jeffrey", "Fabiano", "Danil", "Ben"];

// returns the sorted array
console.log(names.sort());

// modifies the array in place
console.log(names);

var priceList = [1000, 50, 2, 7, 14];
priceList.sort();

// Number is converted to string and sorted
console.log(priceList)
```
Output

```JavaScript
[ 'Adam', 'Ben', 'Danil', 'Fabiano', 'Jeffrey' ]
[ 'Adam', 'Ben', 'Danil', 'Fabiano', 'Jeffrey' ]
[ 1000, 14, 2, 50, 7 ]
```

Here, we can see that the names array is sorted in ascending order of the string. For example, Adam comes before Danil because "A" comes before "D".

Since all non-undefined elements are converted to strings before sorting them, the Number data types are sorted in that order.

Here, we can see that even though 1000 is greater than 50 numerically, it comes at the beginning of the sorted list. It is because "1" < "5".

__Example 2: Sorting using Custom Function__

When compareFunction is passed,

- All non-undefined array elements are sorted according to the return value of compareFunction.

- All undefined elements are sorted to the end of the array and compareFunction is not called for them.

Suppose we want to sort the above names array such that the longest name comes last, rather than sorting it alphabetically. We can do it in the following way:

```JavaScript
// custom sorting an array of strings
var names = ["Adam", "Jeffrey", "Fabiano", "Danil", "Ben"];

function len_compare(a, b){
    return a.length - b.length;
}

// sort according to string length
names.sort(len_compare);

console.log(names);
```

Outpur

```JavaScript
[ 'Ben', 'Adam', 'Danil', 'Jeffrey', 'Fabiano' ]
```
Here, the sorting is based on the logic a.length - b.length. It basically means that the item with shorter length will appear at the beginning of the Array.

__Example 3: Sorting Numbers Numerically__

Since all non-undefined elements are converted to strings before sorting them, we cannot sort numbers using their numeric value by default.

Let's see how we can implement this using a custom function.

```JavaScript
// numeric sorting

// define array
var priceList = [1000, 50, 2, 7, 14];

// sort() using function expression
// ascending order
priceList.sort(function (a, b) {
  return a - b;
});

// Output: Ascending - 2,7,14,50,1000
console.log("Ascending - " + priceList);

// sort() using arrow function expression
// descending order
priceList.sort((a, b) => b - a);

// Output: Descending - 1000,50,14,7,2
console.log("Descending - " + priceList);
```

Outpur

```JavaScript
Ascending - 2,7,14,50,1000
Descending - 1000,50,14,7,2
```

## Array fill()
The fill() method returns an array by filling all elements with a specified value.

Example

```JavaScript
// defining an array 
var fruits = ['Apple', 'Banana', 'Grape'];

// filling every element of the array with 'Cherry'
fruits.fill("Cherry");

console.log(fruits);

// Output: 
// [ 'Cherry', 'Cherry', 'Cherry' ]
```
__fill() Parameters__

The fill() method can take 3 parameters:

- value - Value to fill the array with.
- start (optional) - Start index (default is 0).
- end (optional) - End index (default is Array.length), which is always excluded.

__fill() Return Value__

Returns the modified array, filled with value from start to end.

> Notes:
 If start or end is negative, indexes are counted backwards.
 Since fill() is a mutator method, it changes the array itself (not a copy) and returns it.

```JavaScript
var prices = [651, 41, 4, 3, 6];

// filling every element of the array with '5'
new_prices = prices.fill(5);

console.log(prices);

console.log(new_prices); 
```

Output

```JavaScript
[ 5, 5, 5, 5, 5 ]
[ 5, 5, 5, 5, 5 ]
```
In the above example, we have used the fill() method to fill every element of the prices array with 5.

We have passed 5 as a fill value in the method and then assigned the return value to new_prices.

As the method is mutator, prices.fill(5) modifies the original array and hence both prices and new_prices hold the same value.

## Array join()

The join() method returns a new string by concatenating all of the elements in an array, separated by a specified separator.

__join() Parameters__

The join() method takes in:

- separator (optional) - A string to separate each pair of adjacent elements of the array. By default, it is comma ,.

__join() Return Value

- Returns a String with all the array elements joined by separator.
> Notes: 
>- The join() method does not change the original array.
>- Elements like undefined, null, or empty array have an empty string representation. 



```JavaScript
var info = ["Terence", 28, "Kathmandu"];

var info_str = info.join(" | ");

// join() does not change the original array
console.log(info); // [ 'Terence', 28, 'Kathmandu' ]

// join() returns the string by joining with separator
console.log(info_str); // Terence | 28 | Kathmandu

// empty argument = no separator
var collection = [3, ".", 1, 4, 1, 5, 9, 2];
console.log(collection.join("")); // 3.141592

var random = [44, "abc", undefined];
console.log(random.join(" and ")); // 44 and abc and
```

## Array toString()

The toString() method returns a string formed by the elements of the given array.

__toString() Return Value__

Returns a string representing the values of the array separated by a comma

>Notes:
>- The toString() method does not change the original array.
>- Elements like undefined, null, or empty array, have an empty string representation.


```JavaScript
let info = ["Terence", 28, "Kathmandu"];

// returns the string representation of the info array 
let info_str = info.toString();

console.log(info_str); 

// toString() does not change the original array
console.log(info); 
```

```JavaScript
Terence,28,Kathmandu
[ 'Terence', 28, 'Kathmandu'] 
```
In the above example, we have used the toString() method to convert all the elements of the info array into a string.

info.toString() returns the string representation of info which is Terence,28,Kathmandu.

Since the method does not change the original array, the info array holds the same original value.

## Array concat()

The concat() method returns a new array by merging two or more values/arrays.

__concat() Return Value__

Returns a newly created array after merging all arrays/values passed in the argument.

The concat() method first creates a new array with the elements of the object on which the method is called. It then sequentially adds arguments or the elements of arguments (for arrays).

```JavaScript
var languages1 = ["JavaScript", "Python", "Java"];
var languages2 = ["C", "C++"];

// concatenating two arrays
var new_arr = languages1.concat(languages2);
console.log(new_arr); // [ 'JavaScript', 'Python', 'Java', 'C', 'C++' ]

// concatenating a value and array
var new_arr1 = languages2.concat("Lua", languages1);
console.log(new_arr1); // [ 'C', 'C++', 'Lua', 'JavaScript', 'Python', 'Java' ]
```

## Array splice()

The splice() method returns an array by changing (adding/removing) its elements in place.

__splice() Parameters__

The splice() method takes in:

- start - The index from where the array is changed.
- deleteCount (optional) - The number of items to remove from start.
- item1, ..., itemN (optional) - The elements to add to the start index. If not specified, splice() will only remove elements from the array.

__splice() Return Value__

Returns an array containing the deleted elements.

>Note: The splice() method changes the original array.

```JavaScript
let languages = ["JavaScript", "Python", "Java", "Lua"];

// replacing "Java" & "Lua" with "C" & "C++"
let removed = languages.splice(2, 2, "C", "C++");
console.log(removed); // [ 'Java', 'Lua' ]
console.log(languages); // [ 'JavaScript', 'Python', 'C', 'C++' ]

// adding elements without deleting existing elements
let removed1 = languages.splice(1, 0, "Java", "Lua");
console.log(removed1); // []
console.log(languages); // [ 'JavaScript', 'Java', 'Lua', 'Python', 'C', 'C++' ]

// removing 3 elements
let removed2 = languages.splice(2, 3);
console.log(removed2); // [ 'Lua', 'Python', 'C' ]
console.log(languages); // [ 'JavaScript', 'Java', 'C++' ]
```
## Array slice()

The slice() method returns a shallow copy of a portion of an array into a new array object.

__slice() Parameters__

The slice() method takes in:

- start (optional) - Starting index of the selection. If not provided, the selection starts at start 0.
- end (optional) - Ending index of the selection (exclusive). If not provided, the selection ends at the index of the last element.

Returns a new array containing the extracted elements.

```JavaScript
let languages = ["JavaScript", "Python", "C", "C++", "Java"];

// slicing the array (from start to end)
let new_arr = languages.slice();
console.log(new_arr); // [ 'JavaScript', 'Python', 'C', 'C++', 'Java' ]

// slicing from the third element
let new_arr1 = languages.slice(2);
console.log(new_arr1); // [ 'C', 'C++', 'Java' ]

// slicing from the second element to fourth element
let new_arr2 = languages.slice(1, 4);
console.log(new_arr2); // [ 'Python', 'C', 'C++' ]
```
__slice() With Negative index__

In JavaScript, you can also use negative start and end indices. The index of the last element is -1, the index of the second last element is -2, and so on.

```JavaScript
const languages = ["JavaScript", "Python", "C", "C++", "Java"];

// slicing the array from start to second-to-last
let new_arr = languages.slice(0, -1);
console.log(new_arr); // [ 'JavaScript', 'Python', 'C', 'C++' ]

// slicing the array from third-to-last
let new_arr1 = languages.slice(-3);
console.log(new_arr1); // [ 'C', 'C++', 'Java' ]
```

## Array lastIndexOf()

The lastIndexOf() method returns the index of the last occurrence of a specified element in the array.

Example
```JavaScript
let priceList = [10, 8, 2, 31, 10, 31, 65];

// finding the index of the last occurence of 31
let lastIndex = priceList.lastIndexOf(31);

console.log(lastIndex); 

// Output: 5
```

## Array indexOf()

The indexOf() method returns the first index of occurance of an array element, or -1 if it is not found.

Example

```JavaScript
let languages = ["Java", "JavaScript", "Python", "JavaScript"];

// get the index of the first occurrence of "JavaScript"
let index = languages.indexOf("JavaScript");
console.log(index);

// Output: 1
```
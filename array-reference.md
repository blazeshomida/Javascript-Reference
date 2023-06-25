# Arrays<!-- omit in toc -->

- [**Constructor**](#constructor)
  - [**Array()**](#array)
- [**Properties**](#properties)
  - [**Array\[@@species\]**](#arrayspecies)
  - [**Array.prototype\[@@unscopables\]**](#arrayprototypeunscopables)
  - [**Array.length**](#arraylength)
- [**Methods**](#methods)
  - [**at()**](#at)
  - [**concat()**](#concat)
  - [**copyWithin()**](#copywithin)
  - [**entries()**](#entries)
  - [**every()**](#every)
  - [**fill()**](#fill)
  - [**filter()**](#filter)
  - [**find()**](#find)
  - [**findIndex()**](#findindex)
  - [**findLast()**](#findlast)
  - [**findLastIndex()**](#findlastindex)
  - [**flat()**](#flat)
  - [**flatMap()**](#flatmap)
  - [**forEach()**](#foreach)
  - [**from()**](#from)
  - [**fromAsync()**](#fromasync)
  - [**includes()**](#includes)
  - [**indexOf()**](#indexof)
  - [**isArray()**](#isarray)
  - [**join()**](#join)
  - [**keys()**](#keys)
  - [**lastIndexOf()**](#lastindexof)
  - [**map()**](#map)
  - [**of()**](#of)
  - [**pop()**](#pop)
  - [**push()**](#push)
  - [**reduce()**](#reduce)
  - [**reduceRight()**](#reduceright)
  - [**reverse()**](#reverse)
  - [**shift()**](#shift)
  - [**slice()**](#slice)
  - [**some()**](#some)
  - [**sort()**](#sort)
  - [**splice()**](#splice)
  - [**toLocaleString()**](#tolocalestring)
  - [**toReversed()**](#toreversed)
  - [**toSorted()**](#tosorted)
  - [**toSpliced()**](#tospliced)
  - [**toString()**](#tostring)
  - [**unshift()**](#unshift)

## **Constructor**

### **Array()**

---

- **Syntax**: `new Array(element0, element1[, ...[, elementN]])` or `new Array(arrayLength)`
- **Description**: Creates a new Array object. When called with multiple arguments, creates a new array with the arguments as elements. When called with a single number argument, creates a new array of the specified length (filled with `undefined`).
- **Example**:

  ```javascript
  const array1 = new Array(5);
  console.log(array1.length);
  // expected output: 5

  const array2 = new Array("a", "b", "c");
  console.log(array2);
  // expected output: Array ["a", "b", "c"]
  ```

[Back to Top](#arrays)

## **Properties**

### **Array[@@species]**

---

- **Syntax**: `Array[Symbol.species]`
- **Description**: The Array[@@species] accessor property returns the default constructor for Array objects. Subclass constructors may override it to change the constructor assignment.
- **Example**:
  ```javascript
  console.log(Array[Symbol.species]); // Function: Array
  ```

[Back to Top](#arrays)

### **Array.prototype[@@unscopables]**

---

- **Syntax**: `Array.prototype[Symbol.unscopables]`
- **Description**: The Array.prototype[@@unscopables] symbol contains property names to exclude from a with statement binding scope.
- **Example**:

  ```javascript
  console.log(Array.prototype[Symbol.unscopables]);
  // expected output: { copyWithin: true, entries: true, fill: true, find: true, findIndex: true, flat: true, flatMap: true, includes: true, keys: true, values: true }
  ```

[Back to Top](#arrays)

### **Array.length**

---

- **Syntax**: `array.length`
- **Description**: Reflects the number of elements in an array.
- **Example**:
  ```javascript
  const array = ["a", "b", "c"];
  console.log(array.length);
  // expected output: 3
  ```

[Back to Top](#arrays)

## **Methods**

### **at()**

---

- **Syntax**: `array.at(index)`
- **Description**: This method returns the element at the specified index, allowing for positive and negative integers. Negative integers count back from the last item in the array.
- **Mutability**: Does not mutate the original array
- **Return Value**: Element at the given index
- **Example**:
  ```javascript
  const array1 = [5, 12, 8, 130, 44];
  console.log(array1.at(-1));
  // expected output: 44
  ```

[Back to Top](#arrays)

### **concat()**

---

- **Syntax**: `array1.concat(array2)`
- **Description**: The concat() method is used to merge two or more arrays. This method does not change the existing arrays but instead returns a new array.
- **Mutability**: Does not mutate the original array
- **Return Value**: New array
- **Example**:

  ```javascript
  const array1 = ["a", "b", "c"];
  const array2 = ["d", "e", "f"];
  const array3 = array1.concat(array2);

  console.log(array3);
  // expected output: Array ["a", "b", "c", "d", "e", "f"]
  ```

[Back to Top](#arrays)

### **copyWithin()**

---

- **Syntax**: `arr.copyWithin(target[, start[, end]])`
- **Description**: The copyWithin() method shallow copies part of an array to another location in the same array and returns it without modifying its size.
- **Mutability**: Mutates the original array
- **Return Value**: The modified array
- **Example**:

  ```javascript
  const array1 = ["a", "b", "c", "d", "e"];

  console.log(array1.copyWithin(0, 3, 4));
  // expected output: Array ["d", "b", "c", "d", "e"]
  ```

[Back to Top](#arrays)

### **entries()**

---

- **Syntax**: `array.entries()`
- **Description**: Returns a new Array Iterator object that contains the key/value pairs for each index in the array.
- **Mutability**: Does not mutate the original array
- **Return Value**: New Array Iterator object
- **Example**:

  ```javascript
  const array1 = ["a", "b", "c"];
  const iterator1 = array1.entries();

  console.log(iterator1.next().value);
  // expected output: Array [0, "a"]
  ```

[Back to Top](#arrays)

### **every()**

---

- **Syntax**: `arr.every(callback(element[, index[, array]])[, thisArg])`
- **Description**: Tests whether all elements in the array pass the test implemented by the provided function. It returns a Boolean value.
- **Mutability**: Does not mutate the original array
- **Return Value**: Boolean
- **Example**:

  ```javascript
  function isBelowThreshold(currentValue) {
  	return currentValue < 40;
  }

  const array1 = [1, 30, 39, 29, 10, 13];

  console.log(array1.every(isBelowThreshold));
  // expected output: true
  ```

[Back to Top](#arrays)

### **fill()**

---

- **Syntax**: `arr.fill(value[, start[, end]])`
- **Description**: Changes all elements in an array to a static value, from a start index (default 0) to an end index (default array.length). It returns the modified array.
- **Mutability**: Mutates the original array
- **Return Value**: The modified array
- **Example**:
  ```javascript
  console.log([1, 2, 3].fill(4));
  // expected output: [4, 4, 4]
  ```

[Back to Top](#arrays)

### **filter()**

---

- **Syntax**: `arr.filter(callback(element[, index[, array]])[, thisArg])`
- **Description**: The filter() method creates a new array with all elements that pass the test implemented by the provided function.
- **Mutability**: Does not mutate the original array
- **Return Value**: A new array with the elements that pass the test. If no elements pass the test, an empty array will be returned.
- **Example**:

  ```javascript
  const words = [
  	"spray",
  	"limit",
  	"elite",
  	"exuberant",
  	"destruction",
  	"present",
  ];

  const result = words.filter((word) => word.length > 6);

  console.log(result);
  // expected output: Array ["exuberant", "destruction", "present"]
  ```

[Back to Top](#arrays)

### **find()**

---

- **Syntax**: `arr.find(callback( element[, index[, array]] )[, thisArg])`
- **Description**: The find() method returns the value of the first element in the provided array that satisfies the provided testing function.
- **Mutability**: Does not mutate the original array
- **Return Value**: The first element in the array that passes the test; otherwise, undefined.
- **Example**:

  ```javascript
  const array1 = [5, 12, 8, 130, 44];

  const found = array1.find((element) => element > 10);

  console.log(found);
  // expected output: 12
  ```

[Back to Top](#arrays)

### **findIndex()**

---

- **Syntax**: `arr.findIndex(callback( element[, index[, array]] )[, thisArg])`
- **Description**: The findIndex() method returns the index of the first element in the array that satisfies the provided testing function. Otherwise, it returns -1, indicating that no element passed the test.
- **Mutability**: Does not mutate the original array
- **Return Value**: The index of the first element in the array that passes the test; otherwise, -1.
- **Example**:

  ```javascript
  const array1 = [5, 12, 8, 130, 44];

  const isLargeNumber = (element) => element > 13;

  console.log(array1.findIndex(isLargeNumber));
  // expected output: 3
  ```

[Back to Top](#arrays)

### **findLast()**

---

- **Syntax**: `arr.findLast(callback( element[, index[, array]] )[, thisArg])`
- **Description**: The findLast() method returns the value of the last element in the array where predicate is true, and undefined otherwise.
- **Mutability**: Does not mutate the original array
- **Return Value**: The last element in the array that satisfies the provided testing function. If no values satisfy the testing function, undefined is returned.
- **Example**:

  ```javascript
  const array1 = [5, 12, 8, 130, 44];

  const found = array1.findLast((element) => element > 10);

  console.log(found);
  // expected output: 44
  ```

[Back to Top](#arrays)

### **findLastIndex()**

---

- **Syntax**: `arr.findLastIndex(callback( element[, index[, array]] )[, thisArg])`
- **Description**: The findLastIndex() method returns the index of the last element in the array where predicate is true, and -1 otherwise.
- **Mutability**: Does not mutate the original array
- **Return Value**: The index of the last element in the array that passes the test; otherwise, -1.
- **Example**:

  ```javascript
  const array1 = [5, 12, 8, 130, 44];

  const isLargeNumber = (element) => element > 13;

  console.log(array1.findLastIndex(isLargeNumber));
  // expected output: 4
  ```

[Back to Top](#arrays)

### **flat()**

---

- **Syntax**: `arr.flat([depth])`
- **Description**: The flat() method creates a new array with all sub-array elements concatenated into it recursively up to the specified depth.
- **Mutability**: Does not mutate the original array
- **Return Value**: A new array with the sub-array elements concatenated into it.
- **Example**:

  ```javascript
  const arr1 = [0, 1, 2, [3, 4]];

  console.log(arr1.flat());
  // expected output: [0, 1, 2, 3, 4]
  ```

[Back to Top](#arrays)

### **flatMap()**

---

- **Syntax**: `arr.flatMap(callback(currentValue[, index[, array]])[, thisArg])`
- **Description**: The flatMap() method first maps each element using a mapping function, then flattens the result into a new array.
- **Mutability**: Does not mutate the original array
- **Return Value**: A new array with each element being the result of the callback function and flattened to a depth of 1.
- **Example**:

  ```javascript
  const arr1 = [1, 2, 3, 4];

  console.log(arr1.flatMap((x) => [x * 2]));
  // expected output: [2, 4, 6, 8]
  ```

[Back to Top](#arrays)

### **forEach()**

---

- **Syntax**: `arr.forEach(callback(currentValue [, index [, array]])[, thisArg])`
- **Description**: The forEach() method executes a provided function once for each array element.
- **Mutability**: Does not mutate the original array
- **Return Value**: undefined
- **Example**:

  ```javascript
  const array1 = ["a", "b", "c"];

  array1.forEach((element) => console.log(element));
  // expected output: "a"
  // expected output: "b"
  // expected output: "c"
  ```

[Back to Top](#arrays)

### **from()**

---

- **Syntax**: `Array.from(arrayLike[, mapFn[, thisArg]])`
- **Description**: The Array.from() static method creates a new, shallow-copied Array instance from an array-like or iterable object.
- **Mutability**: Does not mutate the original array-like or iterable object
- **Return Value**: A new Array instance
- **Example**:
  ```javascript
  console.log(Array.from("foo"));
  // expected output: Array ["f", "o", "o"]
  ```

[Back to Top](#arrays)

### **fromAsync()**

---

- **Syntax**: `Array.fromAsync(asyncIterable)`
- **Description**: The Array.fromAsync() static method creates a new Array instance from an asynchronous or synchronous iterable object.
- **Mutability**: Does not mutate the original iterable object
- **Return Value**: A new Promise that resolves with an Array instance
- **Example**:

  ```javascript
  async function* gen() {
  	yield* [1, 2, 3, 4];
  }

  Array.fromAsync(gen()).then(console.log);
  // expected output: [1, 2, 3, 4]
  ```

[Back to Top](#arrays)

### **includes()**

---

- **Syntax**: `arr.includes(valueToFind[, fromIndex])`
- **Description**: The includes() method determines whether an array includes a certain value among its entries, returning true or false as appropriate.
- **Mutability**: Does not mutate the original array
- **Return Value**: Boolean
- **Example**:

  ```javascript
  const array1 = [1, 2, 3];

  console.log(array1.includes(2));
  // expected output: true
  ```

[Back to Top](#arrays)

### **indexOf()**

---

- **Syntax**: `arr.indexOf(searchElement[, fromIndex])`
- **Description**: The indexOf() method returns the first index at which a given element can be found in the array, or -1 if it is not present.
- **Mutability**: Does not mutate the original array
- **Return Value**: The first index of the element in the array; -1 if not found.
- **Example**:

  ```javascript
  const beasts = ["ant", "bison", "camel", "duck", "bison"];

  console.log(beasts.indexOf("bison"));
  // expected output: 1
  ```

[Back to Top](#arrays)

### **isArray()**

---

- **Syntax**: `Array.isArray(obj)`
- **Description**: The Array.isArray() method determines whether the passed value is an Array.
- **Mutability**: Does not mutate the original object
- **Return Value**: Boolean
- **Example**:
  ```javascript
  // all following calls return true
  console.log(Array.isArray([]));
  console.log(Array.isArray(["a", "b", "c"]));
  // all following calls return false
  console.log(Array.isArray({}));
  console.log(Array.isArray(null));
  console.log(Array.isArray(undefined));
  console.log(Array.isArray(17));
  console.log(Array.isArray("Array"));
  console.log(Array.isArray(true));
  console.log(Array.isArray(false));
  console.log(Array.isArray({ __proto__: Array.prototype }));
  ```

[Back to Top](#arrays)

### **join()**

---

- **Syntax**: `arr.join([separator])`
- **Description**: The join() method creates and returns a new string by concatenating all of the elements in an array (or an array-like object), separated by commas or a specified separator string.
- **Mutability**: Does not mutate the original array
- **Return Value**: A string with all array elements joined. If arr.length is 0, the empty string is returned.
- **Example**:

  ```javascript
  const elements = ["Fire", "Air", "Water"];

  console.log(elements.join());
  // expected output: "Fire,Air,Water"
  ```

[Back to Top](#arrays)

### **keys()**

---

- **Syntax**: `arr.keys()`
- **Description**: The keys() method returns a new Array Iterator object that contains the keys for each index in the array.
- **Mutability**: Does not mutate the original array
- **Return Value**: A new Array Iterator object
- **Example**:

  ```javascript
  const array1 = ["a", "b", "c"];
  const iterator = array1.keys();

  for (const key of iterator) {
  	console.log(key);
  }
  // expected output: 0
  // expected output: 1
  // expected output: 2
  ```

[Back to Top](#arrays)

### **lastIndexOf()**

---

- **Syntax**: `arr.lastIndexOf(searchElement[, fromIndex])`
- **Description**: The lastIndexOf() method returns the last index at which a certain element can be found in the array, or -1 if the element is not found. The array is searched backwards, starting at fromIndex.
- **Mutability**: Does not mutate the original array
- **Return Value**: The last index of the element in the array; -1 if not found.
- **Example**:

  ```javascript
  const animals = ["Dodo", "Tiger", "Penguin", "Dodo"];

  console.log(animals.lastIndexOf("Dodo"));
  // expected output: 3
  ```

[Back to Top](#arrays)

### **map()**

---

- **Syntax**: `arr.map(callback(currentValue[, index[, array]])[, thisArg])`
- **Description**: The map() method creates a new array populated with the results of calling a provided function on every element in the calling array.
- **Mutability**: Does not mutate the original array
- **Return Value**: A new array with each element being the result of the callback function.
- **Example**:

  ```javascript
  const array1 = [1, 4, 9, 16];

  const map1 = array1.map((x) => x * 2);

  console.log(map1);
  // expected output: Array [2, 8, 18, 32]
  ```

[Back to Top](#arrays)

### **of()**

---

- **Syntax**: `Array.of(element0[, element1[, ...[, elementN]]])`
- **Description**: The Array.of() method creates a new Array instance from a variable number of arguments, regardless of number or type of the arguments.
- **Mutability**: Does not mutate the original arguments
- **Return Value**: A new Array instance.
- **Example**:
  ```javascript
  console.log(Array.of(1)); // [1]
  console.log(Array.of(1, 2, 3)); // [1, 2, 3]
  console.log(Array.of(undefined)); // [undefined]
  ```

[Back to Top](#arrays)

### **pop()**

---

- **Syntax**: `arr.pop()`
- **Description**: The pop() method removes the last element from an array and returns that element. This method changes the length of the array.
- **Mutability**: Mutates the original array
- **Return Value**: The removed element from the array; undefined if the array is empty.
- **Example**:

  ```javascript
  const plants = ["broccoli", "cauliflower", "cabbage", "kale", "tomato"];

  console.log(plants.pop());
  // expected output: "tomato"
  ```

[Back to Top](#arrays)

### **push()**

---

- **Syntax**: `arr.push(element1[, ...[, elementN]])`
- **Description**: The push() method adds one or more elements to the end of an array and returns the new length of the array.
- **Mutability**: Mutates the original array
- **Return Value**: The new length property of the object upon which the method was called.
- **Example**:

  ```javascript
  const animals = ["pigs", "goats", "sheep"];

  const count = animals.push("cows");
  console.log(count);
  // expected output: 4
  console.log(animals);
  // expected output: Array ["pigs", "goats", "sheep", "cows"]
  ```

[Back to Top](#arrays)

### **reduce()**

---

- **Syntax**: `arr.reduce(callback( accumulator, currentValue[, index[, array]] )[, initialValue])`
- **Description**: The reduce() method executes a reducer function (that you provide) on each element of the array, resulting in a single output value.
- **Mutability**: Does not mutate the original array
- **Return Value**: The single value that results from the reduction.
- **Example**:

  ```javascript
  const array1 = [1, 2, 3, 4];
  const reducer = (accumulator, currentValue) => accumulator + currentValue;

  console.log(array1.reduce(reducer));
  // expected output: 10
  ```

[Back to Top](#arrays)

### **reduceRight()**

---

- **Syntax**: `arr.reduceRight(callback( accumulator, currentValue[, index[, array]] )[, initialValue])`
- **Description**: The reduceRight() method applies a function against an accumulator and each value of the array (from right-to-left) to reduce it to a single value.
- **Mutability**: Does not mutate the original array
- **Return Value**: The single value that results from the reduction.
- **Example**:

  ```javascript
  const array1 = [
  	[0, 1],
  	[2, 3],
  	[4, 5],
  ].reduceRight((accumulator, currentValue) =>
  	accumulator.concat(currentValue)
  );

  console.log(array1);
  // expected output: Array [4, 5, 2, 3, 0, 1]
  ```

[Back to Top](#arrays)

### **reverse()**

---

- **Syntax**: `arr.reverse()`
- **Description**: The reverse() method reverses an array in place. The first array element becomes the last, and the last array element becomes the first.
- **Mutability**: Mutates the original array
- **Return Value**: The reversed array.
- **Example**:

  ```javascript
  const array1 = ["one", "two", "three"];
  console.log("array1:", array1);
  // expected output: "array1:" Array ["one", "two", "three"]

  const reversed = array1.reverse();
  console.log("reversed:", reversed);
  // expected output: "reversed:" Array ["three", "two", "one"]
  ```

[Back to Top](#arrays)

### **shift()**

---

- **Syntax**: `arr.shift()`
- **Description**: The shift() method removes the first element from an array and returns that removed element. This method changes the length of the array.
- **Mutability**: Mutates the original array
- **Return Value**: The removed element from the array; undefined if the array is empty.
- **Example**:

  ```javascript
  const array1 = [1, 2, 3];

  const firstElement = array1.shift();

  console.log(firstElement);
  // expected output: 1
  ```

[Back to Top](#arrays)

### **slice()**

---

- **Syntax**: `arr.slice([begin[, end]])`
- **Description**: The slice() method returns a shallow copy of a portion of an array into a new array object selected from start to end (end not included) where start and end represent the index of items in that array. The original array will not be modified.
- **Mutability**: Does not mutate the original array
- **Return Value**: A new array containing the extracted elements.
- **Example**:

  ```javascript
  const animals = ["ant", "bison", "camel", "duck", "elephant"];

  console.log(animals.slice(2));
  // expected output: Array ["camel", "duck", "elephant"]

  console.log(animals.slice(2, 4));
  // expected output: Array ["camel", "duck"]

  console.log(animals.slice(1, 5));
  // expected output: Array ["bison", "camel", "duck", "elephant"]
  ```

[Back to Top](#arrays)

### **some()**

---

- **Syntax**: `arr.some(callback(element[, index[, array]])[, thisArg])`
- **Description**: The some() method tests whether at least one element in the array passes the test implemented by the provided function. It returns a Boolean value.
- **Mutability**: Does not mutate the original array
- **Return Value**: Boolean
- **Example**:

  ```javascript
  const array = [1, 2, 3, 4, 5];

  const even = (element) => element % 2 === 0;

  console.log(array.some(even));
  // expected output: true
  ```

[Back to Top](#arrays)

### **sort()**

---

- **Syntax**: `arr.sort([compareFunction])`
- **Description**: The sort() method sorts the elements of an array in place and returns the sorted array. The default sort order is built upon converting the elements into strings, then comparing their sequences of UTF-16 code units values.
- **Mutability**: Mutates the original array
- **Return Value**: The sorted array.
- **Example**:

  ```javascript
  const months = ["March", "Jan", "Feb", "Dec"];
  months.sort();
  console.log(months);
  // expected output: Array ["Dec", "Feb", "Jan", "March"]

  const array1 = [1, 30, 4, 21, 100000];
  array1.sort();
  console.log(array1);
  // expected output: Array [1, 100000, 21, 30, 4]
  ```

[Back to Top](#arrays)

### **splice()**

---

- **Syntax**: `arr.splice(start[, deleteCount[, item1[, item2[, ...]]]])`
- **Description**: The splice() method changes the contents of an array by removing or replacing existing elements and/or adding new elements in place.
- **Mutability**: Mutates the original array
- **Return Value**: An array containing the deleted elements. If no elements are removed, an empty array is returned.
- **Example**:

  ```javascript
  const months = ["Jan", "March", "April", "June"];
  months.splice(1, 0, "Feb");
  console.log(months);
  // expected output: Array ["Jan", "Feb", "March", "April", "June"]

  const array1 = [1, 2, 3, 4, 5];
  const removed = array1.splice(2, 1, "a", "b");
  console.log(array1);
  // expected output: Array [1, 2, "a", "b", 4, 5]
  console.log(removed);
  // expected output: Array [3]
  ```

[Back to Top](#arrays)

### **toLocaleString()**

---

- **Syntax**: `arr.toLocaleString([locales[, options]])`
- **Description**: The toLocaleString() method returns a string representing the elements of the array. The elements are converted to strings using their toLocaleString methods and are separated by a locale-specific string (such as a comma ",").
- **Mutability**: Does not mutate the original array
- **Return Value**: A string representing the elements of the array.
- **Example**:

  ```javascript
  const array1 = [1, "a", new Date("21 Dec 1997 14:12:00 UTC")];
  const localeString = array1.toLocaleString("en", { timeZone: "UTC" });

  console.log(localeString);
  // expected output: "1,a,12/21/1997, 2:12:00 PM"
  ```

[Back to Top](#arrays)

### **toReversed()**

---

- **Syntax**: `arr.toReversed()`
- **Description**: This is a custom method that reverses the order of elements in the array and returns a new array.
- **Mutability**: Does not mutate the original array
- **Return Value**: A new array with the reversed order of elements.
- **Example**:

  ```javascript
  const array1 = [1, 2, 3, 4, 5];
  const reversedArray = array1.toReversed();

  console.log(reversedArray);
  // expected output: Array [5, 4, 3, 2, 1]
  ```

[Back to Top](#arrays)

### **toSorted()**

---

- **Syntax**: `arr.toSorted([compareFunction])`
- **Description**: This is a custom method that returns a new array with the elements sorted in ascending order. An optional compareFunction can be provided to define the sort order.
- **Mutability**: Does not mutate the original array
- **Return Value**: A new array with the sorted elements.
- **Example**:

  ```javascript
  const array1 = [3, 1, 4, 2, 5];
  const sortedArray = array1.toSorted();

  console.log(sortedArray);
  // expected output: Array [1, 2, 3, 4, 5]
  ```

[Back to Top](#arrays)

### **toSpliced()**

---

- **Syntax**: `arr.toSpliced(start[, deleteCount[, item1[, item2[, ...]]]])`
- **Description**: This is a custom method that returns a new array with the specified elements removed from the original array and optional new elements inserted at the specified position.
- **Mutability**: Does not mutate the original array
- **Return Value**: A new array with the specified elements removed or replaced.
- **Example**:

  ```javascript
  const array1 = [1, 2, 3, 4, 5];
  const splicedArray = array1.toSpliced(1, 2, "a", "b");

  console.log(splicedArray);
  // expected output: Array [1, "a", "b", 4, 5]
  ```

[Back to Top](#arrays)

### **toString()**

---

- **Syntax**: `arr.toString()`
- **Description**: The toString() method returns a string representing the specified array and its elements.
- **Mutability**: Does not mutate the original array
- **Return Value**: A string representing the array and its elements.
- **Example**:
  ```javascript
  const array1 = [1, 2, "a", "b"];
  console.log(array1.toString());
  // expected output: "1,2,a,b"
  ```

[Back to Top](#arrays)

### **unshift()**

---

- **Syntax**: `arr.unshift(element1[, ...[, elementN]])`
- **Description**: The unshift() method adds one or more elements to the beginning of an array and returns the new length of the array.
- **Mutability**: Mutates the original array
- **Return Value**: The new length property of the object upon which the method was called.
- **Example**:

  ```javascript
  const array1 = [1, 2, 3];

  console.log(array1.unshift(4, 5));
  // expected output: 5
  console.log(array1);
  // expected output: Array [4, 5, 1, 2, 3]
  ```

[Back to Top](#arrays)

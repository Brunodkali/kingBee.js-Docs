# Array and objects functions

## _deepClone(obj)

Function to perform a deep cloning of an object.

**Parameters**:
- `obj` (object) [Required]: The object to be cloned.

**Example of use**

     const originalObj = {
          name: 'John',
          age: 30,
          address: {
            city: 'New York',
            country: 'USA',
          },
    };
    
    const clonedObj = _deepClone(originalObj);
    console.log(clonedObj); // Should display an object equal to the original;

## _flatten(arr)

Function to transform a multidimensional array into a simple array.

**Parameters**:
- `arr` (array) [Required]: The Array that will be handled.

**Example of use**

    const nestedArray = [1, [2, [3, [4]], 5]];
    const flattenedArray = _flatten(nestedArray);
    console.log(flattenedArray); // It should display [1, 2, 3, 4, 5];

## _merge(...objects)

Function for merging two or more objects. It is necessary to pass more than one parameter.

**Parameters**:
- `...objects` (objects) [Required]: The objects to be merged.

**Example of use**

    const obj1 = { a: 1, b: 2 };
    const obj2 = { c: 3, d: 4 };
    const mergedObject = _merge(obj1, obj2);
    console.log(mergedObject); // It should display { a: 1, b: 2, c: 3, d: 4 };

## _findUpdateArray(array, item, update)

Searches for the `item` in the given `array`. If `update` is true and the `item` is not found, it will be added to the array. Returns `true` if the item is found (or added), otherwise `false`.

**Parameters**:
- `array` (Array) [Required]: The array to search and potentially update.
- `item` (any) [Required]: The item to look for in the array.
- `update` (boolean) [Required]: Whether to add the item to the array if not found.

**Example of use**

    _findUpdateArray(myArray, newItem, true); - for find and update;
    _findUpdateArray(myArray, newItem, false); or _findUpdateArray(myArray, newItem); - for just find; 

## _findRemoveArray(array, item)

Searches for the `item` in the given `array`. If it returns `true` it found and removed the item, if it returns `false` it did not find the item in the array

**Parameters**:
- `array` (Array) [Required]: The array to search.
- `item` (any) [Required]: The item to remove for in the array.

**Example of use**

    _findRemoveArray(myArray, itemToRemove);

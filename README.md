# kingBee.js Documentation

CDN for use a library KingBee.js - https://kingbeejs.vercel.app/bundle.js

    <script src="https://kingbeejs.vercel.app/bundle.js"></script>

## _setClass(element, className)

Adds the specified class `className` to the given `element`. Throws an error if the `element` is not a valid HTMLElement.

**Parameters**:
- `element` (HTMLElement) [Required]: The target element to add the class to.
- `className` (string) [Required]: The class name to be added to the element.

**Example of use**

    const element = _selectById(elementId);
    
    _setClass(element, 'new-class');

## _unsetClass(element, className)

Removes the specified class `className` from the given `element`. Throws an error if the `element` is not a valid HTMLElement.

**Parameters**:
- `element` (HTMLElement) [Required]: The target element to remove the class from.
- `className` (string) [Required]: The class name to be removed from the element.

**Example of use**

    const element = _selectById(elementId);
    
    _unsetClass(element, 'new-class');

## _ppGet(url)

Performs an HTTP GET request to the specified `url` and returns a Promise. Resolves with the response if successful or rejects with an error message if the request fails.

**Parameters**:
- `url` (string) [Required]: The URL to make the GET request.

**Example of use**

    const url = 'https://example.com';
    
    _ppGet(url)
        .then(response => {
            console.log('Status:', response.status);
            console.log('Response:', response.response);
        })
        .catch(error => {
            console.error(error);
        });

## _ppPost(url, data)

Performs an HTTP POST request to the specified `url` with the given `data` (in JSON format) and returns a Promise. Resolves with the response if successful or rejects with an error message if the request fails.

**Parameters**:
- `url` (string) [Required]: The URL to make the POST request.
- `data` (object) [Required]: The data to be sent in the request body.

**Example of use**

    const url = 'https://example.com';
    const data = {
        title: 'Title',
        body: 'Example of message.',
        userId: 1
    };
    
    _ppPost(url, data)
        .then(response => {
            console.log('Status:', response.status);
            console.log('Response:', response.response);
        })
        .catch(error => {
            console.error(error);
        });

## _when(element, condition, action)

Executes the `action` function when the specified `condition` function returns true for the `element`. The function checks the condition at regular intervals (100ms) until it is met or the element is no longer valid.

**Parameters**:
- `element` (HTMLElement) [Required]: The target element to wait for.
- `condition` (function) [Required]: The condition function that returns true when the desired state is achieved.
- `action` (function) [Required]: The function to be executed when the condition is met.

**Example of use**

    const element = _selectById(elementId);

    _when(element, () => _classExists(element, 'new-class'), () => {
        console.log('Exist!');
    });

## _setEvent(element, event, handler)

Adds an event `handler` to the specified `element` for the given `event`.

**Parameters**:
- `element` (HTMLElement) [Required]: The target element to attach the event handler to.
- `event` (string) [Required]: The event type (e.g., "click", "keydown", etc.).
- `handler` (function) [Required]: The function to be executed when the event is triggered.

**Example of use**

    const button = _selectById(buttonId);
  
    _setEvent(button, 'click', onClickHandler);

## _unsetEvent(element, event, handler)

Removes the event `handler` from the specified `element` for the given `event`.

**Parameters**:
- `element` (HTMLElement) [Required]: The target element to remove the event handler from.
- `event` (string) [Required]: The event type (e.g., "click", "keydown", etc.).
- `handler` (function) [Required]: The function to be removed from the event.

**Example of use**

    const button = _selectById(buttonId);
  
    _unsetEvent(button, 'click', onClickHandler);

## _getAttr(element, attributeName)

Retrieves the value of the specified attribute `attributeName` from the given `element`. Returns `null` if the element is not a valid HTMLElement or does not have the specified attribute.

**Parameters**:
- `element` (HTMLElement) [Required]: The target element to get the attribute value from.
- `attributeName` (string) [Required]: The name of the attribute to retrieve.

**Example of use**

    const link = _selectById(linkId);
  
    _getAttr(link, 'href');

## _setAttr(element, attributeName, attributeValue)

Sets the value of the specified attribute `attributeName` to `attributeValue` for the given `element`. Throws an error if the `element` is not a valid HTMLElement or does not support the setAttribute method.

**Parameters**:
- `element` (HTMLElement) [Required]: The target element to set the attribute value for.
- `attributeName` (string) [Required]: The name of the attribute to set.
- `attributeValue` (string) [Required]: The value to set for the attribute.

**Example of use**

    const input = _selectById(inputId);
  
    _setAttr(input, 'placeholder', 'newPlaceholder');

## _classExists(element, className)

Checks if the given `element` contains the specified class `className`. Returns `false` if the element is not a valid HTMLElement or does not support the classList method.

**Parameters**:
- `element` (HTMLElement) [Required]: The target element to check for the class.
- `className` (string) [Required]: The class name to check for.

**Example of use**

    const element = _selectById(elementId);
  
    _classExists(element, 'className');

## _buildElement(tagName, attributes, content, events)

Creates an HTML element with the specified `tagName`, attributes, content, and event listeners. Returns the newly created element.

**Parameters**:
- `tagName` (string) [Required]: The HTML tag name of the element to create.
- `attributes` (object) [Optional]: An object containing attribute-value pairs to set for the element.
- `content` (string or HTMLElement) [Optional]: The content to be inserted inside the element (as HTML or an HTMLElement).
- `events` (object) [Optional]: An object containing event-function pairs to add event listeners to the element.

**Example of use**

    const tagName = 'button';
    const attributes = {
        type: 'button',
        id: 'myButton',
        class: 'btn'
    };
    const content = 'Click';
    const events = {
        click: function() {
            console.log('Clicked!');
        }
    };;
  
    _buildElement(tagName, attributes, content, events);

## _formSubmit(formId, callback, controllerPath)

Adds a submit event to the form with the specified `formId`. When the form is submitted, the `callback` function is executed. It can also forward to a controller or route, which is defined by the `controllerPath` parameter.

**Parameters**:
- `formId` (string) [Required]: The ID attribute of the form element.
- `callback` (function) [Optional]: The function to be executed when the form is submitted.
- `controllerPath` (string) [Optional]: The controller or route where you will direct the send.

**Example of use**

    _formSubmit('myForm', formSubmitCallback);
    _formSubmit('myForm', formSubmitCallback, '/route/example');

## _load(url, type)

Loads a resource (e.g., a CSS or JavaScript file) from the specified `url`. The `type` parameter should be either "script" or "link". Returns a Promise that resolves when the resource is successfully loaded or rejects if it fails.

**Parameters**:
- `url` (string) [Required]: The URL of the resource to load.
- `type` (string) [Required]: The type of the resource to load ("script" or "link").

**Example of use**

    _load(scriptUrl, 'script')
        .then(() => {
            console.log('Script loaded!');
        })
        .catch((error) => {
            console.error(error);
        });

## _reset(elementId)

Resets the content of the element with the specified `elementId`. If the element is a form, it will be reset to its initial state. Otherwise, its innerHTML will be cleared.

**Parameters**:
- `elementId` (string) [Required]: The ID attribute of the element to reset.

**Example of use**

     _reset(divId); - reset div content;
     _reset(formId); - reset form content;

## _setChild(parentId, childElement)

Adds the `childElement` as a child of the element with the specified `parentId`.

**Parameters**:
- `parentId` (string) [Required]: The ID attribute of the parent element.
- `childElement` (HTMLElement) [Required]: The element to be added as a child.

**Example of use**

    _setChild(parentId, childElement);

## _unsetChild(parentId, childElement)

Removes the `childElement` from the element with the specified `parentId`.

**Parameters**:
- `parentId` (string) [Required]: The ID attribute of the parent element.
- `childElement` (HTMLElement) [Required]: The element to be removed as a child.

**Example of use**

    _unsetChild(parentId, childElement);

## _setContent(elementId, content)

Sets the content of the element with the specified `elementId`. The `content` can be either a string (to set innerHTML) or an HTMLElement (to append as a child).

**Parameters**:
- `elementId` (string) [Required]: The ID attribute of the element to set the content for.
- `content` (string or HTMLElement) [Required]: The content to be set or appended to the element.

**Example of use**

    _setContent(divId, newContent);

## _getContent(elementId, content)

Gets the content of the element with the specified `elementId` and checks if it includes the given `content`.

**Parameters**:
- `elementId` (string) [Required]: The ID attribute of the element to get the content from.
- `content` (string) [Required]: The content to check for.

**Example of use**

    _getContent(divId, 'newContent');

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

## _makeDrop(parentSelector, childSelector)

Function that takes a `parentSelector` and `childSelector` and transforms the structure into a drag and drop, the function adds the necessary events to enable the "drag and drop" functionality on the child elements inside the parent element.

**Parameters**:
- `parentSelector` (string) [Required]: The parent selector.
- `childSelector` (string) [Required]: The children selector.

**Example of use**

    _makeDrop("div", "p"); - using HTMLElement;
    _makeDrop('#dragContainer', '.draggable'); - using id and class;

## _debounce(function, delay)

Function to define delay in the execution of a function, performing the execution only once. The `delay` parameter has a default of 1000 (1 second).

**Parameters**:
- `function` (function) [Required]: The function to be performed.
- `delay` (number) [Optinal]: The expected time to run.

**Example of use**

    function sayHello() {
       console.log('Hello!');
    }
    
    const debouncedSayHello = _debounce(sayHello, 3000);
    debouncedSayHello(); // Will run console.log after 3 seconds;

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

## License

The KingBee.js library is free software *for use*. Copyright© 2023-present Bruno Duarte duartebruno581@gmail.com 

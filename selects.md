# Selectors - High and low level selectors

## _select(selector, context)

Selects elements based on the given `selector`. If the selector starts with '#', it selects by ID; otherwise, it selects elements by class or tag name. Returns a NodeList of matching elements.

**Parameters**:
- `selector` (string) [Required]: The CSS selector to search for.
- `context` (HTMLElement) [Optional]: The context in which to search for elements.

**Example of use**

    const idSelector = '#myDiv';
    const classSelector = '.my-button';
    
    _select(idSelector);
    _select(classSelector);
    
## _selectByClass(className, context)

Selects all elements with the specified `className` within the given `context` (default is `document`). Returns a NodeList of the matched elements.

**Parameters**:
- `className` (string) [Required]: The class name to search for.
- `context` (HTMLElement) [Optional]: The context in which to search for elements.

**Example of use**

    _selectByClass('my-class');

## _selectById(id)

Selects the element with the specified `id`. Returns the matched element or `null` if not found.

**Parameters**:
- `id` (string) [Required]: The id attribute of the element to search for.

**Example of use**

    _selectById('my-id');

## _selectChild(parentSelector, childSelector)

Selects the child element within the parent element based on the `parentSelector` and `childSelector` data. Returns a list of matching children, or `null` if not found.

**Parameters**:
- `parentSelector` (string) [Required]: The selector for the parent element.
- `childSelector` (string) [Required]: The selector for the child element.

**Example of use**

    _selectChild('parentSelector', 'childSelector');

## _selectByAttribute(attribute, value, context)

Selects all elements with the specified `attribute` and `value` within the given `context` (default is `document`). Returns a NodeList of the matched elements.

**Parameters**:
- `attribute` (string) [Required]: The attribute name to search for.
- `value` (string) [Required]: The value of the attribute to match.
- `context` (HTMLElement) [Optional]: The context in which to search for elements.

**Example of use**

    _selectByAttribute(attribute, value);

## _selectAll(selector, context)

Selects all elements that match the given `selector` within the given `context` (default is `document`). Returns a NodeList of the matched elements.

**Parameters**:
- `selector` (string) [Required]: The CSS selector to search for.
- `context` (HTMLElement) [Optional]: The context in which to search for elements.

**Example of use**

    const selector = '#myList li';
    
    _selectAll(selector);

## _selectFirst(selector, context)

Selects the first element that matches the given `selector` within the given `context` (default is `document`). Returns the matched element or `null` if not found.

**Parameters**:
- `selector` (string) [Required]: The CSS selector to search for.
- `context` (HTMLElement) [Optional]: The context in which to search for elements.

**Example of use**

    const selector = 'li';
    
    _selectFirst(selector);

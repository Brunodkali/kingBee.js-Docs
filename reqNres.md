# Requests and shipments

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

## _formSubmit(formId, callback, controllerPath)

Adds a submit event to the form with the specified `formId`. When the form is submitted, the `callback` function is executed. It can also forward to a controller or route, which is defined by the `controllerPath` parameter.

**Parameters**:
- `formId` (string) [Required]: The ID attribute of the form element.
- `callback` (function) [Optional]: The function to be executed when the form is submitted.
- `controllerPath` (string) [Optional]: The controller or route where you will direct the send.

**Example of use**

    _formSubmit('myForm', formSubmitCallback);
    _formSubmit('myForm', formSubmitCallback, '/route/example');

# Facebook-Batch-Class
A class in PHP for sending batch requests to Facebook for your Facebook app.

Imagine having 30 requests to get the photos of a user or commenting on different posts where every request takes time and adds overhead to the API calls and the server. This class intends to reduce all that to 1 request.

## Note

This class was written for Facebook PHP SDK v2.0 and current version is 5.0 so this has not been tested. It will be updated if found not to be working.

### Usage  

The basic assumption is you have a $facebook variable of the official Facebook class using the Facebook PHP SDK.  

1. Create an instance  
`$batch=new facebook_batch();`  

2. Add your query to `add()` function.  
`$request_key=$batch->add('/id/comments','post','hello');`  
The above creates a request to post a comment 'hello' to the `id` you specify. This returns a unique id for every request added.

3. Execute the requests after adding all requests.  
`$batch->execute();`  

4. Read response using the unique id in `$request_key` to know if it is posted.  
`$response=$batch->response($request_key);`

### License
See the [LICENSE](LICENSE.md) file for license rights and limitations (MIT)

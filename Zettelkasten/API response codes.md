202311021433
Status: #documentation
Tags: #API
# API response codes
### Response Codes

It is important to always **return a valid response code in each request**. These response codes can be used by a consuming application or client to know what exactly happened on the server side.

Here is a list of the most common response codes

- 200 - **Ok**. This signifies it is a success code and it is the default response code
- 201- **Created**. This shows that a resource has been created. It is useful for POST requests.
- 204- **No Content**. This signifies that the action was successful but no content is returned. It is useful for DELETE requests since a deleted resource cannot return any body content
- 400- **Bad Request**. This signifies that the client passed an invalid request to the server
- 401- **Unauthorized**. This signifies that the client is not authorized to access the resource. It is typically used in authentication and authorization services.
- 403- **Forbidden**. This signifies that a user is authenticated but is not allowed to access the resource.
- 404- **Not Found**. This signifies that a resource is not found
- 500- **Internal Server Error**. This implies that there is an error at the server level

---
## References

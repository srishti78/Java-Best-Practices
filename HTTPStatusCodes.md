| HTTP Code | Status Phrase              | Description                                                                                      |
|-----------|-----------------------------|-------------------------------------------------------------------------------------------------|
| 200       | OK                          | The request has succeeded. This is the standard response for successful HTTP requests.          |
| 201       | Created                     | The request has been fulfilled, resulting in the creation of a new resource.                    |
| 204       | No Content                  | The server successfully processed the request, but is not returning any content.                |
| 400       | Bad Request                 | The server could not understand the request due to invalid syntax.                              |
| 401       | Unauthorized                | The request requires user authentication.                                                       |
| 403       | Forbidden                   | The server understood the request but refuses to authorize it.                                  |
| 404       | Not Found                   | The server can't find the requested resource.                                                   |
| 405       | Method Not Allowed          | The request method is not supported for the requested resource.                                 |
| 409       | Conflict                    | The request could not be completed due to a conflict with the current state of the resource.    |
| 415       | Unsupported Media Type      | The server refuses to accept the request because the payload format is unsupported.             |
| 429       | Too Many Requests           | The user has sent too many requests in a given amount of time.                                  |
| 500       | Internal Server Error       | The server encountered an unexpected condition preventing it from fulfilling the request.       |
| 503       | Service Unavailable         | The server is currently unable to handle the request due to temporary overload or maintenance.  |
| 302       | Found                       | The requested resource has been temporarily moved to a different URI.                           |
| 301       | Moved Permanently           | The requested resource has been permanently moved to a new URI.                                 |
|           |                             |                                                                                                 |

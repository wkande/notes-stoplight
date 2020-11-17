# Authorization

The APIs implement an **Email-Code-Token** mechanism for authentication using [**jsonwebtoken**](https://www.npmjs.com/package/jsonwebtoken).

### cURL

1.  Prompt the user for their **Email Address** and call POST /user/code. The endpoint will send a **Code** to the email address and respond with status=201.

    ```bash
    curl -d "email=me@domain.com" \
    -H "Content-Type: application/x-www-form-urlencoded" \
    -X POST https://docs-as-code.herokuapp.com/user/code
    ```

2.  Prompt the user for the **Code** and their **Email**. Send both to GET /user/token. The endpoint will respond with a **Token** and status=200.

    ```bash
    curl -H "Accept:application/json" \
    -X GET "https://docs-as-code.herokuapp.com/user/token?email=me@mydomain.com&code=123456" | json_pp
    ```

--- 
### Use the "Try It" interface

Use these **Try It** blocks to accomplish the same thing. First create a code then get a token.


#### Create a Code

Enter your email address in request body.

```json http
{
  "method": "post",
  "url": "https://docs-as-code.herokuapp.com/user/code",
  "headers": {
    "Content-Type": "application/x-www-form-urlencoded",
    "Accept": "application/json"
  },
  "body": {
    "email": "me@mydomain.com"
  }
}
```

#### Get a Token

Enter the code sent to your email address and your email address in the query parameters.

```json http
{
  "method": "get",
  "url": "https://docs-as-code.herokuapp.com/user/token",
  "headers": {
    "Accept": "application/json"
  },
  "query": {
    "email": "me@mydomain.com",
    "code": ""
  }
}
```

The **Token** must be used to authenticate all other endpoints.

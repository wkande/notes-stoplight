# Heroku

There is a **Heroku Dyno** running **Notes**. Call it using CURL, Postman, Insomnia, your App or the **Try It** feature within the API reference of this guide. The dyno uses a free tier plan and may be idle. Calling an idle dyno may take a moment for it to come alive. Subsequent calls will be fast.


#### Request
Change the **email=me@domain.com** below to your email address. A code will be sent to your email address from support@lelandcreek.com.

```bash
curl -d "email=me@domain.com" \
-H "Content-Type: application/x-www-form-urlencoded" \
-X POST https://docs-as-code.herokuapp.com/user/code | json_pp
```

#### Response

```json
{
  "code": {
    "email": "me@mydomain.com",
    "message": "A code was sent to the email address.",
    "ip": "122.23.45.12"
  }
}
```

#### Deployment

Heroku pulls directly from the main branch of the [wkande/note repository](https://github.com/wkande/notes) to update the dyno running Notes.

The **Source Code** for the backend can be viewed on GitHub.  Deployment instructions are also present in the repo in the [deploy.md](https://github.com/wkande/notes/blob/master/deploy.md) file found in root of the repo.

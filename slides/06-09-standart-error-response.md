#### Помилки <small>(клієнта чи сервера)</small>

```js
Header: 
	Content-type: application/json
	...	
Status code: 400

Body:

{
  "error": 
   {
        "message": "No car found in the database",
        "developerMessage": "Еhe requested resource does not exist",
        "type": "account-error"
        "code": 34,
        "moreInfo": "http://dev.domain.com/api/v1/errors/34"
   }
}
```
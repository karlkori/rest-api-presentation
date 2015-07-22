## Best practice

#### Формат відповідь

```js
Header: 
	Content-type: application/json
	...	
Status code: 200

Body:

{
  "data": 
   {
        "id": "usr_1234567890",
        "name": "John",
        "email": "john@vakoms.com.ua",
        "role": "author"
        ...
   },
   "links" : {
   	 ...
   }
}
```
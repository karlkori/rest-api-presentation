## Колекції/елементи

- використовувати в назві імена, не дії
	
	**/cars**
	
	~~/getInfoAboutAllCars~~
- назва в множині <small>(або в однині, але одне правило на всі колекції)</small>

- дії з колекцією/елементом передавати через HTTP method
	- GET - лише вертає дані, нічого не змінює!
	- POST
	- PUT - оновлення конкретних даних, багаторазовий виклик не має змінювати дані по рзному
	- DELETE - багаторазове повторення не повинно мати ефекту
## API URLs


- **GET /cars**      	отримати список авто

- **POST /cars**     	створити нове авто

- **PUT /cars**      	оновити дані про авто

- **DELETE /cars**   	видалити всі авто

- **GET /cars/711**       отримати деталі конкретного авто

- **POST /cars/711**      Method not allowed (405)

- **PUT /cars/711**       оновити інфо для конкретного авто

- **DELETE /cars/711**    видалити конкретне авто

- вкладені або повязані колекції

	/users/123/tasks

	/users/123/bugs

- фільтр вихідних даних
	
	/users/123?fields=id,name,email

- можливість вернути одночасно дані, звязаної колекції

	/users/123?expand=tasks

```json
GET /task/123
{
    data: {
        id: 123,
        title: 'Buy a milk',
        owner: 'usr_1234567890'
    }
}

GET /task/123?expand=owner
{
    data: {
        id: 123,
        title: 'Buy a milk',
        owner: {
            id: 'usr_1234567890',
            name: 'John',
            email: 'john@gmail.com'
        }
    }
}
```

- пейджинг, умовні фільтри

GET /cars?color=red Returns a list of red cars
GET /cars?seats<=2 Returns a list of cars with a maximum of 2 seats
GET /cars?sort=-manufactorer,+model
GET /cars?fields=manufacturer,model,id,color
GET /cars?offset=10&limit=5

- версіонуваня
	
	/v1.2/cars/

	/2015-07-24/cars/

	/cars/	+ headers v1.2

	/cars?version=1.2

- формат даних
	
	Headers: Content-type: application/json

	/cars.json

	/cars?format=xml

- Use HTTP status codes

	200 – OK

	201 – OK + New resource has been created

	400 – Bad Request – The request was invalid or cannot be served. The exact error should be explained in the error payload. E.g. „The JSON is not valid“

	401 – Unauthorized – The request requires an user authentication

	403 – Forbidden – The server understood the request, but is refusing it or the access is not allowed.

	404 – Not found – There is no resource behind the URI.

	405 - Method not allowed, used to indicate that the requested URL exists, but the requested HTTP method is not applicable.	

- Example of error response:

```json
{
  "error": 
   {
        "message": "Sorry, the requested resource does not exist",
        "developerMessage": "No car found in the database",
        "code": 34,
        "type": "account-error"
        "moreInfo": "http://dev.example.com/api/v1/errors/34"
   }
}
```

- Make your IDs easily understood and descriptive:

	job_d1a62016cba4ee83
	obj_2d9b85fad42f64f8
	adr_575a1b720bcdd6dc

- Request IDs Header: Request-id: 123445678
	
- for localization response

# client request data with EN translation
Accept-Language: en

# server response data 
Content-Language: en

- usefull page in documentation: changelog or how upgrade
# example https://stripe.com/docs/upgrades

-  Чому портрібна документація

- Як документувати АПІ
	apiary.io
	swagger.io
	https://github.com/danielgtaylor/aglio
	https://github.com/tripit/slate
	http://apidocjs.com/

- Usefull links
https://github.com/marmelab/awesome-rest
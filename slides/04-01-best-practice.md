## Колекції/елементи

- використовувати в назві імена не дії
	
	**/cars**
	
	~~/getInfoAboutAllCars~~
- назва в множині <small>(або в однині, але одне правило на всі колекції)</small>

- дії з колекцією/елементом передавати через HTTP method
	- GET
	- POST
	- PUT
	- DELETE

- вкладені або повязані колекції

	/users/123/tasks

	/users/123/bugs

- фільтр вихідних даних
	
	/users/123?fields=id,name,email

- можливість вернути одночасно дані, звязаної колекції

	/users/123?expand=tasks

- пейджинг, умовні фільтри

- версіонуваня
	
	/v1.2/cars/

	/2015-07-24/cars/

	/cars/	+ headers v1.2

	/cars?version=1.2

- формат даних
	
	Headers: Content-type: application/json

	/cars.json

	/cars?format=xml

	
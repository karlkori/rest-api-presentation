## Best practices

#### фільтрація/пейджинг/сортування/...
	
- GET **/cars**?color=red

- GET **/cars**?seats<=2

- GET **/cars**?sort=-manufactorer,+model

- GET **/cars**?fields=manufacturer,model,id,color

- GET **/cars**?offset=10&limit=5
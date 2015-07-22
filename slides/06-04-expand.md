#### Можливість вернути одночасно дані, звязаної колекції

**GET /tasks/123?expand=owner**

```js
{
    id: tsk_1234567890,
    title: 'Buy a milk',
    owner: {
        id: 'usr_1234567890',
        name: 'John',
        email: 'john@vakoms.com.ua'
    }
}
```
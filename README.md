# Node.js
The task has to be made as a homework to the lecture #18 (Networking + Node.js). As I said, you will need 2 weeks for solving. :smiling_imp:
Somebody of you will be ~~happy~~ :angry:! Let's come to the task.

### Steps
- [x] Create a new server using [Express.js](http://expressjs.com/)
- [x] As the main storage, you have to create a new file `storage.data`
- [x] Create following [handlers](http://expressjs.com/en/guide/routing.html), which will be run according to the different requests:
- [`POST /users`](#post-users)
- [`GET /users`](#get-users)
- [`GET /users/{id}`](#get-usersid)
- [`PUT GET /users/{id}`](#put-usersid)
- [`DELETE GET /users/{id}`](#delete-usersid)

#### `POST /users`
Creates a new user (add user info into `storage.data`).

#### `GET /users`
Returns list of users

#### `GET /users/{id}`
Returns user by `id`

#### `PUT /users/{id}`
Replace user data by `id`

#### `DELETE /users/{id}`
Removes user by `id`

### User data:

|id|username|email|password|
|--|--------|-----|--------|
|1|johndoe|john.doe@myownservice.com|q8xowdnaxitf3g3ffjjl|
|2|johndoefriend|friend.of.john.doe@myownservice.com|2a1cgv7e0be2d26my8g9|

### Response examples:

`POST /users` - returns status code:
- `201` after successfully handling
- `409` if resource already exist

`GET /users` - returns a collection

```js
[{
  id: 1,
  username: ‘johndoe’,
  email: ‘john.doe@myownserver.com’
},
{
  id: 1,
  username: ‘johndoefriend’,
  email: ‘friend.of.john.doe@myownserver.com’
}]
```
or empty array

`GET /users/{id}` - returns user data by id
```js
{
  id: 1,
  username: ‘johndoe’,
  email: ‘john.doe@myownserver.com’
}
```
or status code :`404` when resource is not found

`PUT /users/{id}` - returns status code:
- `200` and new user' data
- `404` if user has been not found

`DELETE /users/{id}` - returns status code:
- `200` if user has been removed
- `404` if user has been not found

### Notes
Feel free to choose the data format of storage.data. It can be JSON, CSV, XML :), etc.
Use the module [fs](https://nodejs.org/api/fs.html#fs_fs_readsync_fd_buffer_offset_length_position) for working with file. 
DO NOT USE ‘Sync’ methods like: “fs.readSync()”. You have to use `fs.read(... callback(err, result))`
DO NOT save ‘node_modules’ in github repo. 
Also, it would be better to separate handlers into a few files.

Have a nice weekend! :joy:

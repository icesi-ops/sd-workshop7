# Workshop 6

## Microservices up and running
![Microservices](imgs/workshop.png)

## Usage

### frontend

![Frontend](imgs/frontend.png)

### auth-api

#### • POST /login
```bash
curl -X POST http://127.0.0.1:9000/login -d '{"username": "admin","password": "admin"}'
```

#### • POST /login response
```json
{
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MDk0ODc5MjAsImZpcnN0bmFtZSI6IkZvbyIsImxhc3RuYW1lIjoiQmFyIiwicm9sZSI6IkFETUlOIiwidXNlcm5hbWUiOiJhZG1pbiJ9.dtzpQd37YG9Mi_-h9PanuWKq31oJVrHD93218YQnsCg"
}
```

### users-api

#### • GET /user/admin
```bash
 curl -X GET -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MDk0ODc5MjAsImZpcnN0bmFtZSI6IkZvbyIsImxhc3RuYW1lIjoiQmFyIiwicm9sZSI6IkFETUlOIiwidXNlcm5hbWUiOiJhZG1pbiJ9.dtzpQd37YG9Mi_-h9PanuWKq31oJVrHD93218YQnsCg" http://127.0.0.1:8083/users/admin/
```

#### • GET /users/admin response
```json
{
    "username":"admin",
    "firstname":"Foo",
    "lastname":"Bar",
    "role":"ADMIN"
}
```

#### • GET /users/
```bash
 curl -X GET -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MDk0ODc5MjAsImZpcnN0bmFtZSI6IkZvbyIsImxhc3RuYW1lIjoiQmFyIiwicm9sZSI6IkFETUlOIiwidXNlcm5hbWUiOiJhZG1pbiJ9.dtzpQd37YG9Mi_-h9PanuWKq31oJVrHD93218YQnsCg" http://127.0.0.1:8083/users
```

#### • GET /users/ response
```json
[
    {
        "username": "admin",
        "firstname": "Foo",
        "lastname": "Bar",
        "role": "ADMIN"
    },
    {
        "username": "johnd",
        "firstname": "John",
        "lastname": "Doe",
        "role": "USER"
    },
    {
        "username": "janed",
        "firstname": "Jane",
        "lastname": "Doe",
        "role": "USER"
    }
]
```

### todos-api

#### • GET /todos
```bash
 curl -X GET -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MDk0ODc5MjAsImZpcnN0bmFtZSI6IkZvbyIsImxhc3RuYW1lIjoiQmFyIiwicm9sZSI6IkFETUlOIiwidXNlcm5hbWUiOiJhZG1pbiJ9.dtzpQd37YG9Mi_-h9PanuWKq31oJVrHD93218YQnsCg" http://127.0.0.1:8082/todos
```

#### • GET /todos response
```json
{
    "1": {
        "id": 1,
        "content": "Create new todo"
    },
    "2": {
        "id": 2,
        "content": "Update me"
    },
    "3": {
        "id": 3,
        "content": "Delete example ones"
    }
}
```

#### • POST /todos
```bash
 curl -X POST -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MDk0ODc5MjAsImZpcnN0bmFtZSI6IkZvbyIsImxhc3RuYW1lIjoiQmFyIiwicm9sZSI6IkFETUlOIiwidXNlcm5hbWUiOiJhZG1pbiJ9.dtzpQd37YG9Mi_-h9PanuWKq31oJVrHD93218YQnsCg" http://127.0.0.1:8082/todos -d '{"content": "deal with that"}'
```

#### • POST /todos response
```json
{
    "content": "deal with that",
    "id": 3
}
```

#### • DELETE /todos/3
```bash
 curl -X DELETE -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MDk0ODc5MjAsImZpcnN0bmFtZSI6IkZvbyIsImxhc3RuYW1lIjoiQmFyIiwicm9sZSI6IkFETUlOIiwidXNlcm5hbWUiOiJhZG1pbiJ9.dtzpQd37YG9Mi_-h9PanuWKq31oJVrHD93218YQnsCg" http://127.0.0.1:8082/todos/3
```

#### • DELETE /todos/3 new todos list
```json
{
    "1": {
        "id": 1,
        "content": "Create new todo"
    },
    "2": {
        "id": 2,
        "content": "Update me"
    }
}
```


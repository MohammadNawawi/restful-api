# User API Spec

## Register User

Endpoint : POST /api/users

Request Body :

```json
{
  "username": "fromnaw",
  "password": "*******",
  "name": "Mohammad Nawawi"
}
```

Response Body ( Success ) :

```json
{
  "data": {
    "username": "fromnaw",
    "name": "Mohammad Nawawi"
  }
}
```

Response Body ( Failed ) :

```json
{
  "errors": "Username already registered"
}
```

## Login User

Endpoint : POST /api/users/login

Request Body :

```json
{
  "username": "fromnaw",
  "password": "*******"
}
```

Response Body ( Success ) :

```json
{
  "data": {
    "username": "fromnaw",
    "name": "Mohammad Nawawi",
    "token": "session_id_generated"
  }
}
```

Response Body ( Failed ) :

```json
{
  "errors": "Username or password is wrong!"
}
```

## Get User

Endpoint : GET /api/current

Headers :

- authorization : token

Response Body ( Success ) :

```json
{
  "data": {
    "username": "fromnaw",
    "name": "Mohammad Nawawi"
  }
}
```

Response Body ( Failed ) :

```json
{
  "errors": "Unatuhorized"
}
```

## Update User

Endpoint : PATCH /api/users/current

Headers :

- Authorization : token

Request Body :

```json
{
  "password": "*******", //Optional
  "name": "Mohammad Nawawi" //Optional
}
```

Response Body ( Success ) :

```json
{
  "data": {
    "username": "fromnaw",
    "name": "Mohammad Nawawi"
  }
}
```

## Logout User

Endpoint : DELETE /api/users/current

Headers :

- Authorization : token

Request Body :

Response Body ( Success ) :

```json
{
  "data": true
}
```

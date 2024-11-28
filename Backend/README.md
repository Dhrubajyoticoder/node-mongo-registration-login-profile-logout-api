# Backend API Documentation
=====================================


### Endpoints

#### 1. /users/register

##### Description
Registers a new user by creating a user account with the provided information.

##### HTTP Method
POST

##### Request Body
The request body should be in JSON format and include the following fields:

* `fullname` (object):
	+ `firstname` (string, required): User's first name (minimum 3 characters).
	+ `lastname` (string, optional): User's last name (minimum 3 characters).
* `email` (string, required): User's email address (must be a valid email).
* `password` (string, required): User's password (minimum 6 characters).

##### Example Response

#### User Object

* `user` (object):
	+ `fullname` (object):
		- `firstname` (string): User's first name (minimum 3 characters).
		- `lastname` (string): User's last name (minimum 3 characters).
	+ `email` (string): User's email address (must be a valid email).
	+ `password` (string): User's password (minimum 6 characters).
	+ `token` (String): JWT Token

#### 2. /users/login

##### Description
Authenticates a user using their email and password, returning a JWT token upon successful login.

##### HTTP Method
POST

##### Request Body
The request body should be in JSON format and include the following fields:

* `email` (string, required): User's email address (must be a valid email).
* `password` (string, required): User's password (minimum 6 characters).

##### Example Response
user (object):
  fullname (object):
    firstname (string): User's first name (minimum 3 characters).
    lastname (string): User's last name (minimum 3 characters).
  email (string): User's email address (must be a valid email).
  password (string): User's password (minimum 6 characters).
  token (String): JWT Token

### 3. /users/profile

##### Description
Retrieves the profile information of the currently authenticated user.

##### HTTP Method
GET

##### Authentication
Requires a valid JWT token in the Authorization header: `Authorization: Bearer <token>`

##### Example Response
`user` (object):
  `fullname` (object):
    `firstname` (string): User's first name (minimum 3 characters).
    `lastname` (string): User's last name (minimum 3 characters).
  `email` (string): User's email address (must be a valid email).

### 4. /users/logout

##### Description
Logout the current user and blacklist the token provided in cookie or headers.

##### HTTP Method
GET

##### Authentication
Requires a valid JWT token in the Authorization header or cookie.

#### User Object

* `user` (object):
	+ `fullname` (object):
		- `firstname` (string): User's first name (minimum 3 characters).
		- `lastname` (string): User's last name (minimum 3 characters).
	+ `email` (string): User's email address (must be a valid email).
	+ `password` (string): User's password (minimum 6 characters).
	+ `token` (String): JWT Token

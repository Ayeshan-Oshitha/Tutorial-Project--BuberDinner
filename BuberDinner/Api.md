# Buber Dinner API

- [Buber Dinner API](#buber-dinner-api)
	- [Auth](#auth)
		- [Register](#register)
			- [Register Request](#register-request)
			- [Register Response](#register-response)
		- [Login](#login)
			- [Login Request](#login-request)
			- [Login Response](#login-response)

## Auth

### Register

```json
POST {{host}}/auth/register
```

#### Register Request

```json
{
    "firstName":"Amichai",
	"lastName":"Mantinband",
	"email" : "amichai@mantinband.com",
	"password" : "Amiko1232!"
}
```

#### Register Response

```json
200 Ok
```

```json
{
	"id" : "d89c2d9a-eb3a-4075-95ff-b920b55aa104"
	"firstName":"Amichai",
	"lastName":"Mantinband",
	"email" : "amichai@mantinband.com",
	"token" : "eyJhb...z9dqcnXoY"
}
```

### Login

```json
POST {{host}}/auth/login
```


#### Login Request
```json
{
	"email" : "amichai@mantinband.com",
	"password" : "Amiko1232!"
}
```

#### Login Response
```json
{
	"id" : "d89c2d9a-eb3a-4075-95ff-b920b55aa104"
	"firstName":"Amichai",
	"lastName":"Mantinband",
	"email" : "amichai@mantinband.com",
	"token" : "eyJhb...z9dqcnXoY"	
}
```


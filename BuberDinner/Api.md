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


# Extra

## Part 2  - Generating JWT Token

### User-Secrets

##### Command 1

```
dotnet user-secrets init --project .\BuberDinner.Api
```
- Adds a <UserSecretsId> to your .csproj file (BuberDinner.Api.csproj).

- This ID links your project to a secrets file stored on your machine, not in your codebase.

- The ID looks like this: 6b1db5f2-41f7-49e2-9d69-a9c7005d7c31.

- It enables user secrets for this specific project.

##### Command 2

```
dotnet user-secrets set --project .\BuberDinner.Api "JwtSettings:Secret" "super-secret-key-from-user"
```
- Sets a secret value using the key "JwtSettings:Secret" and value "super-secret-key-from-user".

- The format is like adding something to appsettings.json:
```
"JwtSettings": {
  "Secret": "super-secret-key-from-user-secrets"
}
```

- This secret is stored in a secure, local secrets file (not visible in the code).

##### Command 3

```
dotnet user-secrets list --project .\BuberDinner.Api
```

- Lists all the secrets associated with this project.


## Part 3 - Repository Pattern

What is repository pattern ?

- Microsoft - Repositories are classes or components that ancapsulates the logic required to access data sources.

- Martin Fowler - Mediated between the domain and data mapping layers using a collection-like interface for accessing domain objects.



AI Tutor

← All projects
Todo List API
Build a RESTful API to allow users to manage their to-do list.

beginner
RESTful API
Database
CRUD Operations
Data Modeling
Authentication
Details
Solutions

Started working 2 hours ago. Follow these tips to get most out of it.
Started Working

Submit Solution
5 upvotes
10 upvotes
In this project you are required to develop a RESTful API to allow users to manage their to-do list. The previous backend projects have only focused on the CRUD operations, but this project will require you to implement user authentication as well.

Todo List API
Goals
The skills you will learn from this project include:

User authentication

Schema design and Databases

RESTful API design

CRUD operations

Error handling

Security

Requirements
You are required to develop a RESTful API with following endpoints

User registration to create a new user

Login endpoint to authenticate the user and generate a token

CRUD operations for managing the to-do list

Implement user authentication to allow only authorized users to access the to-do list

Implement error handling and security measures

Use a database to store the user and to-do list data (you can use any database of your choice)

Implement proper data validation

Implement pagination and filtering for the to-do list

Given below is a list of the endpoints and the details of the request and response:

User Registration
Register a new user using the following request:

javascript

POST /register
{
  "name": "John Doe",
  "email": "john@doe.com",
  "password": "password"
}
This will validate the given details, make sure the email is unique and store the user details in the database. Make sure to hash the password before storing it in the database. Respond with a token that can be used for authentication if the registration is successful.

json

{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9"
}
The token can either be a JWT or a random string that can be used for authentication. We leave it up to you to decide the implementation details.

User Login
Authenticate the user using the following request:

javascript

POST /login
{
  "email": "john@doe.com",
  "password": "password"
}
This will validate the given email and password, and respond with a token if the authentication is successful.

json

{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9"
}
Create a To-Do Item
Create a new to-do item using the following request:

javascript

POST /todos
{
  "title": "Buy groceries",
  "description": "Buy milk, eggs, and bread"
}
User must send the token received from the login endpoint in the header to authenticate the request. You can use the Authorization header with the token as the value. In case the token is missing or invalid, respond with an error and status code 401.

json

{
  "message": "Unauthorized"
}
Upon successful creation of the to-do item, respond with the details of the created item.

json

{
  "id": 1,
  "title": "Buy groceries",
  "description": "Buy milk, eggs, and bread"
}
Update a To-Do Item
Update an existing to-do item using the following request:

javascript

PUT /todos/1
{
  "title": "Buy groceries",
  "description": "Buy milk, eggs, bread, and cheese"
}
Just like the create todo endpoint, user must send the token received. Also make sure to validate the user has the permission to update the to-do item i.e. the user is the creator of todo item that they are updating. Respond with an error and status code 403 if the user is not authorized to update the item.

json

{
  "message": "Forbidden"
}
Upon successful update of the to-do item, respond with the updated details of the item.

json

{
  "id": 1,
  "title": "Buy groceries",
  "description": "Buy milk, eggs, bread, and cheese"
}
Delete a To-Do Item
Delete an existing to-do item using the following request:

javascript

DELETE /todos/1
User must be authenticated and authorized to delete the to-do item. Upon successful deletion, respond with the status code 204.

Get To-Do Items
Get the list of to-do items using the following request:

javascript

GET /todos?page=1&limit=10
User must be authenticated to access the tasks and the response should be paginated. Respond with the list of to-do items along with the pagination details.

json

{
  "data": [
    {
      "id": 1,
      "title": "Buy groceries",
      "description": "Buy milk, eggs, bread"
    },
    {
      "id": 2,
      "title": "Pay bills",
      "description": "Pay electricity and water bills"
    }
  ],
  "page": 1,
  "limit": 10,
  "total": 2
}
Bonus
Implement filtering and sorting for the to-do list

Implement unit tests for the API

Implement rate limiting and throttling for the API

Implement refresh token mechanism for the authentication

This project will help you understand how to design and implement a RESTful API with user authentication. You will also learn how to work with databases, handle errors, and implement security measures.

Join the Community

roadmap.sh is among the top 10 most starred projects on GitHub and is visited by hundreds of thousands of developers every month.

Top 10
 out of 28M!

373K

GitHub Stars

Star us on GitHub
Help us reach #1
+90k
every month

+3.2M

Registered Users

Register yourself
Commit to your growth
+2k
every month

52K

Discord Members

Join on Discord
Join the community
Roadmaps
Guides
FAQs
YouTube

roadmap.sh
by
@nilbuild

Community created roadmaps, best practices, projects, articles, resources and journeys to help you choose your path and grow in your career.

© roadmap.sh·Terms·Privacy·

ThewNewStack
The top DevOps resource for Kubernetes, cloud-native computing, and large-scale development and deployment.

DevOps·Kubernetes·Cloud-Native

Cookie Settings
{
  "data": [
    {
      "id": 1,
      "title": "Buy groceries",
      "description": "Buy milk, eggs, bread"
    },
    {
      "id": 2,
      "title": "Pay bills",
      "description": "Pay electricity and water bills"
    }
  ],
  "page": 1,
  "limit": 10,
  "total": 2
}

# setup-python

[![Basic validation](https://github.com/actions/setup-python/actions/workflows/basic-validation.yml/badge.svg?branch=main)](https://github.com/actions/setup-python/actions/workflows/basic-validation.yml)
[![Validate Python e2e](https://github.com/actions/setup-python/actions/workflows/test-python.yml/badge.svg?branch=main)](https://github.com/actions/setup-python/actions/workflows/test-python.yml)
[![Validate PyPy e2e](https://github.com/actions/setup-python/actions/workflows/test-pypy.yml/badge.svg?branch=main)](https://github.com/actions/setup-python/actions/workflows/test-pypy.yml)
[![e2e-cache](https://github.com/actions/setup-python/actions/workflows/e2e-cache.yml/badge.svg?branch=main)](https://github.com/actions/setup-python/actions/workflows/e2e-cache.yml)

This action provides the following functionality for GitHub Actions users:

- Installing a version of Python or PyPy and (by default) adding it to the PATH
- Optionally caching dependencies for pip, pipenv and poetry
- Registering problem matchers for error output

## What's new in V7

- Migrated action internals to ESM for compatibility with latest `@actions/*` packages. No changes to action inputs, outputs, or behavior.

## Breaking changes in V6

- Upgraded action from node20 to node24
  > Make sure your runner is on version v2.327.1 or later to ensure compatibility with this release. See [Release Notes](https://github.com/actions/runner/releases/tag/v2.327.1)

For more details,  see the full release notes on the [releases page](https://github.com/actions/setup-python/releases/tag/v6.0.0)

## Basic usage

See [action.yml](action.yml)

**Python**
```yaml
steps:
- uses: actions/checkout@v7
- uses: actions/setup-python@v7
  with:
    python-version: '3.13' 
- run: python my_script.py
```

**PyPy**
```yaml
steps:
- uses: actions/checkout@v7
- uses: actions/setup-python@v7 
  with:
    python-version: 'pypy3.10' 
- run: python my_script.py
```

**GraalPy**
```yaml
steps:
- uses: actions/checkout@v7
- uses: actions/setup-python@v7 
  with:
    python-version: 'graalpy-24.0' 
- run: python my_script.py
```

**Free threaded Python**
```yaml
steps:
- uses: actions/checkout@v7
- uses: actions/setup-python@v7
  with:
    python-version: '3.13t'
- run: python my_script.py
```

The `python-version` input is optional. If not supplied, the action will try to resolve the version from the default `.python-version` file. If the `.python-version` file doesn't exist Python or PyPy version from the PATH will be used. The default version of Python or PyPy in PATH varies between runners and can be changed unexpectedly so we recommend always setting Python version explicitly using the `python-version` or `python-version-file` inputs.

The action will first check the local [tool cache](docs/advanced-usage.md#hosted-tool-cache) for a [semver](https://github.com/npm/node-semver#versions) match. If unable to find a specific version in the tool cache, the action will attempt to download a version of Python from [GitHub Releases](https://github.com/actions/python-versions/releases) and for PyPy from the official [PyPy's dist](https://downloads.python.org/pypy/).

For information regarding locally cached versions of Python or PyPy on GitHub hosted runners, check out [GitHub Actions Runner Images](https://github.com/actions/runner-images).

## Supported version syntax

The `python-version` input supports the [Semantic Versioning Specification](https://semver.org/) and some special version notations (e.g. `semver ranges`, `x.y-dev syntax`, etc.), for detailed examples please refer to the section: [Using python-version input](docs/advanced-usage.md#using-the-python-version-input) of the [Advanced usage](docs/advanced-usage.md) guide.

## Supported architectures

Using the `architecture` input, it is possible to specify the required Python or PyPy interpreter architecture: `x86`, `x64`, or `arm64`. If the input is not specified, the architecture defaults to the host OS architecture.

## Caching packages dependencies

The action has built-in functionality for caching and restoring dependencies. It uses [toolkit/cache](https://github.com/actions/toolkit/tree/main/packages/cache) under the hood for caching dependencies but requires less configuration settings. Supported package managers are `pip`, `pipenv` and `poetry`. The `cache` input is optional, and caching is turned off by default.

The action defaults to searching for a dependency file (`requirements.txt` or `pyproject.toml` for pip, `Pipfile.lock` for pipenv or `poetry.lock` for poetry) in the repository, and uses its hash as a part of the cache key. Input `cache-dependency-path` is used for cases when multiple dependency files are used, they are located in different subdirectories or different files for the hash that want to be used.

 - For `pip`, the action will cache the global cache directory
 - For `pipenv`, the action will cache virtualenv directory
 - For `poetry`, the action will cache virtualenv directories -- one for each poetry project found

**Caching pip dependencies:**

```yaml
steps:
- uses: actions/checkout@v7
- uses: actions/setup-python@v7
  with:
    python-version: '3.13'
    cache: 'pip' # caching pip dependencies
- run: pip install -r requirements.txt
```
>**Note:** Restored cache will not be used if the requirements.txt file is not updated for a long time and a newer version of the dependency is available which can lead to an increase in total build time.

>The requirements file format allows for specifying dependency versions using logical operators (for example chardet>=3.0.4) or specifying dependencies without any versions. In this case the pip install -r requirements.txt command will always try to install the latest available package version. To be sure that the cache will be used, please stick to a specific dependency version and update it manually if necessary.

>The `setup-python` action does not handle authentication for pip when installing packages from private repositories. For help, refer [pip’s VCS support documentation](https://pip.pypa.io/en/stable/topics/vcs-support/) or visit the [pip repository](https://github.com/pypa/pip).

See examples of using `cache` and `cache-dependency-path` for `pipenv` and `poetry` in the section: [Caching packages](docs/advanced-usage.md#caching-packages) of the [Advanced usage](docs/advanced-usage.md) guide.

## Advanced usage

- [Using the python-version input](docs/advanced-usage.md#using-the-python-version-input)
- [Using the python-version-file input](docs/advanced-usage.md#using-the-python-version-file-input)
- [Check latest version](docs/advanced-usage.md#check-latest-version)
- [Caching packages](docs/advanced-usage.md#caching-packages)
- [Outputs and environment variables](docs/advanced-usage.md#outputs-and-environment-variables)
- [Available versions of Python, PyPy and GraalPy](docs/advanced-usage.md#available-versions-of-python-pypy-and-graalpy)
- [Hosted tool cache](docs/advanced-usage.md#hosted-tool-cache) 
- [Using `setup-python` with a self-hosted runner](docs/advanced-usage.md#using-setup-python-with-a-self-hosted-runner)
- [Using `setup-python` on GHES](docs/advanced-usage.md#using-setup-python-on-ghes)
- [Allow pre-releases](docs/advanced-usage.md#allow-pre-releases)
- [Using the pip-version input](docs/advanced-usage.md#using-the-pip-version-input)

## Recommended permissions

When using the `setup-python` action in your GitHub Actions workflow, it is recommended to set the following permissions to ensure proper functionality:

```yaml
permissions:
  contents: read # access to check out code and install dependencies
```

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE).

## Contributions

Contributions are welcome! See our [Contributor's Guide](docs/contributors.md).
AI Tutor

← All projects
Todo List API
Build a RESTful API to allow users to manage their to-do list.

beginner
RESTful API
Database
CRUD Operations
Data Modeling
Authentication
Details
Solutions

Started working 2 hours ago. Follow these tips to get most out of it.
Started Working

Submit Solution
5 upvotes
10 upvotes
In this project you are required to develop a RESTful API to allow users to manage their to-do list. The previous backend projects have only focused on the CRUD operations, but this project will require you to implement user authentication as well.

Todo List API
Goals
The skills you will learn from this project include:

User authentication

Schema design and Databases

RESTful API design

CRUD operations

Error handling

Security

Requirements
You are required to develop a RESTful API with following endpoints

User registration to create a new user

Login endpoint to authenticate the user and generate a token

CRUD operations for managing the to-do list

Implement user authentication to allow only authorized users to access the to-do list

Implement error handling and security measures

Use a database to store the user and to-do list data (you can use any database of your choice)

Implement proper data validation

Implement pagination and filtering for the to-do list

Given below is a list of the endpoints and the details of the request and response:

User Registration
Register a new user using the following request:

javascript

POST /register
{
  "name": "John Doe",
  "email": "john@doe.com",
  "password": "password"
}
This will validate the given details, make sure the email is unique and store the user details in the database. Make sure to hash the password before storing it in the database. Respond with a token that can be used for authentication if the registration is successful.

json

{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9"
}
The token can either be a JWT or a random string that can be used for authentication. We leave it up to you to decide the implementation details.

User Login
Authenticate the user using the following request:

javascript

POST /login
{
  "email": "john@doe.com",
  "password": "password"
}
This will validate the given email and password, and respond with a token if the authentication is successful.

json

{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9"
}
Create a To-Do Item
Create a new to-do item using the following request:

javascript

POST /todos
{
  "title": "Buy groceries",
  "description": "Buy milk, eggs, and bread"
}
User must send the token received from the login endpoint in the header to authenticate the request. You can use the Authorization header with the token as the value. In case the token is missing or invalid, respond with an error and status code 401.

json

{
  "message": "Unauthorized"
}
Upon successful creation of the to-do item, respond with the details of the created item.

json

{
  "id": 1,
  "title": "Buy groceries",
  "description": "Buy milk, eggs, and bread"
}
Update a To-Do Item
Update an existing to-do item using the following request:

javascript

PUT /todos/1
{
  "title": "Buy groceries",
  "description": "Buy milk, eggs, bread, and cheese"
}
Just like the create todo endpoint, user must send the token received. Also make sure to validate the user has the permission to update the to-do item i.e. the user is the creator of todo item that they are updating. Respond with an error and status code 403 if the user is not authorized to update the item.

json

{
  "message": "Forbidden"
}
Upon successful update of the to-do item, respond with the updated details of the item.

json

{
  "id": 1,
  "title": "Buy groceries",
  "description": "Buy milk, eggs, bread, and cheese"
}
Delete a To-Do Item
Delete an existing to-do item using the following request:

javascript

DELETE /todos/1
User must be authenticated and authorized to delete the to-do item. Upon successful deletion, respond with the status code 204.

Get To-Do Items
Get the list of to-do items using the following request:

javascript

GET /todos?page=1&limit=10
User must be authenticated to access the tasks and the response should be paginated. Respond with the list of to-do items along with the pagination details.

json

{
  "data": [
    {
      "id": 1,
      "title": "Buy groceries",
      "description": "Buy milk, eggs, bread"
    },
    {
      "id": 2,
      "title": "Pay bills",
      "description": "Pay electricity and water bills"
    }
  ],
  "page": 1,
  "limit": 10,
  "total": 2
}
Bonus
Implement filtering and sorting for the to-do list

Implement unit tests for the API

Implement rate limiting and throttling for the API

Implement refresh token mechanism for the authentication

This project will help you understand how to design and implement a RESTful API with user authentication. You will also learn how to work with databases, handle errors, and implement security measures.

Join the Community

roadmap.sh is among the top 10 most starred projects on GitHub and is visited by hundreds of thousands of developers every month.

Top 10
 out of 28M!

373K

GitHub Stars

Star us on GitHub
Help us reach #1
+90k
every month

+3.2M

Registered Users

Register yourself
Commit to your growth
+2k
every month

52K

Discord Members

Join on Discord
Join the community
Roadmaps
Guides
FAQs
YouTube

roadmap.sh
by
@nilbuild

Community created roadmaps, best practices, projects, articles, resources and journeys to help you choose your path and grow in your career.

© roadmap.sh·Terms·Privacy·

ThewNewStack
The top DevOps resource for Kubernetes, cloud-native computing, and large-scale development and deployment.

DevOps·Kubernetes·Cloud-Native

Cookie Settings
AI Tutor

← All projects
Todo List API
Build a RESTful API to allow users to manage their to-do list.

beginner
RESTful API
Database
CRUD Operations
Data Modeling
Authentication
Details
Solutions

Started working 2 hours ago. Follow these tips to get most out of it.
Started Working

Submit Solution
5 upvotes
10 upvotes
In this project you are required to develop a RESTful API to allow users to manage their to-do list. The previous backend projects have only focused on the CRUD operations, but this project will require you to implement user authentication as well.

Todo List API
Goals
The skills you will learn from this project include:

User authentication

Schema design and Databases

RESTful API design

CRUD operations

Error handling

Security

Requirements
You are required to develop a RESTful API with following endpoints

User registration to create a new user

Login endpoint to authenticate the user and generate a token

CRUD operations for managing the to-do list

Implement user authentication to allow only authorized users to access the to-do list

Implement error handling and security measures

Use a database to store the user and to-do list data (you can use any database of your choice)

Implement proper data validation

Implement pagination and filtering for the to-do list

Given below is a list of the endpoints and the details of the request and response:

User Registration
Register a new user using the following request:

javascript

POST /register
{
  "name": "John Doe",
  "email": "john@doe.com",
  "password": "password"
}
This will validate the given details, make sure the email is unique and store the user details in the database. Make sure to hash the password before storing it in the database. Respond with a token that can be used for authentication if the registration is successful.

json

{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9"
}
The token can either be a JWT or a random string that can be used for authentication. We leave it up to you to decide the implementation details.

User Login
Authenticate the user using the following request:

javascript

POST /login
{
  "email": "john@doe.com",
  "password": "password"
}
This will validate the given email and password, and respond with a token if the authentication is successful.

json

{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9"
}
Create a To-Do Item
Create a new to-do item using the following request:

javascript

POST /todos
{
  "title": "Buy groceries",
  "description": "Buy milk, eggs, and bread"
}
User must send the token received from the login endpoint in the header to authenticate the request. You can use the Authorization header with the token as the value. In case the token is missing or invalid, respond with an error and status code 401.

json

{
  "message": "Unauthorized"
}
Upon successful creation of the to-do item, respond with the details of the created item.

json

{
  "id": 1,
  "title": "Buy groceries",
  "description": "Buy milk, eggs, and bread"
}
Update a To-Do Item
Update an existing to-do item using the following request:

javascript

PUT /todos/1
{
  "title": "Buy groceries",
  "description": "Buy milk, eggs, bread, and cheese"
}
Just like the create todo endpoint, user must send the token received. Also make sure to validate the user has the permission to update the to-do item i.e. the user is the creator of todo item that they are updating. Respond with an error and status code 403 if the user is not authorized to update the item.

json

{
  "message": "Forbidden"
}
Upon successful update of the to-do item, respond with the updated details of the item.

json

{
  "id": 1,
  "title": "Buy groceries",
  "description": "Buy milk, eggs, bread, and cheese"
}
Delete a To-Do Item
Delete an existing to-do item using the following request:

javascript

DELETE /todos/1
User must be authenticated and authorized to delete the to-do item. Upon successful deletion, respond with the status code 204.

Get To-Do Items
Get the list of to-do items using the following request:

javascript

GET /todos?page=1&limit=10
User must be authenticated to access the tasks and the response should be paginated. Respond with the list of to-do items along with the pagination details.

json

{
  "data": [
    {
      "id": 1,
      "title": "Buy groceries",
      "description": "Buy milk, eggs, bread"
    },
    {
      "id": 2,
      "title": "Pay bills",
      "description": "Pay electricity and water bills"
    }
  ],
  "page": 1,
  "limit": 10,
  "total": 2
}
Bonus
Implement filtering and sorting for the to-do list

Implement unit tests for the API

Implement rate limiting and throttling for the API

Implement refresh token mechanism for the authentication

This project will help you understand how to design and implement a RESTful API with user authentication. You will also learn how to work with databases, handle errors, and implement security measures.

Join the Community

roadmap.sh is among the top 10 most starred projects on GitHub and is visited by hundreds of thousands of developers every month.

Top 10
 out of 28M!

373K

GitHub Stars

Star us on GitHub
Help us reach #1
+90k
every month

+3.2M

Registered Users

Register yourself
Commit to your growth
+2k
every month

52K

Discord Members

Join on Discord
Join the community
Roadmaps
Guides
FAQs
YouTube

roadmap.sh
by
@nilbuild

Community created roadmaps, best practices, projects, articles, resources and journeys to help you choose your path and grow in your career.

© roadmap.sh·Terms·Privacy·

ThewNewStack
The top DevOps resource for Kubernetes, cloud-native computing, and large-scale development and deployment.

DevOps·Kubernetes·Cloud-Native

Cookie Settings


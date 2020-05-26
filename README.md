## Redux ToDo Web Backend

[![CircleCI](https://circleci.com/gh/alstn2468/Redux_ToDo_Web_Backend.svg?style=svg)](https://circleci.com/gh/alstn2468/Redux_ToDo_Web_Backend)
[![codecov](https://codecov.io/gh/alstn2468/Redux_ToDo_Web_Backend/branch/master/graph/badge.svg)](https://codecov.io/gh/alstn2468/Redux_ToDo_Web_Backend)
[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)<br>
[![Python Version](https://img.shields.io/github/pipenv/locked/python-version/alstn2468/Redux_ToDo_Web_Backend)](https://shields.io/)
[![Django Version](https://img.shields.io/github/pipenv/locked/dependency-version/alstn2468/Redux_ToDo_Web_Backend/django)](https://shields.io/)
[![Generic badge](https://img.shields.io/github/languages/top/alstn2468/Redux_ToDo_Web_Backend)](https://shields.io/)

### Author : [Kim Minsu](https://github.com/alstn2468)<br/>[ [Facebook](https://www.facebook.com/profile.php?id=100003769223078) ] [ [Github](https://github.com/alstn2468) ] [ [LinkedIn](https://www.linkedin.com/in/minsu-kim-336289160/) ] [ [Blog](https://alstn2468.github.io/) ]<br/>

This repository is backend server of this [Redux_ToDo_Web](https://github.com/alstn2468/Redux_ToDo_Web) repository.

### Function

- Get all todo items [➡️](#get-all-todo-items)
- Create one todo item [➡️](#create-one-todo-item)
- Remove all completed todo items [➡️](#remove-all-completed-todo-items)
- Updated one todo item [➡️](#updated-one-todo-item)
- Delete one todo itme [➡️](#delete-one-todo-item)

### ⏰ To Do

- [x] Connect to [Front-End Web Application](https://github.com/alstn2468/Redux_ToDo_Web)
- [ ] Implement authentication logic using jwt
- [ ] Implement kakao oauth
- [ ] Implement github oauth
- [ ] Implement google oauth
- [x] Deploy to Heroku using Circle CI
- [ ] More detailed exception handling

### 📝 Document

#### Get all todo items

##### 1️⃣ Request

```http
GET /todo
```

##### 2️⃣ Parameter

| Name  | Description | Required |
| :---: | :---------: | :------: |
|   -   |      -      |    -     |

##### 3️⃣ Response

| Name  |              Description              |
| :---: | :-----------------------------------: |
| data  | Array consisting of todo item objects |
| error |       Message in case of error        |

##### 4️⃣ Sample

- Success

```json
HTTP/1.1 200 OK
Content-Type: application/json;charset=UTF-8
{
    data: [
        { id: 1, text: "todo 1", isCompleted: true },
        { id: 2, text: "todo 2", isCompleted: false },
        { id: 3, text: "todo 3", isCompleted: true }
    ]
}
```

- Fail

```json
HTTP/1.1 500 INTERNAL SERVER ERROR
Content-Type: application/json;charset=UTF-8
{
    error: "An error has occurred. Please try again."
}
```

#### Create one todo item

##### 1️⃣ Request

```http
POST /todo
```

##### 2️⃣ Parameter

| Name  |         Description          | Required |
| :---: | :--------------------------: | :------: |
| text  | Todo item text to be created |    ✔     |

##### 3️⃣ Response

| Name  |       Description        |
| :---: | :----------------------: |
| data  | Created todo item object |
| error | Message in case of error |

##### 4️⃣ Sample

- Success

```json
HTTP/1.1 200 OK
Content-Type: application/json
{
    data: { id: 4, text: "todo 4", isCompleted: false }
}
```

- Fail

```json
HTTP/1.1 500 INTERNAL SERVER ERROR
Content-Type: application/json
{
    error: "An error has occurred. Please try again."
}
```

#### Remove all completed todo items

##### 1️⃣ Request

```http
DELETE /todo
```

##### 2️⃣ Parameter

| Name  | Description | Required |
| :---: | :---------: | :------: |
|   -   |      -      |    -     |

##### 3️⃣ Response

| Name  |       Description        |
| :---: | :----------------------: |
| error | Message in case of error |

##### 4️⃣ Sample

- Success

```json
HTTP/1.1 204 NO CONTENT
Content-Type: application/json
```

- Fail

```json
HTTP/1.1 500 INTERNAL SERVER ERROR
Content-Type: application/json
{
    error: "An error has occurred. Please try again."
}
```

#### Updated one todo item

##### 1️⃣ Request

```http
PUT /todo/:id
```

##### 2️⃣ Parameter

|    Name     |           Description            | Required |
| :---------: | :------------------------------: | :------: |
|     id      | Unique id of item to be updated  |    ✔     |
|    text     |    Text of item to be updated    |    ✔     |
| isCompleted | Completion of item to be updated |    ✔     |

##### 3️⃣ Response

| Name  |       Description        |
| :---: | :----------------------: |
| data  | Updated todo item object |
| error | Message in case of error |

##### 4️⃣ Sample

- Success

```json
HTTP/1.1 200 OK
Content-Type: application/json
{
    data: { id: 4, text: "Updated Item", isCompleted: true }
}
```

- Fail

```json
HTTP/1.1 500 INTERNAL SERVER ERROR
Content-Type: application/json
{
    error: "An error has occurred. Please try again."
}
```

#### Delete one todo item

##### 1️⃣ Request

```http
DELETE /todo/:id
```

##### 2️⃣ Parameter

| Name  | Description | Required |
| :---: | :---------: | :------: |
|   -   |      -      |    -     |

##### 3️⃣ Response

| Name  |       Description        |
| :---: | :----------------------: |
| error | Message in case of error |

##### 4️⃣ Sample

- Success

```json
HTTP/1.1 204 NO CONTENT
Content-Type: application/json
```

- Fail

```json
HTTP/1.1 500 INTERNAL SERVER ERROR
Content-Type: application/json
{
    error: "An error has occurred. Please try again."
}
```
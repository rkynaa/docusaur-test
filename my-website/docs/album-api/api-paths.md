---
sidebar_label: 'API Paths'
sidebar_position: 1
---

# API Paths

List of paths provided by the API (and with details):

## `/api/actions/`

- `get` 

```yml title: "get"
get:
    operationId: actions_list
    summary: Get Actions List
    description: Retrieves a list of actions.
    tags:
    - actions
    responses: #API's response based on code
```
List of responses are [here](/docs/album-api/api-responses#get).

- `post` 

```yml title: "post"
post:
    operationId: actions_create
    summary: Create an Action
    description: Creates a new action.
    tags:
    - actions
    requestBody:
    content:
        application/json:
        schema:
            $ref: '#/components/schemas/ActionCreate'
        application/x-www-form-urlencoded:
        schema:
            $ref: '#/components/schemas/ActionCreate'
        multipart/form-data:
        schema:
            $ref: '#/components/schemas/ActionCreate'
    responses: #API's response based on code
```
List of responses are [here](/docs/album-api/api-responses#post).

## `/api/actions/{id}/`

- `get`

```yml
get:
    operationId: actions_retrieve
    summary: Get an Action
    description: Retrieves an action by its ID.
    parameters:
    - in: path
    name: id
    schema:
        type: string
        title: UUID
    description: A unique value identifying the action.
    required: true
    tags:
    - actions
    responses: #API's response based on code
```
List of responses are [here](/docs/album-api/api-responses#get-1)

## `/api/actions/{id}/resend/`

- `post`

```yml
post:
      operationId: actions_resend_create
      summary: Resend an Action
      description: Resends a creation request for a specific action using its ID.
      parameters:
      - in: path
        name: id
        schema:
          type: string
          title: UUID
        description: A unique value identifying the action.
        required: true
      tags:
      - actions
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/Action'
          application/x-www-form-urlencoded:
            schema:
              $ref: '#/components/schemas/Action'
          multipart/form-data:
            schema:
              $ref: '#/components/schemas/Action'
      responses: # API's response based on code
```
List of responses are [here](/docs/album-api/api-responses#post-1).
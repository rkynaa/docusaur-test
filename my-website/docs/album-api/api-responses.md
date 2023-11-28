---
sidebar_label: 'API Responses'
sidebar_position: 2
---

# API Responses

API responses for:

## Action (without `id`)

### `get`

```yml title="200"
'200': 
  description: 'Successful Response'
        content:
          application/json:
            schema:
              type: array
              items:
                $ref: '#/components/schemas/Action'
            example:
              - id: Suf5GReGMN8aXmfWo8SSaf
                title: ''
                body: LvarmiKWstWLEnJjvFHArm
                utype: trustee
                created: 2023-10-25 09:02
                album: VoWpVYpUwCgmbub4XAQZg8
                album_name: 'My Archive #1'
                status_label: Pending
                status_name: PENDING
              - id: bkQCBdUbEAprRwEtZYB9Dk
                title: ''
                body: ipoAkk3m26njfojVaVfMSy
                utype: trustee
                created: 2023-10-25 09:02
                album: VoWpVYpUwCgmbub4XAQZg8
                album_name: 'My Archive #1'
                status_label: Pending
                status_name: PENDING
```

```yml title="401"
'401':
  description: Unauthorized
        content:
          application/json:
            schema:
              type: object
              properties:
                detail:
                  type: string
                  description: The error detail.
            example:
              detail: Authentication credentials were not provided.
```

### `post`

```yml title="200"
'201':
  description: 'Successful Response'
  content:
  application/json:
      schema:
      $ref: '#/components/schemas/ActionUpdate'
```

```yml title="401"
'401':
  description: Unauthorized
  content:
  application/json:
      schema:
      type: object
      properties:
          detail:
          type: string
          description: The error detail.
      example:
      detail: Authentication credentials were not provided.
```

## Action (with `id`)

### `get`

```yaml title="200"
'200':
  description: 'Successful Response'
  content:
    application/json:
      schema:
        $ref: '#/components/schemas/Action'
      example:
        id: Suf5GReGMN8aXmfWo8SSaf
        title: ''
        body: LvarmiKWstWLEnJjvFHArm
        utype: trustee
        created: 2023-10-25 09:02
        album: VoWpVYpUwCgmbub4XAQZg8
        album_name: 'My Archive #1'
        status_label: Request Done
        status_name: REQ_DONE
```

```yaml title="401"
'401':
  description: Unauthorized
  content:
    application/json:
      schema:
        type: object
        properties:
          detail:
            type: string
            description: The error detail.
      example:
        detail: Authentication credentials were not provided.
```

```yaml title="404"
'404':
  description: Not Found
  content:
    application/json:
      schema:
        type: object
        properties:
          detail:
            type: string
            description: The error detail.
      example:
        detail: Not found.
```

## Action (with `id` and `resend`)

### `post`

```yml title="204"
'204':
  description: Action Resent Successfully
```

```yml title="401"
'401':
  description: Unauthorized
  content:
    application/json:
      schema:
        type: object
        properties:
          detail:
            type: string
            description: The error detail.
      example:
        detail: Authentication credentials were not provided.
```

```yml title="404"
'404':
  description: Not Found
  content:
    application/json:
      schema:
        type: object
        properties:
          detail:
            type: string
            description: The error detail.
      example:
        detail: Not found.
```
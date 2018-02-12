# flatr API documentation version v0.1

---

## /info

### /info

* **get**: Get info about the API server

## /invitations

### /invitations

* **get**: Get all pending invitations
* **post**: Invite a person via email address. An email with invite code is sent to them

### /invitations/{invitationId}

* **get**: Get information about a specific invitation
* **patch**: Resend invitation email
* **delete**: Delete/Invalidate this invitation

## /tasks

### /tasks

* **get**: List all tasks

* **post**: Add a new task

### /tasks/{taskId}

* **get**: Get detailed information about a task

* **delete**: Delete a task

* **put**: Update a task and return the same one

### /tasks/{taskId}/finish

* **post**: Finish the currently active turn

## /auth

### /auth

* **post**: Authenticate yourself

## /users

### /users

* **get**: Get all users
* **post**: Register a new user

### /users/{userId}

* **get**: Get the user with this Id
responses:
  200:
    body:
      type: User
  404:
    body:
      type: Error
      example: |
        {
          "error": {
            "code": "not_found",
            "message": "The resource you requested could not be found"
          }
        }
  401:
    body:
      type: Error
      example: |
        {
          "error": {
            "code": "unauthorized",
            "message": "You are not authorized to query this information"
          }
        }

* **delete**: Delete the user with this id
responses:
  204:
    description: User was successfully deleted
  404:
    body:
      type: Error
      example: |
        {
          "error": {
            "code": "not_found",
            "message": "The resource you requested could not be found"
          }
        }
  401:
    body:
      type: Error
      example: |
        {
          "error": {
            "code": "unauthorized",
            "message": "You are not authorized to query this information"
          }
        }

### /users/current

* **get**: Get the currently logged in user


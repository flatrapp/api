# flatr API documentation version v0.2.1

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

* **put**: Replace a task and return the same one

### /tasks/{taskId}/finish

* **post**: Finish the currently active turn of this task

## /auth

### /auth

* **post**: Authenticate yourself

## /users

### /users

* **get**: Get all users
* **post**: Register a new user

### /users/{userId}

* **get**: Get the user with this Id

* **delete**: Delete the user with this id

### /users/verify

* **post**: Verify the email of a user by providing the code
sent to him in an email.

### /users/current

* **get**: Get the currently logged in user


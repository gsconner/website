---
permalink: /login-page
layout: base
---

# Login Page

<a href="https://GitHub.com/gsconner/login-page"><strong>GitHub page</strong></a>

<p>A login page supported by a Go backend and a webapp created with ReactJS, with a Postgres database. User data is stored in the database in the form of username/hash pairs. The passwords are hashed and salted via Argon2id. When login credentials are entered on the webapp, they are sent to the Go server via an HTTP POST request, which then compares the user's password to the corresponding entry in the database. If the log-in is successful, the server creates a session and sends back a cookie to the webapp, which is used to verify the ongoing session for future requests. The sessions are also stored in the database and expire after 1 minute. Deployed with Docker Compose.</p>

## Database

<p>This website uses a Postgres database to store authentication credentials and session information. There are two tables, one storing a list of users and their data and another storing session information.</p>

<p>A row in the Users table looks like this</p>

| Userame | Password |
| :--- | :------- |
| User name | Argon2ID hash of user password |

<p>And a row in the Sessions table looks like this</p>

| Username | SessID | Expires |
| :------- | :----- | :------ |
| Name of user this session is for | Random number used to identify sessions uniquely | Time of expiration for session |

## Backend

<p>Made in Go. Communcates with the database and the frontend webapp to form the foundation of the server. Handles security features like hashing passwords. Also features a command line interface so an admin can control the database easily and start/stop the server.</p>

## Frontend

<p>ReactJS webapp that acts as an interface for a user to access the site. Features a frontpage with a login window that takes a username and password to create a user, as well as a sign up page to create an account. Both send HTTP POST requests to the backend server that prompt it to communicate with the database and respond with the results. Once a user is logged in, they can access a blank secure page to indicate they are authenticated. If the session is expired or the user tries to access this secure page without a cookie, they are not granted access and are instead directed back to the frontpage.</p>

## History

<p>Jul 10, 2024: Project uploaded to GitHub.</p>

<p>Jul 13, 2024: Automated Docker Compose deployment process.</p>

<p>Aug 23, 2024: Added clientside Sign Up feature.</p>
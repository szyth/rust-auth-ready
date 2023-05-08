
Hi Rust community, I've written an authentication boilerplate code for your next Rust Server side project.

Features:
- Dockerized Postgres and PgAdmin4 Setup, ( or use your own Hosted Postgres Service )
- User migration script ( up and down )
- Logger Middleware

- [ ] Security
	- [ ] Authentication `jsonwebtoken`
	- [ ] Authorization
	- [ ] Loggers: `env_logger`
	- [ ] Security Headers 
		- [ ] `actix-cors`
	- [ ] Unique IDs instead of guessable IDs `uuid`
	- [ ] Hashed Passwords `argon2, Bcrypt`
- [ ] Database: `sqlx`, uses prepared statments
- [ ] Routes:
  - [ ] /healthchecker
  - [ ] /register
  - [ ] /login
  - [ ] /logout
  - [ ] /users/me


```bash
git clone
cargo install

# setup DB with docker
# this will spin up pgadmin4 
sudo apt install docker-compose
sudo docker-compose up -d

# If schema exists then synchronises local schema with Database Schema
# else pushes schema to Database, 
sqlx migrate run

# login pdAdmin4 at http://localhost:5050, use creds from .env
# Connect to DB using creds from .env, get postgres IP address using below command
sudo docker inspect postgres

# Run live server
cargo watch -q -c -w src/ -x run



```

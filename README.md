**Get started**
# Directory and files
/your_directory

├ apps (empty directory)

├ Dockerfile

├ docker-compose.yaml

├ entrypoint.sh

├ Gemfile

└ Gemfile.lock
# Making Rails Project
To copy the files `Gemfile` and `Gemfile.lock` into the `apps` directory.
## Using Tailwind CSS and Database is MySQL
On terminal
```
docker-compose run web rails new . --css tailwind --force --no-deps --database=mysql
```
# Correcting Procfile.dev
To edit `apps/Procfile.dev`

*before*
```
web: bin/rails server -p 3000
```
*after*
```
web: bin/rails server -p 3000 -b 0.0.0.0
```
# Configure Rails database connection
To edit `apps/config/database.yml`

*before*
```
default: &default
  adapter: mysql2
  encoding: utf8mb4
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  username: root
  password:
  host: localhost
```
*after*
```
default: &default
  adapter: mysql2
  encoding: utf8mb4
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  username: root
  password: password
  host: db
```
# Docker Compose bulid
On terminal
```
docker-compose build
```
# Meke Rails database
On terminal
```
docker-compose run web rails db:create
```
# Start Docker Compose image (Finish)
On terminal
```
docker-compose up
```

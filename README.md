# get started
## directory and files
/your_directory

├ apps (empty directory)

├ Dockerfile

├ docker-compose.yaml

├ entrypoint.sh

├ Gemfile

└ Gemfile.lock
## Making Rails Project on 
To copy the files `Gemfile` and `Gemfile.lock` into the `apps` directory.
### Using Tailwind CSS and Database is MySQL
On teminal
```
docker-compose run web rails new . --css tailwind --force --no-deps --database=mysql
```
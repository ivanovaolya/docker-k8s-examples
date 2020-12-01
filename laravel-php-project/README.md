# Laravel PHP dockerized project sample
Contains samples of https://www.udemy.com/course/docker-kubernetes-the-practical-guide.   
Section 8: A More Complex Setup: Laravel & PHP Dockerized Project.
Only for local development
### Setup
1. Run the composer container using following command to create a project
```
> docker-compose run --rm composer create-project --prefer-dist laravel/laravel .
```
2. Replace ./src/.env credentials for the database (using specified values in ./env/mysql.env)
3. Bring up nginx-server using following command
```
> docker-compose up -d --build nginx-server
```
4. Run artisan container to migrate data
```
> docker-compose run --rm artisan migrate
```
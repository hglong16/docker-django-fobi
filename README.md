# Will be cool

## How to run
```
docker compose up -d --build
```

Server will run in [localhost:8000](http://localhost:8000) and result page is 404

Migrate
```
docker exec -it  django-fobi python manage.py migrate
```



Create superuser
```
docker exec -it django-fobi python manage.py createsuperuser
```


All done
Go to [localhost:8000/admin](http://localhost:8000/admin) login with account you created

Goto [localhost:8000/fobi](localhost:8000/fobi)




Running commands within Docker is a little different than in a traditional Django project. For example, to migrate the new PostgreSQL database running in Docker execute the following command:

```
$ docker-compose exec django python manage.py migrate
```
If you wanted to run createsuperuser you'd also prefix it with docker-compose exec web... so:

```
$ docker-compose exec django python manage.py createsuperuser
```
And so on. When you're done, don't forget to close down your Docker container since it can consume a lot of computer memory.

```
$ docker-compose down
```
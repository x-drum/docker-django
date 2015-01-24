# docker-django
# basic Django container for docker

A Simple image based on CentOS 6 with python 2.7 (SCL repository)

## Usage

With Django embedded webserver:

```bash
$ docker run -ti --rm -v /path/to/myapp/:/data -p 8000:8000 xdrum/django:latest python testproject/manage.py runserver 0.0.0.0:8000
```

With gunicorn and wsgi:

```bash
$ docker run -ti --rm -v /path/to/myapp:/data -p 8000:8000 xdrum/django:latest gunicorn -w 2 --bind=0.0.0.0:8000 testproject.wsgi:application
```

Note that various versions (tag) are currently available from Docker hub, but it's easy to build a specific image using the Dockerfile just passing a different DJANGO_VERSION. 

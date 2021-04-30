## Let's create some basic files that we will use in our program

### Create wsgi.py file

`touch wsgi.py`{{execute}}

`nano wsgi.py`{{execute}}

`from app import app`{{copy}}

`if __name__ == "__main__":`{{copy}}

`    app.run()`{{copy}}

Save File: Control + X, Yes, Enter

### Create app.py file

`touch app.py`{{execute}}

`nano app.py`{{execute}}

`from flask import Flask`{{copy}}

`import socket`{{copy}}

`app = FLask(__name__)`{{copy}}

`@app.route("/")`{{copy}}

`def hello():`{{copy}}

`    return "<h1 style='color:blue'>Hello There from {}!</h1>".format(socket.gethostname())`{{copy}}

`if __name__ == "__main__":`{{copy}}

`    app.run(host ='0.0.0.0')`{{copy}}

Save File: Control + X, Yes, Enter

### Create Dockerfile

`touch Dockerfile`{{execute}}

`FROM python:3.8-slim-buster`{{copy}}

`WORKDIR /app`{{copy}}

`RUN python3 -m venv /.venv`{{copy}}

`RUN /.venv/bin/pip install flask gunicorn`{{copy}}

`CMD ["/.venv/bin/gunicorn", "--bind", "0.0.0.0:5000", "wsgi:app"]`{{copy}}


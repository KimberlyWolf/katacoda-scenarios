# Let's create some basic files that we will use in our program

In order to get Docker to run a specific application, we need to create a few. This includes the Dockerfile and any other files that would be necessary for the application to work. In this instance, we will be creating the two python files: wsgi.py and app.py, and we will create our Dockerfile. To make this process go by quicker, we provided the information needed for each file. Instead of giving you the files themselves, this will give you practice learning how to create files and work inside the editor that is provided at the top of the terminal.

### Let's start with the wsgi.py file

To create the file, run the following command in the terminal:

`touch wsgi.py`{{execute}}

Next, you will go to the editor and click on the newly created wsgi.py file to open it.
If the editor is not working, please run `nano wsgi.py`{{execute}} to open a text editor in the terminal.

Now, we have to copy the following lines into the wgsi.py file.

<pre class="file" data-target="clipboard">
from app import app
if __name__ == "__main__":
    app.run()
</pre>

If you were writing in the terminal, you need to save your file with the following steps: (control + X), Y, Enter.

### Next, let's create the app.py file

To create the file, run the following command in the terminal:

`touch app.py`{{execute}}

Next, you will go to the editor and click on the newly created app.py file to open it.
If the editor is not working, please run `nano app.py`{{execute}} to open a text editor in the terminal.

Now, we have to copy the following lines into the app.py file. 

<pre class="file" data-target="clipboard">
from flask import Flask
import socket

app = Flask(__name__)
@app.route("/")

def hello():
</pre>

After *def hello():* please copy the following line with an indent of approximately 4 spaces: 

`   return "<h1 style='color:blue'>Hello There from {}!</h1>".format(socket.gethostname())`{{copy}}

Then please continue copying the rest of the file:

<pre class="file" data-target="clipboard">    
if __name__ == "__main__":
    app.run(host ='0.0.0.0')
</pre>

If you were writing in the terminal, you need to save your file with the following steps: (control + X), Y, Enter.

### Finally, we can create the Dockerfile

To create the file, run the following command in the terminal:

`touch Dockerfile`{{execute}}

Next, you will go to the editor and click on the newly created Dockerfile to open it.
If the editor is not working, please run `nano Dockerfile`{{execute}} to open a text editor in the terminal.

Now, we have to copy the following lines into the Dockerfile. Each of the lines are on a separate line.

<pre class="file" data-target="clipboard">

FROM python:3.8-slim-buster

WORKDIR /app

RUN python3 -m venv /.venv

RUN /.venv/bin/pip install flask gunicorn

COPY wsgi.py .

COPY app.py .
CMD ["/.venv/bin/gunicorn", "--bind", "0.0.0.0:5000", "wsgi:app"]
</pre>

If you were writing in the terminal, you need to save your file with the following steps: (control + X), Y, Enter.

Once all of these lines are copied over, you may move onto the next step.

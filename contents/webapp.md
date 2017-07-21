# 6. Publish Web Application
First, We start to learn how to create the most simple web application, and then we make an application, ascii art converter, then finally publish it.

## 6.1 We use web frame work, Flask {#flask}
Web frame work helps you to create an web application easily. There are many web frame work. This lecture uses flask, as it is so simple and minimum.

## 6.2 Minimal application: Just say "Hello World!" {#hello}

We launch a server and show just 'Hi'.

```py:sample.py
from flask import Flask
app = FLask(__name__)
@app.route('/'):
    return 'Hello World!'
app.run
```

execute ```python sample.py```.
Now head over to [http://localhost:5000](http://localhost:5000), and you should see your hello world greeting.

![Hi](../img/hi.png)


## 6.3 Change URL (Rooting) {#rooting}

```py:sample.py
from flask import Flask
app = Flask(__name__)

@app.route('/'):
    return 'Index page'

@app.route('hello'):
    return 'Hello world!'

app.run

Visit
http://localhost:5000
http://localhost:5000/hello


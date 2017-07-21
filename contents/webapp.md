# 6. Publish Web Application
First, We start to learn how to create the most simple web application, and then we make an application, ascii art converter, then finally publish it.

## 6.1 What happens when you browse a website? {#client-server}

Browser (client) asks a web server, then the server responses a content. To build a web application or make a website, you set up a server.
![client-server](../images/client-server.png)


## 6.2 We use web frame work, Flask {#flask}
Web frame work helps you to create an web application easily. There are many web frame work. This lecture uses flask, as it is so simple and minimum.

We can say, dijango is to Ruby-on-rails what flask is to sinatra.

## 6.3 Minimal application: Just say "Hello World!" {#hello}

We launch a server and show just 'Hello World'.

sample.py
```py
from flask import Flask
app = FLask(__name__)
@app.route('/'):
    return 'Hello World!'
app.run
```

execute ```python sample.py```.
Now head over to [http://localhost:5000](http://localhost:5000), and you should see your hello world greeting.

![Hi](../img/hello.png)


## 6.4 Change URL (Rooting) {#rooting}

route function is used to bind a url and a function. Here are basic examples.

```py
from flask import Flask
app = Flask(__name__)

@app.route('/'):
    return 'Index page'

@app.route('hello'):
    return 'Hello world!'

app.run
```

Visit
http://localhost:5000
http://localhost:5000/hello


You can put a variable in a URL as ```<variable_name>```. It can be used as a keyword argument to your function.


```py
from flask import Flask
app = Flask(__name__)

@app.route('/user/<username>')
def show_user_profile(username):
    # show the user profile for that user
    return 'User {}'.format(username)

@app.route('/post/<int:post_id>')
def show_post(post_id):
    # show the post with the given id, the id is an integer
    return 'Post {}'.format(post_id)

app.run
```

## 6.5 URL Building

You can get URL from function by url_for


```py
from flask import Flask, url_for
 app = Flask(__name__)
@app.route('/')
def index(): pass

@app.route('/login')
def login(): pass
@app.route('/user/<username>')
def profile(username): pass
with app.test_request_context():
    print(url_for('index'))
    print(url_for('login'))
    print(url_for('login', next='/'))
    print(url_for('profile', username='John Doe'))
```

It shows
```
/
/login
/login?next=/
/user/John%20Doe
```

## 6.6 Create Uploader {#uploader}



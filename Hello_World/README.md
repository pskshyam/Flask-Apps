## Hello World - A Simple Local Flask Application

We'll start by creating a very simple Flask web application. It is a good idea to start with a local version before working on a hosted solution - iron out the easy issues and bugs before they become big headaches once in the cloud.

Let’s create a very simple Flask script straight from the official Flask help docs: http://flask.pocoo.org/

Open a text editor and copy and paste the following code and save it as 'hello.py':

```python
from flask import Flask
app = Flask(__name__)
 
@app.route("/")
def hello():
    return "Hello World!"`
```

### Start a Virtual Environment

It's always a good idea to segregate your development work from the rest of your machine. This ensures that any library you import will be sandboxed to a temporary area (and it is also useful when building "requirements.txt" files if you want to package all your imports in one txt file).

Open a terminal/command window, CD into the same folder where you 'hello.py' lives and enter the following commands to start a virtual environment named simple_flask and pip3 install Flask:

`$ python3 -m venv simple_flask`

`$ source simple_flask/bin/activate`

`$ pip3 install Flask # or: python3 -m pip install Flask`

Once the virtual environment activated, run the following command to start your local web server to run 'hello.py'.

Open a command/terminal window and enter the following command on the Mac:

`$ export FLASK_APP=hello.py`

`$ flask run`

or on Windows:

`$ export FLASK_APP= hello.py`

`$ python -m flask run`

You should see a message in the command window offering a local “HTTP” address to follow.

Copy and drop the local URL address into your browser. You should see a very simple site statign "Hello World!"

### A Faster Way

You have just create a server-generated web page. There is an even easier way you can get your Flask app up-and-running locally by adding the following two lines to the end of your "hello.py" script. This only works for locally servered pages, but allows the script itself to run the instantiated Flask application and allows you to skip the exporting step:

```python
if __name__ == '__main__':
    app.run(debug=True)
```

Save the amended "hello.py" script which should look like:

```python
from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello World!"

if __name__=='__main__':
    app.run(debug=True)
```
    
Go back to your command/terminal window pointing to "hello.py" and enter the shorter version:

`$ python3 main.py`

The line "app.run(debug=True)" will allow you to see errors in the web browser, this can come in handy when you are debugging, but remember to set it to "False" if you are using it publicly!

### Closing Down the Virtual Environment

To stop the web application from serving the 'Hello World!' page, hit 'ctrl-c' in your terminal window. Finally, to turn terminate your virtual environment run the following command:

`$ deactivate simple_flask`

If you go into your folder, you will notice a folder called "simple_flask". That is your virtual environment's folder. You can choose to delete the folder or leave it there. If you leave it there, the next time you start the VE with the same name, it will use that previous instance.

# Flask-Apps

## Introduction

If I had to summarize this repository in one sentence, it would be "to learn how to put your machine learning ideas into your customer’s plate". That’s it. Here we will extend multiple Python ideas into fully interactive web applications, into a format that anybody anywhere can access as long as they have access to a web browser. Our last project will be built around a professional paywall infrastructure so you can control and monetize how and whom can access it.

You should know some python. You’ll be able to pick up flask and PythonAnywhere, but Ideally, you should understand some basic modeling and have some ideas that you want to export to the web.


Our first project, <b>Plagiarism Defender</b>:

Our second project, <b>Worldwide Earthquake Forecaster</b>:

And our third project, a paywall <b>Stock Market Prediction Service</b>:

## Introduction: Tools of the Trade - Python, Flask, Bootstrap, PythonAnywhere, Memberful
### Introduction Python and Flask

<b>Python</b> is an easy to use, very powerful and interpreted general-purpose language. You should have access to a text or Python interpreter, know how to use python 3.x and install/upgrade typical libraries like Numpy, Pandas, and Scikit-learn.

<b>Flask</b> is a lightweight but very powerful server-side web framework and its all in Python! This is why I love Flask so much, not only is it easy to use, it will automatically integrates with any of your Python work with little added headache (in most cases). This makes passing our ML and coding objets to the Flask and, therefore the web, a whole lot easier!

Flask comes with the bare minimum to get a web page publish, if you need additional support, like a database, form controls, etc., you will have to install additional libraries and that is why it is called a light-weight, micro framework. This is also what makes it so easy to use, as you only have to learn a few more tricks, everything else uses the tried-and-true Python libraries we’re already familiar with. <b>Jinja2</b> is the glue betwee flask and HTML, see more at http://jinja.pocoo.org/.

For more information on Flask, check the official Flask documentation at http://flask.pocoo.org/.

### Jupyter Notebooks

A Jupyter notebook is a great tool to experiment with Python concepts quickly and interactively. If you aren't familiar with Jupyter notebooks, they are web-based interactive Python interpreters great for building, tweaking, and publishing anything that makes use of Python scripting. It attaches to a fully functioning Python kernel (make it a Python 3.x one) and can load and run libraries and scripts just like any other interpreter. To install Jupyter notebooks, follow the official docs at http://jupyter.org/install

To use a Jupyter notebook is both easy and powerful at the same time. You simply need to download the notebook to your local machine (it will be the file with a *.ipynb extension), open a command/terminal shell window, navigate to that folder and run the command:

$ jupyter notebook
This command will open a web page showing the content of the folder from where it was launched. You can navigate down a folder structure by clicking on the folder icon right above the file listings.

To open a Jupyter notebook, simply click on any file with the "*.ipynb" extension and you are good to go. If you want to create a brand-new notebook, click on the "new" button at the right of the dashboard next to the refresh button.

For additional information, issues with Jupyter notebooks and attaching kernels, see: http://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/execute.html

### Virtual Environments

Using a virtual environment offers many advantages:

* Creates an environment with no installed Python libraries
* Know exactly which Python libraries are required for your application to run
* Keeps the rest of your computer system safe from any Python libraries you install in this environment
* Encourages experimentation

To start a virtual environment, use the "venv" command. If it isn't installed on your computer, it is recommended you do so (it is available via common installers such as pip, conda, brew, etc). For more information on installing virtual environments for your OS, see the "venv - Creation of virtual environments" user guide: https://docs.python.org/3/library/venv.html

Open a command window and call the Python 3 "venv" function on the command line to create a sandbox area:

`$ python3 -m venv some_name`

To activate it:

`$ source some_name/bin/activate`

Once you are done, you can deactivate your virtual environment with the following command:

`$ deactivate`

### Introduction Bootstrap

Bootstrap is a very powerful tool for front-end web work. It is used by almost 13% of the web according to BuiltWith Trends ( https://trends.builtwith.com/docinfo/Twitter-Bootstrap ). It contains all sorts of great looking styles and behavior for most web tags and controls. By simply linking your web page to the latest Bootstrap CSS will give any boring HTML page an instant and professional-looking makeover. And by putting a little work in using the right templates and tags you can make you site look phenomenal (and we will leverage Bootstrap in each of our web applications).

For additional information and training on Bootstrap, check out the official documents on GetBootstrap.com.

### Introduction PythonAnywhere

PythonAnywhere is a great way to rapidly prototype your Python interactive ideas and models on the Internet. It works quickly and integrates easily with Flask, but also works with all sorts of other frameworks like Django for example. It is free for most of the work presented here except for the paywall portion that will require the cheapest option (its called the Hacker Plan and goes for $5/month).

For additional information and training on Bootstrap, check out the official documents on Pythonanywhere.com.

it doesn't require a credit card to sign up and it can craft a proof-of-concept in no time. Proof is in the pudding; no code is needed for this project as PythonAnywhere already defaults to a "Hello World" example when you spin up an instance.

One more thing, if you want to use another web-hosting platform, you can! Examples will work on any hosting platform as long as it supports Python 3, Flask, and the ability to import Python libraries.

### Introduction Memberful

Memberful is the plugin we will work with and implement here. I personally really like Memberful.com and think it is a great choice for anybody looking for an easy way to manage a paywall section of a website. It offers credit card payment through Stripe.com, offers user-management features, and is tightly integrated within your own web application.

It is also one of the few that will allow you to sell products, sell subscriptions, check if a visitor is a currently paid up customer, all the while giving the impression that you are never leaving your site. Yet no user financial information, credit card processing, etc ever, ever happens on the site!

For additional information see www.memberful.com

Source: https://ml-entrepreneur.teachable.com

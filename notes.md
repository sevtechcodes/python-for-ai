# Python for AI - Dave Ebbelaar
https://python.datalumina.com/

Python is the dominant language in AI research and development: OpenAI, Google, Anthropic (and many others) use Python heavily for prototyping, experimentation, and tooling around their LLMs.
It has also been the backbone of modern machine learning, powering the entire ecosystem of frameworks like TensorFlow, PyTorch, scikit-learn, and XGBoost – the tools that made deep learning and AI breakthroughs possible in the first place.

Master the Python fundamentals essential for AI development:

## Set up like a pro
Master VS Code, Git, and the exact workflow used in real AI companies
## Learn Python fast
Variables, functions, APIs, and everything you need for AI development
## Build AI agents
Apply what you learn to create real AI-powered applications

# Install Python extension
VS Code needs the Python extension to work properly with Python files:
Click the Extensions icon in the left sidebar (it looks like 4 squares)
Search for “Python”
Find the one by Microsoft (it has millions of downloads)
Click “Install”
Wait for installation to complete

This for import settings
VSCode=>Manage=> Settings => Search for “Python Terminal Execute In File Dir”. Check the box to enable it

What this does: When you run a Python file, VS Code will execute it from the file’s directory instead of your workspace root.
Why I recommend it: This prevents common path-related errors. For example, if your script reads a file with open('data.csv'), it will look for the file in the same folder as your script, which is usually what you want. Without this setting, it would look in your project root instead, causing “file not found” errors.

# Additional recommended extensions
While VS Code works great with just the Python extension, here are a few more I recommend:
​
## Pylance
Search for “Pylance” by Microsoft
Provides even better code completion and error detection
Works alongside the Python extension
​
## Jupyter
Search for “Jupyter” by Microsoft
Enables interactive Python mode (we’ll use this later)
Essential for data science and AI work


# Customize appearance (optional)
I’ve been using these settings for years - they’re easy on the eyes:
​
## Theme
Install “Atom One Dark Theme”
Press Ctrl/Cmd + K, then Ctrl/Cmd + T to select it
​
## Icons
Install “Material Icon Theme” by Philipp Kief
Makes file types easier to recognize
​
## Tree indentation
Open Settings (Ctrl/Cmd + ,)
Search for “tree indent”
Change from 8 to 20 for clearer folder structure
View keyboard shortcuts: Open Command Palette (Ctrl/Cmd + Shift + P) and search “keyboard shortcuts”. You can search for any command and change its shortcut by clicking the pencil icon.
​
# Check Python detection
After setting up VS Code:
Press Ctrl + Shift + P (Windows/Linux) or Cmd + Shift + P (macOS)
Type “Python: Select Interpreter”
You should see your Python installation listed
If not, we’ll fix this in the next section

#  Create a main folder for all your Python work
## Create a folder called PythonProjects
## Inside your PythonProjects folder, create a new folder called python-for-ai (all lowercase)
This will be our learning project for this course

You can name your project folder anything you like, but I usually use lowercase letters with dashes (called “kebab-case”) like python-for-ai or my-first-project. This matches how projects appear on GitHub (more on that later).

## Install the correct version on windows package manager
Powershell => winget install Python.Python.3.13.t

Setting => Tree indent => Controls tree indentation in pixels. Update it from 8 to 20, see the change happens to the folders structure on left side.


# Running manually from the terminal
You can run Python files directly in the terminal without using VS Code’s button:
## Make sure you're in the same folder as your file
python hello.py

# Dowload resources: Download all templates, files, and cheat sheets for free
https://datalumina.gumroad.com/l/qlhkx

# Virtual environments
Keep your Python projects organize

## Your Python installation
Remember when we installed Python? That installation lives in a specific folder on your computer:
- Windows: C:\Users\[YourName]\AppData\Local\Programs\Python\Python313\
- macOS: /Library/Frameworks/Python.framework/Versions/3.13/
- Linux: /usr/bin/python3
This is your “system Python” - it’s shared by everything on your computer. 

## The problem with sharing
Imagine you’re working on two projects:
Project A needs version 1.0 of a tool
Project B needs version 2.0 of the same tool
If you install version 2.0 for Project B, you just broke Project A! This is where virtual environments save the day.

## What are virtual environments?
A virtual environment is like a private copy of Python for each project. Think of it as:
A separate folder for each project
Its own Python installation
Its own place to install packages
Complete isolation from other projects
Virtual environments are so important that I create a new one for EVERY project. It’s a Python best practice that will save you from many headaches.
​
## Understanding packages
Before we continue, let’s understand what packages are:
Packages are pre-written code that others have created for us to use. Instead of writing everything from scratch, we can import these packages. For example:
- requests - for downloading web pages
- pandas - for working with data
- openai - for using AI models
Each package has different versions, and different projects might need different versions.

# Create your first virtual environment
Let’s create one for our python-for-ai project. You have two methods:
​
## Method 1: VS Code Command Palette (easier)
Open your project in VS Code
Press Ctrl/Cmd + Shift + P
Type “Python: Create Environment”
Select “Venv”
Select your Python installation
VS Code creates and activates everything for you!
​
## Method 2: Terminal command
Open the terminal in VS Code (View > Terminal)
Make sure you’re in your project folder
Run this command:
Windows
macOS/Linux
python -m venv .venv
What this does:
python -m venv - Run Python’s virtual environment module
.venv - The name of the folder to create (convention is to use “.venv” with a dot)
​
What just happened?
Look at your project folder - you now have a new .venv folder:
python-for-ai/
├── .venv/          # Your virtual environment (hidden folder)
├── hello.py        # Your code
└── python-for-ai.code-workspace
The dot in .venv makes it a hidden folder on Mac/Linux. This keeps your project clean since you don’t need to see this folder often.
This .venv folder contains:
A copy of Python
A place to install packages
Scripts to activate/deactivate
​
## Activate your virtual environment
VS Code makes activation super easy:
Press Ctrl/Cmd + Shift + P to open Command Palette
Type “Python: Select Interpreter”
Choose the one that says .venv (it will show the full path like ./.venv/bin/python)
That’s it! VS Code automatically activates it for you
You’ll know it’s working when you see (.venv) in your terminal:
(.venv) PS C:\...\python-for-ai>
This is my recommended approach. VS Code remembers your choice and automatically activates the environment every time you open the project!
​
Common issues
Command not found

Permission denied

VS Code not recognizing venv

​
# What about Anaconda?
You might have heard of Anaconda - it’s another tool that manages Python environments and packages. It’s popular in the data science world because it comes pre-loaded with many data science packages.
However, I don’t recommend using Anaconda unless you have a specific reason to.
Stick with Python’s built-in virtual environments unless your company or a specific project requires Anaconda. You’ll have a lighter, faster, and simpler setup.
​
What’s next?


 We did something like a local installation of Python. When we run files in the project, it will use the local enviroment we created in the project. 

On the terminal it will look similar to this: (.venv)C:\Users\SevoDevo\Desktop\CODING\PythonProjects\python-for-ai>

# Packages and pip: Understanding Python’s package ecosystem
What are packages?
Packages are collections of Python code that solve specific problems:
- requests - Download web pages and data
- pandas - Work with spreadsheets and data
- numpy - Fast mathematical operations
- openai - Connect to AI models
- beautifulsoup4 - Extract data from websites
Each package is like a toolbox with specialized tools for a specific job.

# Meet pip (Pip Installs Packages) is Python’s package manager

Downloads packages from the internet
Installs them in your environment
Manages versions and dependencies
pip comes with Python, so you already have it! When you activated your virtual environment, you got your own copy of pip.
​
Your first package installation
Now we need to use the terminal - your command center for managing packages.


Install your first package. First lets check our enviroment. Make sure you install in this correct enviroment, similar to (.venv) PS C:\Users\SevoDevo\Desktop\CODING\PythonProjects\python-for-ai> 
Let’s install the requests package: pip install requests

What just happened?
No magic here! When you ran pip install requests, here’s what happened:
pip connected to PyPI (Python Package Index) - a huge website where developers share their code
Downloaded the requests package - just a bunch of Python files that someone else wrote
Saved it in your .venv folder - specifically in .venv/lib/python3.x/site-packages/
That’s it! You just downloaded someone else’s Python code and saved it in your project. Now you can use their code as if you wrote it yourself.
Want to see the actual files? Look in your .venv folder and navigate to lib > python3.x > site-packages > requests. It’s just Python files!

Using installed packages
Now you can use this package in your Python code:
import requests

# Download a web page
response = requests.get("https://api.github.com")
print(response.status_code)  # Should print 200
Without the requests package, downloading web data would require dozens of lines of complex code. With it, it’s just two lines!
​
See what’s installed
To check which packages you have:
pip list
Output:
Package            Version
------------------ --------
certifi           2024.2.2
charset-normalizer 3.3.2
idna              3.6
pip               24.0
requests          2.31.0
urllib3           2.2.0
Notice how installing requests also installed other packages it needs (like urllib3). pip handles this automatically!
​
Install specific versions
Sometimes you need a specific version of a package:
# Install exact version
pip install requests==2.30.0

# Install minimum version
pip install requests>=2.28.0

# Install compatible version
pip install requests~=2.31.0
​
Uninstall packages
Made a mistake or no longer need something?
pip uninstall requests
pip will ask for confirmation before removing it.
​
Where packages come from
pip downloads packages from PyPI (Python Package Index), which hosts over 500,000 packages! Anyone can upload packages there, which is why Python has tools for everything.
​
# Ready for interactive Python
Now that you understand packages, let’s install what we need for interactive Python mode!

Closed the project and reopen it ( because there is a little bit of bug still shows like you did not install request but actually we did. that is why we reopen the project.) Then

PS C:\Users\SevoDevo\Desktop\CODING\PythonProjects\python-for-ai> .\.venv\Scripts\activate
(.venv) PS C:\Users\SevoDevo\Desktop\CODING\PythonProjects\python-for-ai> python hello.py
200

This is the result of the request we create:
import requests
response = requests.get("https://api.github.com")
print(response.status_code)
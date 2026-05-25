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
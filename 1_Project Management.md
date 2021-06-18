# Project Management

## Setting up a Project

### Creating a Virtual Environment

#### Why Create Virtual Environments?

When you a starting a new project, you will want to create a new virtual environment for each project. This is so that you can use different versions of each package for each project. This prevents a change you make in one project from breaking your code in another project you've already built.

For example, if you have used NumPy in multiple projects in the past, but update to a new version for this project you could introduce breaking changes to your old projects without realizing it if you're only using a single version of NumPy on your machine. Additionally, this helps ensure that everyone on your project is using the same version of the package to avoid errors that only exist on one machine. By managing our packages this way, we can ensure that we're only updating packages when we mean to and can make sure that there were no breaking changes when we updated the package rather than finding them next time we try to run our old project.

#### How to Create a Virtual Environment

https://www.jetbrains.com/help/pycharm/creating-empty-project.html

#### Adding a Virtual Environment to an Existing Project

From: https://www.jetbrains.com/help/pycharm/creating-virtual-environment.html#env-requirements

In PyCharm:

1. Press `Ctrl-Alt-S` to open IDE settings and select **Project <project name> | Python Interpreter**. Then click the Gear icon and select **Add**.
2. In the left-hand pane of the **Add Python Interpreter** dialog, select **Virtualenv Environment**.
3. Specify the location of the new virtual environment in the text field, or click the **... icon** and find the location in your file system. Note that the directory where the new virtual environment should be located, must be empty!

Choose the base interpreter from the list, or click Choose the base interpreter and find a Python executable in the your file system.

### Using the Virtual Environment

The virtual environment will automatically open in PyCharm, there is no need to activate it to use it.

You can see that it's working correctly by seeing what packages you have installed in your new environment.

`pip list`

You should have only pip and setuptools installed in a new environment.

Now you can install packages normally with pip:

`pip install numpy`

And now that will appear in the `pip list`.

One useful part of virtual environments is you can export a list of all the packages required for this project into a single file for someone else to install.

`pip freeze > requirements.txt`

To now install all the packages in the `requirements.txt` file onto a new machine we use:

`pip install -r requirements.txt`

### Virtual Environments and Version Control

You don't want to save all the files in your virtual environment to your repo because they will take up too much space. Instead you can just use the requirements.txt file to recreate them on each machine. Make sure to add your `venv/*` to your `.gitignore` file before you commit it. You just want to commit your `requirements.txt` file.

### Project Structure

For consistency, set up your project structure using the template from Cookiecutter Data Science. This consistant structure will encourage good practices and make sure that someone new to your project can quickly onboard.

1. Install Cookiecutter with `pip install cookiecutter`.
2. In the command line, navigate to an empty directory and run `cookiecutter https://github.com/drivendata/cookiecutter-data-science`.
3. Copy these directories and files into your repo.

From: https://drivendata.github.io/cookiecutter-data-science

# Setup Instructions
## Prerequisites
This project uses the following tools:
- **Git**: Git and GitHub will be used for all code housing and version control of this project. If not already installed, the Git command line tools are highly recommended, with installation instructions found [at the official git startup guide](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git). 
    - To get the code from this project, run the following command line function in a folder of your choice:  
    ```git
    git clone https://github.com/McMasterAI/StyleGAN.git
    ```
- **Python 3**: All model code will be done in Python 3. Some application code may be done through JS, but that'll be tackled later on. This will come packaged natively with Ubuntu, but if you are running this on a different OS, download and installation instructions for the latest Python 3 release can be found [at the official python wiki](https://wiki.python.org/moin/BeginnersGuide/Download).
    - **pip** will also be used as a package manager for Python 3, included by default in the Python 3 installation, just make sure you don't do a custom install without it
- **Jupyter Notebook**: All coding will also be done through Jupyter notebooks, for convenience of segmented code running and modification. To install notebooks, you can find instructions [at the official Jupyter install guide](https://jupyter.org/install), although it can be done with the command line:
    ```
    pip install jupyterlab
    ```
    - You can run the program once installed with the `jupyter notebook` command line function, and then navigate to this folder to look at the `ExampleNotebook.ipynb` file through the web interface.
- **ZenHub**: For issue and task management on the project, we will be using GitHub Issues and a free tie-in program called ZenHub. If you've ever worked in the field with software like JIRA or Trello, this will be very familiar. The program links directly with your GitHub account, and can be found [at the official ZenHub site](https://www.zenhub.com/).
    - You can view your issues on this site, but I recommend that you get the web interface, as it will automatically add a tab to the GitHub page for ZenHub issues. 

## Packages
- **ipykernel**: Allows us to use the virtual environment as a kernel in Jupyter
- **keras**: Machine learning library, built on top of TensorFlow and what we will be using for this project
- **matplotlib**: Data visualization library, helpful for viewing loss function results over time, generator image scores against discriminator, etc.
- **numpy**: Math library for Python, will be used for vectorizing and managing input/output of the GAN
- **pylint**: Linting program to aid in keeping code neat and consistent
- **scikit-learn**: Another machine learning library we can play around with while developing
- **scipy**: Environment of Python science libraries, expanding on packages like numpy and matplotlib

## Making a Virtual Environment
For this project, we will be using a virtual environment with the same packages and same package versions across machines, to prevent any issues with different packages or package versions being on each person's machine. To do this, we have a number of steps to go through:

- Python 3 already comes with virtual environments available, so there is no need to install a new pip package for it. There is more explicit documentation [in the python docs page](https://docs.python.org/3/library/venv.html), but this will hopefully provide a quick summary to that. You will want to first to create a new virtual environment at a chosen location, the last part of the path being the venv name:
    ```  
    python -m venv <venv path>
    ```  
    An example of the above could be making a new venv named `newVEnv` (Mac formatting):
    ```
    python -m venv Desktop/myVEnvs/newVEnv
    ```
- Entering your virtual environment depends on the shell you are using. All possible shells are given in the documentation, but for rule of thumb, if you are on windows, you will need to type: 
    ```
    <venv path>\Scripts\activate.bat
    ``` 
    Alternatively, if you are on a Mac/Linux machine, you will want to use:
    ```
    source <venv path>/bin/activate
    ```
    You will know your are in your virtual environment when your input line of your shell starts with your virtual environment name
- To leave a virtual environment, just type `deactivate`

## Installing Necessary Packages and Adding it to Jupyter Notebooks
As stated, we will now install some standardized packages into our virtual environments to use when working on this project, and will also make it available to use within our Jupyter Notebooks:

1. Create a new virtual environment with any name, and enter it using the notes above
2. Navigate to this folder in your command line, and install the project packages onto your virtual environment using the following command:
    ```
    pip install -r requirements.txt
    ```
3. Add your virtual environment to Jupyter using the following command:
    ```
    python -m ipykernel install --name=<venv name>
    ```
4. To confirm this worked, launch `jupyter notebook`, at the top right click `New`, and your virtual environment name should be under the list of notebooks, under `Python 3`
- Note, to see all current Jupyter kernels in your machine, use:
    ```
    jupyter kernelspec list
    ```
    and to remove a given environment, use:
    ```
    jupyter kernelspec uninstall <kernel name>
    ```
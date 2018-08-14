#TIR - Totvs Interface Robot

TIR is a Python module used to create test scripts for web interfaces. With it, you are able to easily create and execute test suites and test cases for any supported Totvs' web interface systems, such as Protheus Webapp.

##Currently Supported Technologies:

- Protheus Webapp

##Documentation
Our documentation can be found in these locations:

- [TIR Documentation](http://localhost:8080)

- [TDN](http://tdn.totvs.com/display/F1/Classe%3A+Webapp)

Our MindMap can be found here:

- [TIR MindMap](http://code.engpro.totvs.com.br/engpro/tir/src/branch/master/docs/Protheus%20Web%20Automation.xmind)

This project has a docs folder with [Sphinx](http://www.sphinx-doc.org/en/master/) files.

Our **create_docs.cmd** script handles the installation of dependencies and creates the offline documentation.

##How to install:

The installation is pretty simple. All you need as a requirement is Python 3.6 and a browser (Mozilla Firefox/Google Chrome) installed in your system.

We provide a handy environment setup script named **install_environment.cmd** inside **scripts** folder that can install/upgrade Python 3.6, Mozilla Firefox and Visual Studio Code, using the Windows package manager called Chocolatey.

After cloning or downloading this repository and having your environment ready, double click on **install_package.cmd**.

OBS: Our installation scripts will install our package in the current active Python instance. If you're willing to use Python's virtual environment in your machine, please be sure that the virtual environment is active before installing our package.

##Config file

The environment must be configured through a *config.json* file.
You can find one to be used as a base in this repo. To select your file, you can either put it in your workspace or pass its path as a parameter of any of our classes' initialization.

```python
#To use the config file in the same workspace directory
test_helper = Webapp()

#To use a custom path for your config.json
test_helper = Webapp("C:\PATH_HERE\config.json")
```

##Usage:

After the module is installed, you could just import it on your Test Case.
See the following example:

```python
# Import from our package the class you're going to use
from tir import Webapp

test_helper = Webapp()
test_helper.Setup('SIGAGCT','10/08/2017','T1','D MG 01 ','05')
test_helper.Program('CNTA010')

test_helper.SetButton('Cancelar')
test_helper.AssertTrue()

test_helper.TearDown()
```

##Contributing

In order to contribute be sure to follow the [Contribution](CONTRIBUTING.md) guidelines.
## How to create a virtualenv

### Install virtualenv in os
```bash
sudo apt-get install python-virtualenv
sudo apt-get install python-pip
sudo apt-get install python-tk
```

### Create virtualenv with python2.7
```bash
virtualenv mykeras2
```

### Create virtualenv with python3
```bash
virtualenv -p python3 mykeras3
```

## Manage virtualenvs

Create a requirements.txt file which contains a simple
list of all packages in the current environment and
their respective versions.
```bash
pip freeze > requirements.txt
pip install -r requirements.txt
```

### Install folder structure for ML projects
```bash
pip install cookiecutter
cookiecutter https://github.com/drivendata/cookiecutter-data-science
```
### Useful linux commands for handling files

To display the largest files for humans.
```bash
du -hs * | sort -rh | head -5
```




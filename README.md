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

To display the largest files (human-readable):
```bash
du -hs * | sort -rh | head -5
```

To find files with a specific pattern:
```bash
find . -type f -name '*_2019_07_*'
```

To find files with a specific pattern and remove them
```bash
find . -type f -name '*_2019_07_*' -print0 | xargs -r0 rm --
```

To check the size of group of files:
```bash
find . -type f -name '*_2020_08_*' -print0 | du -ch --files0-from=-
```

To find files associated with a month and year:
```bash
month="Oct-2019"
find . -newermt "01-$month -1 sec" -and -not -newermt "01-$month +1 month -1 sec" > files_to_copy
```

To find files associated with a day, month, year:
```bash
ls -ltr | awk '$8 == 2019 && $6 == "Nov" && $7 >=01 && $7 <= 12 {print "./"$9}' > files_to_copy
```

To download files from server according to list of files:
```bash
rsync -a --info=progress2 --files-from=files_to_copy user@<ip_server>:/var/www/drscratchv3/uploads .
```




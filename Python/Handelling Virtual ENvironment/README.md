#Virtual Environment


###Installing on windows:
```
py -m pip install --user virtualenv
```


###Installing on Linux:
```
python3 -m pip install --user virtualenv
```


###Creating virtual environment:

Linux:
```
python3 -m venv env
```

Windows:
```
py -m venv env
```


### Activating venv

Linux:
```
source env/bin/activate
```

Windows:
```
.\env\Scripts\activate
```


### Exiting venv

```
deactivate
```


### Installing from requirements.txt

```
pip install -r requirements.txt
```


### Adding dependencies to requirement.txt and making requirements.txt if not exists

```
pip freeze
```
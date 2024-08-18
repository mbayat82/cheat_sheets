# Pyenv
### Verify Installation
```
pyenv --version
pyenv install --list
```
### Install a Python Version
```
pyenv install 3.8.10
```
### Set Global Version
```
pyenv global 3.9.5
```
### Set Local Version
```
cd myProject
pyenv local 3.9.5
```

# Virtual Environment
### Create venv
```
mkdir my_project
cd my_project
python -m venv venv
```
For MacOS
```
source venv/bin/activate
```
For Windows
```
venv\Scripts\activate
```
### Create Reqruiment File
```
touch requirements.txt
pip install requests
pip freeze > requirements.txt
```
### Install from Requirement File
```
pip install -r requirements.txt
```

# CSV to DICT
```
import csv
with open('data.csv', 'r') as file:
    csv_reader = csv.DictReader(file)
    data = [row for row in csv_reader]
for record in data:
	print(record)
```

# API with JSON
```
import requests

try:
    head = {"Authorization":"Bearer "+os.environ['CF_API_TOKEN']+""}
except:
    print("ERROR: no enviromental variable CF_API_TOKEN")
    sys.exit(0)

accounts_url = f"https://api.cloudflare.com/client/v4/accounts/"
session = requests.Session()

r = session.get(accounts_url, headers=head)
r_json = json.loads(r.text)
for account in r_json['result']:
	print(account['name'])
```
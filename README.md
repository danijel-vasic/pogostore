# Intuity Medical - Registation api

Flask Api for handling custom registration app

## Requirements

## Install
####Install pyenv
```
brew update
brew install pyenv
brew install pyenv-virtualenv
```
Add pyenv to shell in either `~/.zshrc` or `~/.bash_profile`
```
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```

####Install Mysql Client
```
brew install mysql-client
```

Add Mysql Client to path with

zsh: `echo 'export PATH="/usr/local/opt/mysql-client/bin:$PATH"' >> ~/.zshrc`
bash: `echo 'export PATH="/usr/local/opt/mysql-client/bin:$PATH"' >> ~/.bash_profile`

Restart shell or source your new config with `source ~/.zshrc` or `source ~/.bash_profile`


####Install Python 3.6
```
pyenv install 3.6.8
```

Create virtual environment
```
pyenv virtualenv 3.6.8 backinstock
pyenv activate backinstock
```

Install Requirements
```
pip install -r requirements.txt
```

## Local Development

### App Credentials

Copy the `.env.example` and update the values for shopify store, sailthru environment and Database.

```
cp .env.example .env
```

Add a random string to `SECRET_KEY`

### Initialize the database
```
flask db init
```
Run migrations
```
flask db upgrade
```

### Run the server
```
flask run
```

## Deploy
Copy the `zappa_settings.json.example`

```
cp zappa_settings.json.example zappa_settings.json
```

Update `aws_environment_variables` in  `zappa_settings.json`

Deploy api to AWS Lambda.

```
zappa deploy
```

Update api in AWS Lambda.

```
zappa update
```
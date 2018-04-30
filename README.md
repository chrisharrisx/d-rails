# Docker Rails

- `docker-compose run rails_app rails new . --force --database=postgresql`
- `sudo chown -R $USER:$USER .`
- `docker-compose build`
- Replace the contents of config/database.yml with ```
default: &default
adapter: postgresql
encoding: unicode
host: db
username: postgres
password:
pool: 5

development:
<<: *default
database: myapp_development


test:
<<: *default
database: myapp_test
```
- `docker-compose up`
- `docker-compose run rails_app rake db:create`

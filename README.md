# namesdb-datasette - Names Registry Datasette

View multiple SQLite3 databases in one Datasette install.

## Basic Installation
```
sudo apt install git python3-venv python3-pip supervisor nginx ufw
git clone https://github.com/denshoproject/namesdb-datasette
sudo mv namesdb-datasette /opt/
cd /opt/namesdb-datasette/
python3 -m venv venv/namesdbdatasette
source venv/namesdbdatasette/bin/activate
pip install -U -r requirements.txt
sudo cp conf/supervisor.conf /etc/supervisor/conf.d/namesdbdatasette.conf
sudo service supervisor restart
sudo supervisorctl status
```

## Nginx
Note: this is the same Nginx conf as `namesdb-editor`.
```
sudo cp conf/nginx.conf /etc/nginx/sites-enabled/namesdbeditor.conf
sudo service nginx restart
```
http://namesdbeditor.local/datasette/

## Databases

Just drop database files in `/opt/namesdb-datasette/db/` and then restart
`supervisor`:
```
sudo supervisorctl reload
```

# Frappe IO Full Stack App

## Steps to Install
1. Run below commands to setup environment
```
sudo apt update
sudo apt install git redis-server libmariadb-dev mariadb-server mariadb-client pkg-config
#sudo mariadb-secure-installation    # only if no root password promt
sudo apt install xvfb libfontconfig
sudo dpkg -i wkhtmltox_file.deb   # Download file from https://wkhtmltopdf.org/downloads.html


curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash
nvm install 24
npm install -g yarn


curl -LsSf https://astral.sh/uv/install.sh | sh
uv python install 3.14 --default
```

2. Install bench
```
uv tool install frappe-bench
bench --version

mkdir ~/frappe
cd ~/frappe
bench init frappe-bench
bench start
```

3. Create an App
```
bench new-app library_management
bench new-site library.localhost
bench --site site_name add-to-hosts
bench --site library.localhost install-app library_management
bench --site library.localhost list-apps
```

4. All Console commands
```
bench --site library.localhost console  # Python console
bench --site library.localhost mariadb  # Sql console
bench --site library.localhost backup   # DB Backup

```

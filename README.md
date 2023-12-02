## Backup step:

1. Clean ssh
```
cd ./.ssh;del -r -f *
```

2. Connect ssh
```
ssh root@195.35..
```
After that, enter password

3. Update apt
```
sudo apt update -y && apt upgrade -y
```

4. Install python3 and the necessary components
```
sudo apt install python3-pip  wget python3-dev python3-venv python3-wheel libxml2-dev libpq-dev libjpeg8-dev liblcms2-dev libxslt1-dev zlib1g-dev libsasl2-dev libldap2-dev build-essential git libssl-dev libffi-dev libmysqlclient-dev libjpeg-dev libblas-dev libatlas-base-dev -y
```

5. Install and Configure PostgreSQL
```
sudo apt install postgresql -y
```

6. create a new PostgreSQL user and name that user odoo15
```
sudo su - postgres -c "createuser -s odoo15"
```

7. Create a system user
```
sudo useradd -m -d /opt/odoo15 -U -r -s /bin/bash odoo15
```

8. Install wkhtmltopdf
```
sudo apt-get install wkhtmltopdf -y
```

9. Access the user odoo15
```
su - odoo15
```

10. Download the Odoo15 repository from Github
```
git clone https://www.github.com/odoo/odoo --depth 1 --branch 15.0 /opt/odoo15/odoo
```

11. Move into the odoo15 directory
```
cd /opt/odoo15
```

12. Create a virtual environment by the command
```
python3 -m venv myodoo15-venv
```

13. Activate the virtual environment
```
source myodoo15-venv/bin/activate
```

14. In the virtual environment, you install the necessary python modules
```
pip3 install wheel
pip3 install -r odoo/requirements.txt
pip3 install pysftp==0.2.9
```
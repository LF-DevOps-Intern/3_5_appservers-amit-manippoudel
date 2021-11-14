# Gunicorn
    Create Django starter project in a separate virtual environment.
    Deploy the 3 instance of application using Gunicorn in 8089 port.
    Dump access log in a file in non-default pattern.
    Dump error log in a file.


> For creating Virtualenv:
    virtualenv {virtual_enviroment_name}

    > For activating Virtualenv
        - source venv/bin/activate
    
    >  Installing required dependencies in Virtualenv using pip install:
        asgiref==3.4.1
        Django==3.2.9
        gunicorn==20.1.0
        psycopg2-binary==2.9.2
        pytz==2021.3
        sqlparse==0.4.2

    > Updating settings.py file to include the IP for allowed host in file and adding static url dir for Django.

    > sudo ufw allow 8089 #to allow port in firewall.

> Running 3 instances of DJango application


    gunicorn django_deploy_lf.wsgi --workers 3 --daemon --bind :8089

> For access log and error log we can pass the flaf --access-logfile & --error-logfile to capture the log

    gunicorn django_deploy_lf.wsgi  --bind 0.0.0.0:8089 -w 3 --capture-output --access-logfile access.log --error-logfile error.log -D



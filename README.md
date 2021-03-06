Up to date development : https://github.com/Phoenix1708/OpenAcademy_OpenStack_Flyway

Flyway
======

Forklift Resources from One Cloud to Another which can be executed in Ubuntu, Debian operating systems

    1 - Users and their respective roles in projects
    2 - Projects with related metadata
    3 - Project quotas
    4 - Private Keys
    5 - Images/Snapshots and their metadata.
    6 - VMs
    7 - Flavor mappings
    
Configuration
=============

Some dependencies of Flyway have to be installed before running it. Please execute the below command in the 'preconfiguration' directory of project to install relevant libraries if they haven't been installed before:
    
    1 - sudo pip install -r requirements.txt
	2 - sudo sh pythonutils.sh

Notes:
Below is the solution to one of the common error encounted during the installation of MySQLdb on Mac OS X:
http://stackoverflow.com/questions/22313407/clang-error-unknown-argument-mno-fused-madd-python-package-installation-fa

Usage
=====

Execute the command below in the 'flyway' directory of project:
    
    python main.py -src sourcecloudname -dst targetcloudname

which retrieves the corresponding cloud infos from Flyway database.
    
If sourcecloudname or targetcloudname does not exist in the Flyway database, please configure new clouds in the flyway.conf file and execute the command below, the new clouds will be automatically stored in Flyway database for future migration.
    
    python main.py --config-file ./etc/flyway.conf

For running the simple web interface, please execute the following command (inside "web" directory):

    python manage.py runserver
    
Or via Pycharm with same parameter and visit the address shown at line stating "Starting development server at <address>" plus "/flyway_test/" e.g (http://127.0.0.1:8000/flyway_test/) from a web browser. Note: source and target OpenStack deployments must be accessible before running the UI. (More improvement will be introduced later)

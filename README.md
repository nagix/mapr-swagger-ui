# mapr-swagger-ui

## How to setup

Download and unzip the swagger-ui zip file and copy the dist diectory to the MCS webapp directory (as `root` user on MCS node).
    
    wget https://github.com/swagger-api/swagger-ui/archive/v2.2.3.zip
    unzip v2.2.3.zip
    cd swagger-ui-2.2.3
    cp -r dist /opt/mapr/adminuiapp/webapp/swagger-ui

Download and unzip the mapr-swagger-ui zip file and copy `update_yaml`, `mapr.yaml` and `css/mapr.css` to the MCS webapp directory.

    wget https://github.com/nagix/mapr-swagger-ui/archive/master.zip
    unzip master.zip
    cd mapr-swagger-ui-master
    cp -r update_yaml mapr.yaml css /opt/mapr/adminuiapp/webapp/swagger-ui

Replace the default css and Swagger definition file.

    cd /opt/mapr/adminuiapp/webapp/swagger-ui
    sed -e 's/screen\.css/mapr.css/' -e 's/".*\.json"/"mapr.yaml"/' -i index.html

Go to `https://<MCS node>:8443/swagger-ui/`

## How to update the Swagger definition file

Run the following command (requires the `python-pyquery` rpm/deb package). This command updates the Swagger definition file based on the latest MapR online document on maprdocs.mapr.com.

    cd /opt/mapr/adminuiapp/webapp/swagger-ui
    ./update_yaml

# mapr-swagger-ui

## How to setup

Run the following commands (as `root` user on MCS node)
    
    wget https://github.com/swagger-api/swagger-ui/archive/v2.2.2.zip
    unzip v2.2.2.zip -d /tmp
    cp -r /tmp/swagger-ui-2.2.2/dist /opt/mapr/adminuiapp/webapp/swagger-ui
    cd /opt/mapr/adminuiapp/webapp/swagger-ui
    sed -e 's/".*\.json"/"mapr.yaml"/' -i index.html

Copy `update_yaml` and `mapr.yaml` to `/opt/mapr/adminuiapp/webapp/swagger-ui`

Go to `https://<MCS node>:8443/swagger-ui/`

## How to update YAML file

Run the following commands (requires the `python-pyquery` rpm package)

    cd /opt/mapr/adminuiapp/webapp/swagger-ui
    ./update_yaml

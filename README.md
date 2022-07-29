# squid-Helm-chart

### Squid Helm Chart with Authentication Enabled
Run the CMD -
> helm upgrade  --install squid . --namespace default

##### Test the Working of Squid with below cmd
> curl -x http://username:pasword@node-ip:node-port -I https://google.com

##### Configuring values.yaml

*    To Disable squid proxy basic auth, set enable_auth to false or viceversa.
*    Add IP(s) in proxy.clients to allow browsing from
*    Add domain in proxy.domains to block it accessing from squid
*    Squid will run on port defined in service.port

### Create the basic Authentication before running the helm chart
Create a flat-file using htpasswd for basic authentication if enable_auth is set to true.
###### Run this if file not present or need to create a single user
> htpasswd -c .auth_conf < user_name >
###### Run below cmd to add another user in existing file
> htpasswd .auth_conf < user_name >

Note:- If htpasswd is not present, install httpd-utils or apache2-utils
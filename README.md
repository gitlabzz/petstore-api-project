### command line invoke maven

#### Enable Debug logs for apim-cli

`export MAVEN_OPTS='-Xms64m -Xmx256m -Dlog4j.configurationFile=src/main/resources/log4j/log4j2.xml'`

#### Folder containing 'DEV' API Manager connectivity setup via environment variables passed from command line or Jenkins pipeline

- APIM_HOST
- APIM_ADMIN_USER
- APIM_ADMIN_PASSWORD

export AXWAY_APIM_CLI_HOME=src/main/environments/dev

#### Commandline setup, set variables for build

- `export APIM_HOST=dev.apim.demo.bct`
- `export APIM_ADMIN_PASSWORD=changeme`
- `export APIM_ADMIN_USER=apiadmin`

### For Jenkins setup, set environment variables

based on branch, the APIM_*_HOST is mapped to APIM_HOST.

- APIM_DEV_HOST
- APIM_PROD_HOST
- APIM_SIT_HOST
- APIM_UAT_HOST

define credentials for supported environments, the pattern is 'APIM_ADMIN_USERNAME_PASSWORD_*_ENV'

- APIM_ADMIN_USERNAME_PASSWORD_DEV_ENV
- APIM_ADMIN_USERNAME_PASSWORD_SIT_ENV
- APIM_ADMIN_USERNAME_PASSWORD_UAT_ENV
- APIM_ADMIN_USERNAME_PASSWORD_PROD_ENV

#### Import into API Manager

`mvn clean install exec:java@import-api`

#### List published APIs

`mvn clean install exec:java@list-api`za
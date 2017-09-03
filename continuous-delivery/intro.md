In this lab you will learn how to manage application configuration and how to provide environment 
specific configuration to the services.

## Application Configuration

Applications require configuration in order to tweak the application behavior 
or adapt it to a certain environment without the need to write code and repackage 
the application for every change. These configurations are sometimes specific to 
the application itself such as the number of products to be displayed on a product 
page and some other times they are dependent on the environment they are deployed in 
such as the database coordinates for the application.

The most common way to provide configurations to applications is using environment 
variables and external configuration files such as properties, JSON or YAML files.

configuration files and command line arguments. These configuration artifacts
should be externalized form the application and the docker image content in
order to keep the image portable across environments.

OpenShift provides a mechanism called [ConfigMaps](https://docs.openshift.com/container-platform/3.6/dev_guide/configmaps.html) 
in order to externalize configurations 
from the applications deployed within containers and provide them to the containers 
in a unified way as files and environment variables. OpenShift also offers a way to 
provide sensitive configuration data such as certificates, credentials, etc to the 
application containers in a secure and encrypted mechanism called Secrets.

This allows developers to build the container image for their application only once, 
and reuse that image to deploy the application across various environments with 
different configurations that are provided to the application at runtime.
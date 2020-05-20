<p align="center">
	<img src="http://www.efsa.europa.eu/profiles/efsa/themes/responsive_efsa/logo.png" alt="European Food Safety Authority"/>
</p>

# Http Manager
This maven project module, written in Java, can be used for managing the http connections (for now it is possible to call get requests).
In addition, it is possible to configure a proxy if present.

## Dependencies
All project dependencies are listed in the [pom.xml](pom.xml) file.

## Import the project
In order to import the project correctly into the integrated development environment (e.g. Eclipse), it is necessary to download the project together with all its dependencies.
The project and all its dependencies are based on the concept of "project object model" and hence Apache Maven is used for the specific purpose.

_Please note that the "SWT.jar" and the "Jface.jar" libraries (if used) must be downloaded and installed manually in the Maven local repository since are custom versions used in the tool ((install 3rd party jars)[https://maven.apache.org/guides/mini/guide-3rd-party-jars-local.html])._

## Proxy configuration
The proxy can be configured in the "config/proxyConfig.xml" file. In particular, Proxy.Mode defines which is the method to detect the proxy. It can assume the following values:
* NO_PROXY: no proxy is actually used;
* AUTO: the proxy is automatically detected and, if not present, NO_PROXY is used;
* MANUAL: the proxy can be manually set (hostname and port are required in the Proxy.ManualHostName and Proxy.ManualPort fields)

_Note that since the project can be wrapped inside an installer (i.e. the application is updated), the program first checks if the proxy configuration are present in the parent (../config/proxyConfig.xml). 
Only if they are not present there it will use the configuration present in config/proxyConfig.xml!_
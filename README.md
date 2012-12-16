# Remember Me authentication module example

This authentication module provides an example way to implement remember me functionality (persistent cookies)

## How to install the module

Open Up the administration console and go to Configuration -> Servers and sites -> Default Server Config -> Advanced tab and set the following property:
ssoadm.disabled=false

* Visit /openam/ssoadm.jsp?cmd=create-svc page, and upload the content of amAuthRememberMe.xml
* Visit /openam/ssoadm.jsp?cmd=register-auth-module page and enter:
org.forgerock.openam.examples.rememberme.RememberMe
* Restart the container
* Go to Access Control -> realm -> Authentication page and create a new Authentication chain containing:
RememberMe SUFFICIENT
DataStore REQUIRED
* In this new chain also set the following Post Authentication Processing class:
org.forgerock.openam.examples.rememberme.RememberMePAP
* change the Organization Authentication Configuration to  this new chain

## License

Everything in this repository is licensed under the ForgeRock CDDL license: http://forgerock.org/license/CDDLv1.0.html

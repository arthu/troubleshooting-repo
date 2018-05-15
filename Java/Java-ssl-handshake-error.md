
# Java Certification Error =

## Error
sun.security.validator.ValidatorException: `PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target`

## The Cause:
When an application attempts to connect to another application over https, it needs to trust the other application. i.e. Java application will only trust certificates that are signed by those CA certificate or public certificates that exist within that keystore ( $JAVA_HOME/lib/security/cacerts). 

This problem comes from a certificate that is either self-signed (a CA did not sign it) or the certificate chain does not exist within the Java keystore. Subsequently, your application doesn't trust the certificate and fails to connect to the application.


## Resolution:

1. run **InstallCert.jar** to generate **jssecacerts** file (a Java program written by Andreas Sterbenz, and posted on a blog in Oct, 2006, 
https://blogs.oracle.com/gc/entry/unable_to_find_valid_certification )

`Java -jar InstallCert.jar maven.apache.org:443`

2. copy jssecacerts to the java security folder

`JAVA_HOME\lib\security`


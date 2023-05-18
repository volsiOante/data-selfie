## How to fix the error "Cannot find NT Oracle Server DLL <oci.dll>" in SAP Data Services</oci.dll>

  
# How to fix the error "Cannot find NT Oracle Server DLL <oci.dll>" in SAP Data Services</oci.dll>
 
If you are using SAP Data Services (DS) to connect to an Oracle database, you may encounter the following error when executing a job:
 
## bods cannot find nt oracle server dll oci.dll


[**Download**](https://walllowcopo.blogspot.com/?download=2tKGG7)

 

> Cannot find NT Oracle Server DLL <oci.dll>. Please make sure that Oracle has been installed and the PATH variable points to the correct lib directories.</oci.dll>

This error indicates that DS cannot locate the Oracle client library (OCI.DLL) that is required to communicate with the Oracle database. To resolve this issue, you need to check the following:
 
- Make sure that you have installed the Oracle client software on the same machine where DS is running. The Oracle client version should match or be higher than the Oracle database version. For example, if you are connecting to an Oracle 11g database, you should install the Oracle 11g client or higher.
- Make sure that the ORACLE\_HOME environment variable is set correctly and points to the directory where the Oracle client software is installed. For example, if you have installed the Oracle 11g client in C:\oracle\client\_11g, then ORACLE\_HOME should be set to C:\oracle\client\_11g.
- Make sure that the PATH environment variable contains the directory where the OCI.DLL file is located. This directory is usually under ORACLE\_HOME\bin. For example, if ORACLE\_HOME is C:\oracle\client\_11g, then PATH should include C:\oracle\client\_11g\bin. You can check the PATH variable by opening a command prompt and typing echo %PATH%. You can also use the command where OCI.DLL to verify if the correct OCI.DLL file is found.

If you have made any changes to the environment variables, you need to restart DS for them to take effect. You can also test the connection to the Oracle database using a tool like SQL\*Plus or SQL Developer before running the job in DS.
 
For more information, please refer to the following SAP Knowledge Base Articles:

- [Cannot find NT Oracle Server DLL <oci.dll>. Ensure that Oracle has been installed and the PATH variable points to the correct | SAP Community</oci.dll>](https://answers.sap.com/questions/10201623/cannot-find-nt-oracle-server-dll-ocidll-ensure-tha.html)
- [1667572 - ERROR: Cannot find NT Oracle Server dll <oci.dll> - SAP Data Services 4.x | SAP Knowledge Base Article</oci.dll>](https://userapps.support.sap.com/sap/support/knowledge/en/1667572)
- [Cannot find NT Oracle Server DLL <oci.dll>. Ensure that Oracle ... - SAP</oci.dll>](https://answers.sap.com/questions/10072816/cannot-find-nt-oracle-server-dll-ocidll-ensure-tha.html)

In some cases, you may also need to check the registry settings for the Oracle client software. You can use the regedit tool to open the registry editor and navigate to the following key:

> HKEY\_LOCAL\_MACHINE\SOFTWARE\ORACLE

Under this key, you should see a subkey with the name of your Oracle client version, such as KEY\_OraClient11g\_home1. This subkey should have a string value named ORACLE\_HOME that matches the ORACLE\_HOME environment variable. If this value is missing or incorrect, you need to edit it or create it manually.
 
Another possible cause of the error is that you are using a 64-bit version of DS and a 32-bit version of Oracle client, or vice versa. DS and Oracle client must have the same architecture (32-bit or 64-bit) to work properly. You can check the architecture of DS by looking at the file name of the executable (AL\_Designer.exe for 32-bit or AL\_Designer64.exe for 64-bit). You can check the architecture of Oracle client by looking at the size of the OCI.DLL file (around 2 MB for 32-bit or around 8 MB for 64-bit).
 
If you need to install a different version of Oracle client, you should uninstall the existing one first and then install the new one. You should also update the environment variables and registry settings accordingly.
 0f148eb4a0

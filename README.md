## Steps to generate SSL certificate

1. Install **OPENSSL**. If you are on MAC OS, OPENSSL, you already have it installed. For Windows or Linux users, you can use url _https://slproweb.com/products/Win32OpenSSL.html_

2. Verify OPENSSL has been installed with command **openssl**

3. Launch terminal/ cmd. In the project root directory, create a directory **cert** and cd into the directory

4. _Generate private key_ :
To create a **rsa key file**, run command **openssl genrsa -out key.pem**

5. _Create a CSR (Certificate Signing Request)_ :
To generate a **certificate signing request file** using the above key file, run command **openssl req -new -key key.pem -out csr.pem**
Note - If you run into issues regarding **Can't open \openssl.cnf for reading, No such file or directory**, try setting path of **OPENSSL_CONF** env variable. Example - **set "OPENSSL_CONF=C:\Program Files\OpenSSL-Win64\bin\openssl.cfg"**

6. _Generate SSL certificate from CSR_ :
To generate a To generate a **certificate file** run command - **openssl x509 -req -days 3650 -in csr.pem -signkey key.pem -out cert.pem**
Note - x509 is format public key certificate

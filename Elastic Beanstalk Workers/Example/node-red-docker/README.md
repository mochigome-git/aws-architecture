## Folder Structure

1. Create a folder named `certs`:
    ```bash
    mkdir certs
    ```

2. Create files `cert.csr`, `cert.pem`, and `key.pem` inside the `certs` folder:
    ```bash
    cd certs
    touch cert.csr cert.pem key.pem
    ```

## Creating `.htpasswd`

1. At the top level of your project path, create a `.htpasswd` file containing username and password:
    - First, make sure you have `htpasswd` utility installed. If not installed, you can install it using:
        ```bash
        sudo apt-get install apache2-utils
        ```
    - Now, you can create the `.htpasswd` file. Replace `username` and `password` with your desired credentials:
        ```bash
        htpasswd -c .htpasswd username
        ```
    - You'll be prompted to enter the password for the username you specified.

    **Note:** If you need to add more users to the `.htpasswd` file without recreating it, remove the `-c` flag from the command.


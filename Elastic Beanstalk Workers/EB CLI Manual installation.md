# Installing Python, pip, and the EB CLI on Linux
#### copied from official AWS documentation 18/3/2024

The EB CLI requires Python 2.7, 3.4, or later. If your distribution didn't come with Python, or came with an earlier version, install Python before installing pip and the EB CLI.

## Install Python 3.7 on Linux

1. Determine whether Python is already installed.

    ```bash
    $ python --version
    ```

2. If Python 2.7 or later isn't installed, install Python 3.7 using your distribution's package manager. The command and package name vary:

    - On Debian derivatives, such as Ubuntu, use APT.

        ```bash
        $ sudo apt-get install python3.7
        ```

    - On Red Hat and derivatives, use yum.

        ```bash
        $ sudo yum install python37
        ```

    - On SUSE and derivatives, use zypper.

        ```bash
        $ sudo zypper install python3-3.7
        ```

3. To verify that Python installed correctly, open a terminal or shell and run the following command.

    ```bash
    $ python3 --version
    Python 3.7.3
    ```

## Install pip and the EB CLI

1. Download the installation script from pypa.io.

    ```bash
    $ curl -O https://bootstrap.pypa.io/get-pip.py
    ```

2. Run the script with Python.

    ```bash
    $ python3 get-pip.py --user
    ```

    Invoking Python version 3 directly by using the python3 command instead of python ensures that pip is installed in the proper location, even if an earlier version of Python is present on your system.

3. Add the executable path, ~/.local/bin, to your PATH variable.

    To modify your PATH variable (Linux, Unix, or macOS):

    - Find your shell's profile script in your user folder. If you are not sure which shell you have, run `echo $SHELL`.

        ```bash
        $ ls -a ~
        .  ..  .bash_logout  .bash_profile  .bashrc  Desktop  Documents  Downloads
        ```

        - Bash – .bash_profile, .profile, or .bash_login.
        - Zsh – .zshrc
        - Tcsh – .tcshrc, .cshrc or .login.

    - Add an export command to your profile script. The following example adds the path represented by LOCAL_PATH to the current PATH variable.

        ```bash
        export PATH=LOCAL_PATH:$PATH
        ```

    - Load the profile script described in the first step into your current session. The following example loads the profile script represented by PROFILE_SCRIPT.

        ```bash
        $ source ~/PROFILE_SCRIPT
        ```

4. Verify that pip is installed correctly.

    ```bash
    $ pip --version
    pip 8.1.2 from ~/.local/lib/python3.7/site-packages (python 3.7)
    ```

5. Use pip to install the EB CLI.

    ```bash
    $ pip install awsebcli --upgrade --user
    ```

6. Verify that the EB CLI installed correctly.

    ```bash
    $ eb --version
    EB CLI 3.14.8 (Python 3.7)
    ```

## Additional Notes

To upgrade to the latest version of the EB CLI, run the installation command again.

```bash
$ pip install awsebcli --upgrade --user
```

For detailed instructions and troubleshooting, refer to the official [AWS documentation](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install-linux.html).


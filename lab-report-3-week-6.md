# Lab Report 3

# Streamlining ssh Configuration
First I had to make a config file in the .ssh folder and add the following lines to it.
```
Host ieng6
    HostName ieng6.ucsd.edu
    User cs15lsp22afx
```
So it become this:

![image](config_file.png)

So now whenever I enter the command `ssh ieng6` I will connect to the remote server. As shown below.

![image](ssh_login_after_config.png)


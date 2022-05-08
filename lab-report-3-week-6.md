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

I can also use the alias ieng6 when copying a file as shown below.

![image](copy_file.png)

# Setup Github Access from ieng6
I was able to create a public and private rsa key pair and it is stored my user account as shown in the image below.

![image](keys.png)

I added the public key to GitHub.

![image](github_keys.png)

Following this I was able to commit and push changes to github from the remote desktop as shown in the images below.

![image](git_commit.png)

![image](git_push.png)

Here is a [link](https://github.com/Gregory-Chan/cse15l-lab-reports/commit/865b5ab78b6fc3ef39aa3af96ca464ba9011431f) to the commit.

# Copy whole directories with `scp -r`

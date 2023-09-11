# How to manage multiple git accounts and their respective SSH keys.

1. Goto **~/.ssh**

        cd ~/.ssh

2. List the folder to check wether there's existing keys and config files.

        ls

    >If there is no "config" and key files like "id_rsa"/"ed_25519", that's fine, we can create those later. If those file exist, when we create key file in the next step, make sure the filename that you're going to use won't be the same as the existing ones.

3. Generate a new SSH Key based on your github email account followed by your preferred filename like github username.

        ssh-keygen -t ed25519 -C "your_github_account_email@domain.com" -f "your_github_username"

    >It's suggested to use modern way like ed25519 to generate a key, but if your system does not support that, like you're using a legacy system, you may run the following: 
    >
    >        ssh-keygen -t rsa -b 4096 -C "your_github_account_email@domain.com" -f "your_github_username"

4. By now, you'll have a key pairs of "your_github_username" and "your_github_username.pub"

5. Repeat if you need more key pairs for every other Github account(s).

6. Open config file in ~/.ssh

        open config

    >You may create one if you don't have that by:
    >
    >       touch config

7. Edit the config file with the following details:

        ## Account 1
        Host github.com-your_github_username1
        HostName github.com
        User git
        IdentityFile ~/.ssh/your_github_username1    

        ## Account 2
        Host github.com-your_github_username2
        HostName github.com
        User git
        IdentityFile ~/.ssh/your_github_username2

> If I have github username of hklam0, then I change code as:
>
>        ## Account 1
>        Host github.com-your_github_hklam0
>        HostName github.com
>        User git
>        IdentityFile ~/.ssh/your_github_hklam0
>
> Note, here I save the key pair as hklam0 and hklam0.pub
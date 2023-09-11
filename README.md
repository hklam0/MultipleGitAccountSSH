# How to manage multiple git account and their respective SSH keys.

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

    
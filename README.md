# How to manage multiple git account and their respective SSH keys.

1. Goto **~/.ssh**

        cd ~/.ssh

2. List the folder to check wether there's existing keys and config files.

        ls

>If there is no "config" and key files like "id_rsa"/"ed_25519", that's fine, we can create those later. If those file exist, when we create key file in the next step, make sure the filename that you're going to use won't be the same as the existing ones.


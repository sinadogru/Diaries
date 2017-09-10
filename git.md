# git Diaries

## Setting up multiple github accounts on same computer

I just needed to set up multiple github accounts to my personal computer.
I took those steps to accomplish it:
- Create SSH Keys
    - name them differently, ~/.ssh/id_rsa_x and ~/.ssh/id_rsa_y
- Add new SSH keys to GitHub accounts
- Create a ~/.ssh/config file
    - Add new hosts to config file:
    ```
    Host github_x
        HostName github.com
        User git
        IdentityFile ~/.ssh/id_rsa
    Host github_y
        HostName github.com
        User git
        IdentityFile ~/.ssh/id_rsa_y
    ```
- Set origin url of your local repository to new host
    - command: git remote set-url origin git@HOSTNAME:USERNAME/REPOSITORY_NAME.git
    ```
    git remote set-url origin git@github-cavit:sinadogru/Diaries.git
    ```

References: 
- https://code.tutsplus.com/tutorials/quick-tip-how-to-work-with-github-and-multiple-accounts--net-22574
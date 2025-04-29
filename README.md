# mac-setup

## Software
- iTerm
- Git
- ZSH
- oh-my-zsh
- nvm for node
- .Net core
- VS code
- Docker
- MongoDB
- Vim

## GitHub vs multiple SSH Keys
Create new SSH Keys according to instructions.

Modify ````~/.ssh/config````:
````
Host github.com-SOME-ID
HostName github.com
AddKeysToAgent yes
UseKeyChain yes
IdentityFile ~/.ssh/keyname
````

Modify local repo config file ````.git/config```` to match updated host name:
````
[remote "origin"]
        url = git@github.com-SOME-ID:username/project.git
````

Check if all SSH keys are added to the agent:
````ssh-add -l````

If key(s) not present, add the key to the agent:
````
ssh-add --appe-use-keychain ~/.ssh/keyname
````
https://vanthanhtran245.github.io/use-multiple-ssh-key-for-different-git-accounts/
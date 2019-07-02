# Git Training with Albert

## Questions

* Initial SSH setup for git
* Home folder
* Several git accounts for several users in the same set up?
* Branch strategy (Git Flow) Whats the recommendation?
* What git editor/viewer do you recommend?

Albert Rigo's settings from .bash_profile:

```bash
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
export PS1="\u@\h \[\033[32m\]\w\[\033[33m\]\$(parse_git_branch)\[\033[00m\] $ "

#export JAVA_HOME=$(/usr/libexec/java_home)
#source /opt/atlassian/setup.sh

export M2_HOME=/usr/local/Cellar/maven/3.5.4/libexec
export M2=${M2_HOME}/bin
export PATH=${PATH}:${M2_HOME}/bin

alias ls='ls -FG'
```

Generate a new SSH key:

* Create .ssh folder in `~home` directory.
* The owner(me) only should have permissions to this folder and it's files.
* From shell prompt run:

```bash
~home $ ssh-keygen
```
* Skipp the password protection if you want. Often the computers password protection is enough 

Set permissions to the file:
Browse to ~home directory and run:

```bash
chmod o-r  .ssh/id_rsa
chmod g-r  .ssh/id_rsa
```

After changes to the file .bash_profile reload "source" from shell or restart bash.

```bash
source ~/.bash_profile
```

If SSH key already exists:
Browse to `~home` directory and then `.ssh`

* id_rsa (private key)
* id_rsa.pub (public key)

Look at the keys:

* cat id_rsa.pub
* cat id_rsa

To use the the SSH key withGitHub

* copy and paste the key into GitHub.

[Use multiple SSH private keys on one client](https://stackoverflow.com/questions/2419566/best-way-to-use-multiple-ssh-private-keys-on-one-client)

[Get Color themes for bash in macos-terminal-themes](https://github.com/lysyi3m/macos-terminal-themes)
# Computer Science Resources

## LINKS

### UI
- https://unsplash.com
- https://undraw.co/illustrations

### GIT REPOS
- https://github.com/github/gitignore

### Helper Tools
- API Builder: https://postwoman.io/
- API Builder: https://www.postman.com/
- Hosting: https://vercel.com/

### YouTube Channels
- 3blue1brown [Random Math]: https://www.youtube.com/channel/UCYO_jab_esuFRV4b17AJtAw
- Tom Scott [Random]: https://www.youtube.com/channel/UCBa659QWEk1AI4Tg--mrJ2A
- Computerphile [Fundamentals]: https://www.youtube.com/channel/UC9-y-6csu5WGm29I7JiwpnA
- LearnCode.Academy [CS]: https://www.youtube.com/channel/UCVTlvUkGslCV_h-nSAId8Sw
- freeCodeCamp [CS]: https://www.youtube.com/channel/UC8butISFwT-Wl7EV0hUK0BQ
- Jabrils [ML]: https://www.youtube.com/channel/UCQALLeQPoZdZC4JNUboVEUg
- javidx9 [CS]: https://www.youtube.com/channel/UC-yuWVUplUJZvieEligKBkA

### Online Courses
- CS50 (David Malan & Co.): https://online-learning.harvard.edu/course/cs50-introduction-computer-science
- Andre Ng (God of ML): https://www.coursera.org/learn/machine-learning

### Hacker Stuff
- Hacker website with useful resources: https://www.hacker101.com/
- Catch The Flag: https://ctf.hacker101.com/ctf
- Binary Exploit: https://trailofbits.github.io/ctf/exploits/binary1.html
- Hacker One: https://www.hackerone.com/
- HackerSploit: https://www.youtube.com/channel/UC0ZTPkdxlAKf-V33tqXwi3Q

### Random Links
- Stuff about CS: https://www.geeksforgeeks.org/

## DOCKER TRICKS

### Starting a Docker instance

1. Install docker (https://www.docker.com/get-started)
2. Get image you want `docker pull some-linux-image`
3. Run the image `docker run -ti some-linux-image /bin/bash`

> **_NOTE:_**  Once exited, the container is stopped. You can restart it by `docker ps -a` and with the name of the container `docker start -ai <NAME_CONTAINER>`

4. Some basic setups inside the docker VM:
    1. `apt update`
    2. `apt dist-upgrade`
    3. `apt autoremove`
    4. `apt clean`

5. The VM is now ready to use, install whathever you want...

#### Persist VM

1. Get container ID `docker ps -a`
2. Persist the container `docker commit <CONTAINER ID> my-kali`
3. Run it back `docker run -ti my-kali /bin/bash`
4. List all committed images `docker images`

> **_NOTE:_**  There are two ways to create a Docker image, (1) write a Dockerfile and run docker build on it, (2) run a container, make changes and run docker commit to create a new image. Committing a container to create a new image is not ideal. Dockerfiles for reproducible images (see repo https://github.com/C00kieMonsta/kali-image).

#### Restart a container

1. Get container ID `docker ps -a`
2. Restart specific container `docker start -ai <CONTAINER ID>`

> **_NOTE:_**  An Image is blueprint/snapshot of a container. So the container is like an instance of this Image. Each time the image is being run, it creates a new container.


### Kali Linux Instance

> **_NOTE:_**  A Debian-derived Linux distribution designed for digital forensics and penetration testing.

1. Get Kali image `docker pull kalilinux/kali-rolling`
2. Run the image `docker run -ti kalilinux/kali-rolling /bin/bash`
3. Basic setups
4. Installing Hydra for brute force code breaking
    1. `apt install hydra`
    2. `apt install hydra hydra-gtk`
    3. `apt install wordlists`
    4. `gunzip /usr/share/wordlists/rockyou.txt.gz`


### Setup SSH on Instance

1. Install openssh package: `apt-get install openssh-server`
2. (If package was wrongly configured, you can reconfigure it with the debian package manager: `dpkg-reconfigure openssh-server`)
3. Refactor the `sshd_config` file to configure the ssh options: `vi /etc/ssh/sshd_config`
4. You then want to start the ssh server: `service ssh start`
5. Next you want to know the local IP address of the VM (you might need to install the `net-tool` package): `ifconfig`
6. On you machine, open a bash console and run: `ssh root@<ip>`


## PYTHON TIPS

### Setup of python project

#### Setup env

`python3 -m venv env`
`source ./env/bin/activate`

#### Install dependencies inside env

`python -m pip install numpy`
`python -m pip install matplotlib`


## BASH TIPS

### How to create a bash script

1. Turn on executable mode for your script: `chmod +x myscript.sh`
2. Start your script with an interpreter string `#!/bin/bash`
3. If script sits in `~/bin`, export the `PATH` in  `~/.profile`: `export PATH="$HOME/bin:$PATH"`

### Where to put bash script

- If you are a system admin and want everyone on the system to be able to run the scripts, place them in `/usr/local/bin`

- If you want them to only be accessible to you, place them in `~/bin`

### Tips to create bash scripts

- Create bash scripts: http://linuxcommand.org/lc3_writing_shell_scripts.php
- Using screen command: https://linuxize.com/post/how-to-use-linux-screen/


## CODE SNIPPETS

### Bash Customisation

It is always nice to custom your bash:

1. Go to `cd ~`
2. Edit the hidden .bash_profile file `vi .bash_profile`
3. Refresh file `source ~/.bash_profile`

```bash
# Git Branch

parse_git_branch() {
   git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}


# Folder Color

export PS1="\[\033[36m\]\u\[\033[m\]@\[\033[32m\]\h:\[\033[33;1m\]\w\[\033[m\]\[\033[32m\]\$(parse_git_branch)\[\033[00m\]$ "
export CLICOLOR=1
export LSCOLORS=ExFxBxDxCxegedabagacad
alias ls='ls -GFh'
```

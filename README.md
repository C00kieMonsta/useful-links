# USEFUL LINKS & NOTES

## UI

- https://unsplash.com
- https://undraw.co/illustrations

## GIT REPOS

- https://github.com/github/gitignore


## YouTube Channels

- 3blue1brown: https://www.youtube.com/channel/UCYO_jab_esuFRV4b17AJtAw
- Tom Scott: https://www.youtube.com/channel/UCBa659QWEk1AI4Tg--mrJ2A
- Computerphile: https://www.youtube.com/channel/UC9-y-6csu5WGm29I7JiwpnA
- LearnCode.Academy: https://www.youtube.com/channel/UCVTlvUkGslCV_h-nSAId8Sw
- freeCodeCamp: https://www.youtube.com/channel/UC8butISFwT-Wl7EV0hUK0BQ
- Jabrils: https://www.youtube.com/channel/UCQALLeQPoZdZC4JNUboVEUg

## Favorite Online Courses

- CS50 (David Malan & Co.): https://online-learning.harvard.edu/course/cs50-introduction-computer-science
- Andre Ng (God of ML): https://www.coursera.org/learn/machine-learning

## Random Links

- Stuff about CS: https://www.geeksforgeeks.org/

## Starting a Docker instance

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

### Kali Linux Instance

1. Get Kali image `docker pull kalilinux/kali-rolling`
2. Run the image `docker run -ti kalilinux/kali-rolling /bin/bash`
3. Basic setups
4. Installing Hydra for brute force code breaking
    1. `apt install hydra`
    2. `apt install hydra hydra-gtk`
    3. `apt install wordlists`
    4. `gunzip /usr/share/wordlists/rockyou.txt.gz`

### Persist VM

1. Get container ID `docker ps -a`
2. Persist the container `docker commit <CONTAINER ID> my-kali`
3. Run it back `docker run -ti my-kali /bin/bash`
4. List all committed images `docker images`

> **_NOTE:_**  An Image is blueprint/snapshot of a container. So the container is like an instance of this Image. Each time the image is being run, it creates a new container.

## Hacker Stuff

- Hacker website with useful resources: https://www.hacker101.com/
- Catch The Flag: https://ctf.hacker101.com/ctf
- Binary Exploit: https://trailofbits.github.io/ctf/exploits/binary1.html
- Hacker One: https://www.hackerone.com/

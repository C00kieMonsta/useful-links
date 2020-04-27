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

## Starting a Docker instance

1. Install docker (https://www.docker.com/get-started)
2. Get image you want `docker pull some-linux-image`
3. Run the image `docker run -ti some-linux-image /bin/bash`

> **_NOTE:_**  Once exited, everything is lost.

4. Some basic setups inside the docker VM:
    1. `apt update`
    2. `apt dist-upgrade`
    3. `apt autoremove`
    4. `apt clean`

5. The VM is now ready to use, install whathever you want...

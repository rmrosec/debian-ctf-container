# Debian CTF Docker Image

A Debian-based Docker container intended to be used for CTFs and PenTesting. 
 
Due to the fact that the image builds the jumbo edition of John the Ripper from source, the first time building it may take a few minutes.


Programs Included:
* john (Jumbo version from source, installed in `/home/${USERNAME}/john/run`)
* netcat
* node.js
* python3.9
* pwntools
* pypykatz (Mimikatz implementation in Python)
* sqlmap (Installed in `/home/${USERNAME}/sqlmap`)
* tcpdump
* tshark (CLI alternative to Wireshark)

### Configure and Run:
* Requirements: `Docker`, `docker-compose`
* The `.env` file has a variable `LOCALPATH`, which should point at a local directory that you want to mount on the container at `/home/work`.
    * This is useful for when working on payloads or programs, or trying to transfer files between container and host. Obviously, this is at your own discretion - you should not put malware in this folder and should be very careful.
* In the `Dockerfile`, set the `USERNAME` arg to your own username
* In the root directory of this repository, run `docker-compose up -d` to build and run the container automatically. If any changes are made to the `Dockerfile` or `docker-compose.yml` files, you should re-run this command to relaunch the container (and rebuild if applicable)
* Once the container is running, attach a shell to it and run `passwd` to configure your password - the default is `default`

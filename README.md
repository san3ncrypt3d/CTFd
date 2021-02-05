# Run CTFd on Ubuntu 20.04

This repo will let you run CTFs on Ubuntu 20.04. You will also be able to run CTFd as a secure (HTTPS) site.

## Prep

1. Run the `docker_ubuntu.sh` script in this repo:
`sudo ./docker_ubuntu.sh`

2. Run the `docker_compose_ubuntu.sh` script in this repo:
`sudo ./docker_compose_ubuntu.sh`

3. To generate your Public-Private Key Pair, run the `generate_crt.sh` script in this repo:
`sudo ./generate_crt.sh`

4. Edit the `hostname` line in the `docker-compose-production.yml` file to match the hostname you have defined to point to your server.
For example, if your server name is `mywifictf.com`, then change the `hostname` line in the `docker-compose-production.yml` file to `mywifictf.com`.

## Run the CTFd environment

In the terminal, run `docker-compose -f docker-compose.yml -f docker-compose-production.yml up`.




## Credits

- CTFd by [CTFd](https://github.com/CTFd/CTFd)
- HTTPS by [Josh Grossman](https://github.com/tghosth/CTFd-docker-deploy)

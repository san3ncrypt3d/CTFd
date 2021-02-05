# Run CTFd on Ubuntu 20.04

This repo will let you run CTFs on Ubuntu 20.04. You will also be able to run CTFd as a secure (HTTPS) site.

## Prep

1. Run the `docker_ubuntu.sh` script in this repo:
`sudo ./docker_ubuntu.sh`

2. Run the `docker_compose_ubuntu.sh` script in this repo:
`sudo ./docker_compose_ubuntu.sh`

3. In the terminal, go to the `ssl` directory (`cd ssl`)

4. Generate your Public-Private Key Pair, CSR, and Certificate for your site. If your site name is `mywifictf.com`, run the following commands:
`openssl req -newkey rsa:2048 -x509 -sha256 -days 3650 -nodes -out ctfd.crt -keyout ctfd.key`
Make sure to name your .crt and .key files exactly as specified in the command above: ctfd.crt and ctfd.key, respectively. Follow the prompts and enter all required information.

5. Edit the `hostname` line in the `docker-compose-production.yml` file to match the hostname you have defined to point to your server.
For example, if your server name is `mywifictf.com`, then change the `hostname` line in the `docker-compose-production.yml` file to `mywifictf.com`.

## Run the CTFd environment

In the terminal, run `docker-compose -f docker-compose.yml -f docker-compose-production.yml up`.




## Credits

- CTFd by [CTFd](https://github.com/CTFd/CTFd)
- HTTPS by [Josh Grossman](https://github.com/tghosth/CTFd-docker-deploy)

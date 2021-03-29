# deployment - example deployment of the application

This repository serves as an example deployment of "An Interactive End-To-End Machine Learning Platform" (Name subject to change). The application consists of 4 different components, each of which is distributed as a docker image via Dockerfiles.

Each of these 4 services can be run on different machines, networks and configured via their respective environment variables. See the respective repositories for more details on how to configure each service. One can also scale the application horizontally using using load balancer gateways and multiple service instances.

This repository includes a `docker-compose.yml` file that runs all 4 services on a single machine and an example nginx virtual host `pse.sample.conf` acting as a simple gateway for these services. This gateway expects a properly configured nginx server with SSL (the application ONLY works over https). You can use `certbot` from Let's Encrypt for this purpose.

## Building

- clone this repository, including it's submodules: (`git clone --recurse-submodules`)
- build the images: `docker-compose build --parallel`
- deploy `pse.sample.conf` vhost and set up certificates.
- `docker-compose up`

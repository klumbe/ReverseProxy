## About the Project
This is a basic reverse-proxy configuration designed to run on a RaspberryPi.
It uses [Traefik](https://www.traefik.io) running on [Docker](https://www.docker.com) 
using [Docker-Compose](https://docs.docker.com/compose).

HTTPS is enforced by using [Let's Encrypt](https://letsencrypt.org) with the HTTP Challenge.

## Getting Started

### Prerequisites

* Install Docker
  [https://docs.docker.com/engine/install](https://docs.docker.com/engine/install)

* Install Docker-Compose
  [https://docs.docker.com/compose/install](https://docs.docker.com/compose/install)


* Install apache-utils to get htpasswd for generating passwords.

  * Debian/Ubuntu/Raspbian/...

    ```bash
    # sudo apt-get update && sudo apt-get install apache2-utils -y
    ```
  * Fedora > 21
    ```bash
    # sudo dnf install apache2-utils -y
    ```
  * Fedora < 22
    ```bash
    # sudo yum install apache2-utils -y
    ```

### Installation

1. Clone this repo
   ```bash
   # sudo git clone https://github.com/klumbe/ReverseProxy
   ```

2. Generate password(s) for the Traefik dashboard:
    ```bash
    # htpasswd ./conf/auth/traefik_basic <username>
    ```

3. Start the container in detached mode:
   ```bash
   # sudo docker-compose up -d
   ```

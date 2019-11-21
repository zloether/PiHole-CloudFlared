# PiHole-CloudFlared
Anible project to configure CloudFlare DNS over HTTPS client on PiHole


## What is DNS over HTTPS?
[https://en.wikipedia.org/wiki/DNS_over_HTTPS](https://en.wikipedia.org/wiki/DNS_over_HTTPS)


## Prerequisites
1. This project assumes you already have an [PiHole](https://pi-hole.net/) configured on your network.

1. You need to have a computer with [Ansible](https://www.ansible.com/) installed

    On most Debian based Linux distributions, installing Ansible is as easy as running:
    ```
    sudo apt update
    sudo apt -y install ansible
    ```


## Instructions
1. Clone this repository:
    ```
    git clone https://github.com/zloether/PiHole-CloudFlared.git
    ```

1. Edit the `inventory` file with the IP address of your PiHole

1. From inside the `PiHole-CloudFlared` directory, run this command:
    ```
    ansible-playbook -i inventory --ask-pass --ask-become-pass
    ```

1. Log into the admin page of your PiHole

1. Click on Settings (left side of screen) and then DNS (top of screen)

1. Change your Upstream DNS Servers to use a custom value:
    __127.0.0.1#5300__

1. Click the `Save` button

![config](https://github.com/zloether/PiHole-CloudFlared/blob/master/config.png)
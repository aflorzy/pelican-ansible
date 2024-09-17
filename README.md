# All-In-One Pelican Game Panel Installation Playbook

This playbook was created to automate the installation of Pelican so that it can be quickly and reliably deployed on game servers.

 It was written with a host OS of Ubuntu in mind, so certain plays that use modules such as `apt` will not work on some servers.

**Pelican 1.0.0-beta8 tested working on Ubuntu 24.04**

## Getting Started

Edit `inventory` and the variables section of `install_pelican.yml` to use values that will work in your setup.
Read through each of the plays to get an idea of what the setup process is like.

Run `ansible-playbook install_pelican.yml`

## Post-Script Steps

Visit your panel URL and click through the steps

Follow steps in the [Configure step](https://pelican.dev/docs/wings/install#configure) of the Pelican documentation

SSH into your server

Copy the code for `config.yml` in the "Configuration" tab of your node and paste it in `/etc/pelican/config.yml`

Ensure Wings is able to work by running `sudo wings --debug`

If successful, cancel the execution with `Ctrl + C` and enable the Wings service to start on boot `sudo systemctl enable --now wings`

## Limitations

HTTPS/SSL is not yet supported with this playbook.
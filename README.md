# dockerinstall
Boring template for Ubuntu Server. I usually find new reasons to spin up a server and want a simple way to automate common installations without Ansible.
Update Apt so I can use HTTPS:
sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
Add Docker’s GPG key:
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg


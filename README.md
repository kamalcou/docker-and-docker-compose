# docker-and-docker-compose

Step 1. Installing Docker 

Update your existing packages:

sudo apt update
Install a prerequisite packages which let apt utilize HTTPS:

sudo apt install apt-transport-https ca-certificates curl software-properties-common
Add GPG key for the official Docker repo to the Ubuntu system:

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
Add the Docker repo to APT sources:

sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
Update the  database with the Docker packages from the added repo:

sudo apt update
Install Docker software:

sudo apt install docker-ce
Docker should now be installed, the daemon started, and the process enabled to start on boot. To verify:

sudo systemctl status docker
 

NOTE: To avoid using sudo for docker activities, add your username to the Docker Group

sudo usermod -aG docker ${USER}
 

Step 2. Installing docker-compose

Note - using a non-root user perform the following.

Docker Compose is a tool that allows you to run container environments based on definitions set in a YAML file.  Installing NetFoundry software into containers using this method is the simplest way to get started quickly.

Confirm the latest version available in their releases page. At the time of this writing, the most current stable version is 1.28.5.

The command below will download the 1.28.5 release and save the executable at /usr/local/bin/docker-compose, which will make this software globally accessible as docker-compose:

sudo curl -L "https://github.com/docker/compose/releases/download/1.28.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
Set permissions so that the docker-compose command is executable:

sudo chmod +x /usr/local/bin/docker-compose
Verify that the installation was successful by viewing version information:

docker-compose --version
docker-compose version 1.28.5, build c4eb3a1f
Now your ready to run our endpoint software. Follow these instructions to continue your NetFoundry containerized journey.

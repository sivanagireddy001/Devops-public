# Install docker on ubuntu

# Method 1

1. To download the Docker installation script on Ubuntu
``` 
sudo curl -fsSL https://get.docker.com -o get-docker.sh 
```
This command will download the installation script from the Docker website and save it as a file named `get-docker.sh` in your current directory.

You can then run the installation script with sudo permissions to install Docker on your system.

2. Make the installation script executable
```
sudo chmod +x get-docker.sh
```
3. Run the installation script
```
sudo sh get-docker.sh
```
4. Start the Docker service
```
sudo systemctl start docker
```
5. enable it to start automatically on boot
```
sudo systemctl enable docker
```
6. To check the status of docker
```
sudo systemctl status docker
```
7. To check the docker version
```
docker version
```
* To check docker version in more detail
```
docker info
```
* If you want to run Docker commands without using `sudo`, you can add your user to the docker group:
```
sudo usermod -aG docker ${USER}
```
Log out and log back in for the changes to take effect.

<br></br>
If you are still experiencing issues, check the permissions on the `/var/run/docker.sock` file.

```
ls -l /var/run/docker.sock
```
If the permissions are incorrect, you can fix them
```
sudo chown root:docker /var/run/docker.sock
```
```
sudo chmod g+rw /var/run/docker.sock
```

<br></br>
# Method 2

* Update your system's package index and install the necessary packages
```
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```
* Add the GPG key for Docker's official repository
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
* Add the Docker repository to your system's sources
```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```
* Update the package index again
```
sudo apt update
```
* install Docker
```
sudo apt install docker.io
```
* Start the Docker service 
```
sudo systemctl start docker
```
* enable it to start automatically on boot
```
sudo systemctl enable docker
```
* To check the status of docker
```
sudo systemctl status docker
```
* Verify that Docker has been installed correctly by running the hello-world container
```
sudo docker run hello-world
```
* If you want to run Docker commands without using sudo, you can add your user to the docker group:
```
sudo usermod -aG docker ${USER}
```
Log out and log back in for the changes to take effect.

<br></br>
# Uninstall docker on ubuntu
To remove Docker completely from your Ubuntu system

* Stop any running Docker containers
```
sudo docker stop $(sudo docker ps -a -q)
```
* remove Docker containers
```
sudo docker rm $(sudo docker ps -a -q)
```
* Remove the Docker package and its dependencies:
```
sudo apt-get purge docker-ce
sudo apt-get autoremove --purge docker-ce
```
* Remove any Docker-related files and directories
```
sudo rm -rf /var/lib/docker
sudo rm /etc/docker
```
* delete docker group
```
sudo groupdel docker
```
* Finally, if you added your user to the docker group, remove yourself from the group
```
sudo userdel ${USER} docker
```
That should completely remove Docker from your Ubuntu system.


























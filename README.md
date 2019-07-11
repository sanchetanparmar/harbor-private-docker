# Install Harbor private docker registry

### Prerequisite
 1.  Install Docker 
 
     Uninstall docker old versions

` sudo apt-get remove docker docker-engine docker.io containerd runc`   

2. Install Docker CE

 `sudo apt-get update`
 
 install packages to allow `apt` to use a repository over HTTPS:
 
 ``sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common``

3. Add Docker official GPG key 
  `curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`
  
4. Add stable repository.  
` sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"`
5. update repo - `apt-get update`
6. Install the docker latest version `sudo apt-get install docker-ce docker-ce-cli containerd.io`

## Install Docker-compose
`sudo curl -L "https://github.com/docker/compose/releases/download/1.24.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose`

`sudo chmod +x /usr/local/bin/docker-compose`

`sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose`

 # Generate self-signed certificates

* Create certificate authority

 `openssl req -newkey rsa:4096 -nodes -sha256 -keyout ca.key -x509 -days 3650 -out ca.crt`
*  Generate certificate signing request

`openssl req -newkey rsa:4096 -nodes -sha256 -keyout harbor.key -out harbor.csr`



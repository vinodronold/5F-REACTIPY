# REQUIRED SYSTEM SETUP


## INSTALL CREATE-REACT-APP
- sudo npm -g create-react-app - **DONE**

## CREATING PYTHON VENV FIVEFRETS
- INSTALL DJANGO - **DONE**
- INSTALL DJANGORESTFRAMEWORK - **DONE**
- INSTALL DJANOG-REST-KNOX

## CREATING REACT DEV ENV USING CREATE-REACT-APP

## INSTALLING DOCKER
~~~~
sudo apt-get update
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add
sudo apt-key fingerprint 0EBFCD88
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

sudo apt-get update
sudo apt-get install docker-ce

~~~~

## DOCKER COMPOSE
~~~~
sudo -i
curl -L "https://github.com/docker/compose/releases/download/1.11.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
exit
~~~~

## CREATING: FF POSTGRES IMAGE AND SPIN A CONTAINER:
~~~~
dckr build -t "psql01" .
dckr run --name db01 -e POSTGRES_PASSWORD=fivefrets -d psql01
                                                     (IMAGE_NAME)
~~~~
### TEST DB
~~~~
dckr run -it --rm --link db01:postgres postgres psql -h postgres -U fivefrets
~~~~

## CREATING: FF UBUNTU 16.04 WITH DJANGO / LIBROSA

## BUILDING CHORDINO VAMP-PLUGIN

cd <path to nnls-chorma source>
make -f Makefile.linux


## MISC
NEED TO CHECK : myproject/settings.py @ https://www.syncano.io/blog/configuring-running-django-celery-docker-containers-pt-1/


rm -rf ~/.local/share/Trash/*

## DIGITAL OCEAN:

non-root user
~~~~
adduser fivefrets
groups fivefrets
usermod -aG sudo fivefrets
~~~~
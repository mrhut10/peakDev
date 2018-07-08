# peakDev
The Reproducible Developer Environment designed for **peak Fun***ction*  

1. **Reproducible** - recreate your developer environment quickly and automatically 
3. **Immutable** in at least thinking - permanent changes to VM to be defined in vagrant file only
4. **Minimalistic** - *reduced bandwidth/space required to reproduce* plus less distractions - currently only tools for peak performance i.e. preferred editors & browsers.
4. **Extendable with** tools like Docker on the fly
5. **Promotes Community** - lets help each other create the best **peak fun***cionable* Developer environment there is.
    * Helpful docker files and scripts to show common extra toolsets
    * Well documented process to set up and use
    * Dynamic/evolving the project from what is learnt.


## Current Tool Set
* Ubuntu bionic64 Server with minimal desktop GUI
* Container Technology for extending tools
  * [Docker](https://www.docker.com/)
  * [docker-compose](https://www.docker.com/)
* Browsers
  * [Firefox](https://www.mozilla.org/en-US/firefox/)
  * [chromium](https://www.chromium.org/Home)
* Editors & dev Tools
  * [VS code](https://code.visualstudio.com/)
  * vim
  * [git](https://git-scm.com/)

## Getting Started
1. download and Install the both  
  * [VirtualBox](https://www.virtualbox.org/)*(virtualisation technology)*  
  * [Vagrant](https://www.vagrantup.com/) *(a automated VM build tool)*  
  * [vagrant docker compose plugin](https://github.com/leighmcculloch/vagrant-docker-compose)  
  run `vagrant plugin install vagrant-docker-compose` to install 

2. Clone repo  
`git clone https://github.com/mrhut10/peakDev && cd peakDev`
4. Provision peakDev  
`vagrant up`
will take some time  
afterwards virtualbox window should be visible
5. Login too virtualbox window login  
`user: vagrant`, `password: vagrant`
6. Start GUI `startx`  

*you should now be within your peakDev environment*  

## Community Welcome 
  Welcome to the community of developers who want a peak performing defined dev environment which is quickly reproducible.
## Contributing
  Please contribute your skills (regardless of level) to improve the project and/or the community.
## Note
  currently this is a vagrantfile + docs & tools however in the future will consider building vagrantbox images for peoples convenience
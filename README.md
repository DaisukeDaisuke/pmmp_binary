# pmmp_binary
pmmp binary for ubuntu18
## warning
If using ubuntu 20 or higher os, please use the official binaries.  
https://jenkins.pmmp.io/  

## overview
The goal of this repository is to provide executable binaries for the latest pmmp on older ubuntu os using github actions.  
The pmmp binaries for ubuntu18 will be maintained until March 2023.  
  
Some server hosts use ubuntu 18 docker images and do not provide image modification features or Linux bash shell access.  
Therefore, official binaries supporting ubuntu 20 and above will not work, and users will need to build their own binaries.  

The [panel](https://github.com/pterodactyl/panel) decompressor does not process symbolic links correctly, so binaries that do not use it are also distributed.

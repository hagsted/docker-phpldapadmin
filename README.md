
### Repositories
- [Docker Hub repository](https://registry.hub.docker.com/u/kalaksi/phpldapadmin/)
- [GitHub repository](https://github.com/kalaksi/docker-phpldapadmin)

### Why use this container?
**Simply put, this container has been written with simplicity and security in mind.**

Surprisingly, _many_ community containers run unnecessarily with root privileges by default and don't provide help for dropping unneeded CAPabilities either.
On top of that, overly complex shell scripts, monolithic designs and unofficial base images make it harder to verify the source among other issues.

To remedy the situation, these images have been written with security and simplicity in mind. See [Design Goals](#design-goals) further down.

### Running this container
This container only contains phpldapadmin and the necessary PHP (PHP-FPM) packages. In other words, this container only runs the PHP process and no HTTP server (which is how things should be).  
You will therefore need an accompanying HTTP server. Luckily, the ```docker-compose.yml``` in the source repository contains a complete example of running this container with nginx and will work without additional steps.

#### Supported tags
See the ```Tags``` tab on Docker Hub for specifics. Basically you have:
- The default ```latest``` tag that always has the latest changes.
- Minor versioned tags (follow Semantic Versioning), e.g. ```1.1``` which would follow branch ```1.1.x``` on GitHub.

#### Configuration
By default, the configuration files can be found on the named volume and is currently the only way to configure phpldapadmin.
See ```Dockerfile``` and ```docker-compose.yml``` (<https://github.com/kalaksi/docker-phpldapadmin>) for more details.

### Development
#### Design Goals
- Never run as root unless necessary.
- No static default passwords. That would make the container insecure by default.
- Use only official base images.
- Provide an example ```docker-compose.yml``` that also shows what CAPabilities can be dropped.
- Offer versioned tags for stability.
- Try to keep everything in the Dockerfile (if reasonable, considering line count and readability).
- Don't restrict configuration possibilities: provide a way to use native config files for the containerized application.
- Handle signals properly.

#### Contributing
See the repository on <https://github.com/kalaksi/docker-phpldapadmin>.
All kinds of contributions are welcome!

### License
View [license information](https://github.com/kalaksi/docker-phpldapadmin/blob/master/LICENSE) for the software contained in this image.  
As with all Docker images, these likely also contain other software which may be under other licenses (such as Bash, etc from the base distribution, along with any direct or indirect dependencies of the primary software being contained).  
  
As for any pre-built image usage, it is the image user's responsibility to ensure that any use of this image complies with any relevant licenses for all software contained within.
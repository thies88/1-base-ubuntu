# docker-base-ubuntu
ubuntu cloud image for minimal container size

Ripped from: https://github.com/linuxserver/docker-baseimage-ubuntu


Ubuntu based Image for creating docker container monitored by s6-overlay.


    Rebuilds new base image from scratch @https://partner-images.canonical.com/core/${REL}/current/ubuntu-${REL}-core-cloudimg-${ARCH}-root.tar.gz
        Base OS is updated
        Packages are updated
        Application within image(container) gets updated if new release is available.
        Don't manual update Application within container unless you know what you're doing.
        Application settings are restored if mapped correctly to a host folder, your /config folder and settings will be preserved

docker setup

docker create \
  --name=appname \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Europe/Amsterdam \
  -v /path/to/config:/config \
  --restart unless-stopped \
  thies88/spotweb

After starting the container check log for instructions.

update your container:

Via Docker Run/Create

-Update the image: docker pull thies88/containername
-Stop the running container: docker stop containername
-Delete the container: docker rm containername
-Recreate a new container with the same docker create parameters used at the setup of the container (if mapped correctly to a host folder, your /config folder and settings will be preserved)
-Start the new container: docker start containername
-You can also remove the old dangling images: docker image prune

Unraid users can use "Check for updates" within Unraid WebGui

 

A custom base image built with Ubuntu and S6 overlay Based on: https://github.com/linuxserver/docker-baseimage-alpine# _template_docker
# _template_docker
# test1

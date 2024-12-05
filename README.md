# This Repo is for build docker images used by netOSLAB project.
## Steps to update the docker image:
 - Change/update with new features Dockerfile-<image>
 - commit the changes to github
     git add Dockerfile-<image>
     git commit -m "update <image> with new features"
 - Github actions will auto built and push new image version to dockerhub.
     Check the status of the build at https://github.com/lpr-unsl/imagenes-docker/actions
     <version> of the image is the date and time of the commit.
 - You will need to pull the image from dockerhub to use it.
     docker pull netoslab/<image>:<version> 
 - Run the image:
     docker run -it --rm netoslab/<image>:<version>
 - Test if all your changes are correct:
     test your changes in the container
 - Once everything is ok, create a new tag for the image:
     docker tag netoslab/<image>:<version> netoslab/<image>:latest
 - Push the new tag to dockerhub:
     docker push netoslab/<image>:latest


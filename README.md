# This Repo is for build docker images used by netOSLAB project.
## Steps to update the docker image:
 - Change/update with new features Dockerfile-[image]
 - commit the changes to github
 ```
     git add Dockerfile-[image]
     git commit -m "update [image] with new features"
     git push origin master
```
 - Github actions will auto built and push new [image] version to dockerhub.
   - Check the status of the build at https://github.com/lpr-unsl/imagenes-docker/actions
 - Once build, you can see new image in dockerhub https://hub.docker.com/repository/docker/sistemasoperativostur/[image]/general
   - [version] of the image is the date and time of the commit.
 - To test, y ou will need to pull the image from dockerhub.
```
     docker pull sistemasoperativostur/netoslab-[image]:[version]
     docker run -it --rm sistemasoperativostur/netoslab-[image]:[version]
     test ....
     exit
```
 - If everything is ok, create a new tag for the image and push it to dockerhub registry:
   - NOTE: you need to log in in dockerhub with sistemasoperativostur user
```
     docker login
     docker tag sistemasoperativostur/netoslab-[image]:[version] sistemasoperativostur/netoslab-[image]:latest
     docker push sistemasoperativostur/netoslab-[image]:latest
  ```
- **latest** tag is used by netOSLab to pull images

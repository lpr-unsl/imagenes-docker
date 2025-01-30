# This Repo is for build docker images used by netOSLAB project.
## Steps to update the docker image:
 - Create a new branch (e.g. develop)
``` 
     git checkout -b develop
```
 
 - Change/update with new features Dockerfile-[image]
 - commit the changes to github
 ```
     git add Dockerfile-[image]
     git commit -m "update [image] with new features"
     git push --set-upstream origin develop
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
 - If everything is ok, got to github repo web page, and:
   - click "Compare & Pull request" button
   - add a description of the changes
   - click "Create pull request" button
   - wait for the review and merge
   - then click "Confirm merge" button AND "Delete branch" button
   
- Then github actions will create and push **latest** tag netOSLab image to dockerhub.

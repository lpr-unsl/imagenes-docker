# This Repo is for build docker images used by netOSLAB project.
## Steps to update the docker image:
 - Change/update with new features Dockerfile-image
 - commit the changes to github
 ```
     git add Dockerfile-image
     git commit -m "update image with new features"
     git push origin master
    ```
 - Github actions will auto built and push new image version to dockerhub.
     Check the status of the build at https://github.com/lpr-unsl/imagenes-docker/actions
     version of the image is the date and time of the commit.
 - You will need to pull the image from dockerhub to test it.
```
     docker pull netoslab/image:version
     docker run -it --rm netoslab/image:version
     test ....
     exit
```
 - If everything is ok, create a new tag for the image and push it to dockerhub registry:
```
     docker tag netoslab/image:version netoslab/image:latest
     docker push netoslab/image:latest
  ```


# instabug_task

I will follow all steps starting from Creating a Rails Image to deploy it on k8s using my local PC


############Creating a Rails Image###############

To build the image:
docker build -t rails-toolbox \
       --build-arg USER_ID=$(id -u)  \
       --build-arg GROUP_ID=$(id -g) \
       -f Dockerfile.rails .

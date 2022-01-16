# instabug_task

I will follow all steps starting from Creating a Rails Image to deploy it on k8s using my local PC


############Creating a Rails Image###############

To build the image:
docker build -t rails-toolbox \
       --build-arg USER_ID=$(id -u)  \
       --build-arg GROUP_ID=$(id -g) \
       -f Dockerfile .
       
############Building our contianer for new Rails image to create our project drkiq#########################
docker run -it \
    -v $PWD:/opt/app \
    rails-toolbox rails new --skip-bundle drkiq
    
############make all the needed changes in drkiq project ############################
when it comes to Creating the Environment Variable File we can use \
1-if we will build our container form CLI we can use –env, -e \
2- we can use Docker Compose to build our container and pass the env var to the container  \

#######################After adding volumes & intialize Database ###############
we can run :
docker-compose up

Follow the steps to have our images on docker hub 
################################################################################33
when it comes to depoly the image on k8s 

 Kubeclt apply -f Deployment-rails.yaml
 kubectl create -f Configmap.yml

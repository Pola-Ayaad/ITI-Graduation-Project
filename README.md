# Terraform-GCP
Deploy a Simple Python Project with GCP using Terraform


# Terraform-GCP
Deploy a Simple Python Project with GCP using Terraform

Creating Docker Image and pushing the image to Google artifacte registery :


1- Create a Folder for the project mkdir gcp-terraform

2- Clone the git repository to your folder git clone https://github.com/nidhinshah/Accessing-DockerHub-Repos-IKS-Examples.git

3- Create a Dockerfile for the project 

![image](https://user-images.githubusercontent.com/71693153/182429095-21dc9ecf-b1f9-4b32-8e83-db5a6f63da28.png)

4- Build your image docker image build . -t (image-name)

5- Make sure the image is up and running docker run -d -it (image-ID) bash

6- Check running container docker ps

7- Create a Repository on DockerHub 

8- Dockerhub Login on your terminal  --- (docker login)

9- Tag your Image ---(docker tag <existing-image> <hub-user>/<repo-name>[:<tag>])

10- docker push <hub-user>/<repo-name>:<tag>

Creating Terraform Files for Network  : 
   Note :  ---(Use terraform fmt)-- command to correct your files formate 
           ---GCP already supports state locking so there is no need to create a DynamoDB like
              in AWS state
           ---Run terrform init to intiate terraform enviroment and in case any changes in the backend.tf file you need to run the command again 
           ---Add .gitignore file to add all the files that you wouldn't like to push to github ex: files with credentials for any unrelated files 


1- Create provider file 

2- Create credentials.json file which has the your credintials 

3- create a backendend.tf which will have the tfstae file uploaded to gcs bucket

4- create a variables.tf file to declare your enviromental variables

5- create terraform.tfvars to declare values to your variables 

6- create VPC

7- Create 2 Subnets 

8- Create Cloud Router which enables Cloud router enables you to exchange routes between vpc and peers 

9- Create Nat-Gatway 

10- Create IAP.tf to allow IAP 


Creating Terraform Files for the VM and GKE cluster 

1- Create 2 service accounts one for the VM and the other for the GKE cluster and the purpose of 

the service accounts intended to represent a non-human user that needs to authenticate and be authorized to access data in Google APIs.

2- Create VM with a stable version of Ubuntu --- make sure the tag is correct to you can ssh 

3- Create GKE cluster 

4- Terraform apply 

5- SSH on the machine ---- gcloud compute ssh vm --zone=us-east1-b


6- configure vm with gke credintials --- gcloud container clusters get-credentials my-gke-cluster --zone us-east1-b --project pola-gcp-project-1

7- Create a deployment and service.yml files for jenkins 

8- Apply those file 

9- kubectl get svc to get the External IP of jenkins 
   
10- configure Jenkins , add github credentials , Jenkins credentials and your Virtual instace private key 

11- Add your Virtual Instance as a Slave --
    ![image](https://user-images.githubusercontent.com/71693153/182432161-3fc30f07-cd33-40a0-ba8a-68f143fd5388.png)
    
    
 

    
 


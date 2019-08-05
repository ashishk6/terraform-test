# Jenkins pipeline to create IAM user and group using terraform
> Here we will use the Terraform and Jenkins pipleline to create an AWS IAM(Identity and access Management) user and group

-- Steps to create and configure:
- Install jenkins containers and map it to the local port
  -docker run -d --rm -p 8080:8080 jenkins/jenkins
  -use the localhost:8080 to run the jenkins 
 - You have to enter the secret key of the jenkins in order to start it which can be retrived via given path during the Jenkins setup. For this you need to go inside the container using below command:
   - docker exec -it <container id> /bin/bash
 
-  Download the AWS credentials and terraform plugins in order to configure it.
>Note: If the terraform plugins are not running properly then you may have to login to the root folder of the jenkins container and install the terraform inside the usr/bin folder and set the path for the terraform.

- Write the terraform script and Jenkinsfiles which is written in a Groovy language to configure the IAM user and group and to run the jenkins respectively. Make sure that all the files are in the same location.

-  Here we will make the use of WebHook of GIthub feature which will make sure that any changes/modification  made to the Gitbranch will trigger the Jenkins for updating/recreating the old task.
- To enable the Webhook, go to the Github setting--> Developer settings--> Personal access tokens. Generate the tokens by marking repo, admin:repo_hook, user, read:packages
- Create the Jenkins Pipelines and use the GItHub secret text option to save the token and then mark the option the option Git Hook trigger for GITSCM pooling under built section.
- Enter the AWS credentials- the access_key_id  and secret_access_key.
- save the code/cnfiguration.

--  Use the below link for looking into the documentation:
#  [Terraform](https://www.terraform.io/docs/index.html) |  [Jenkins](https://jenkins.io/doc/) | [Github Pipeline](https://docs.gitlab.com/ee/ci/pipelines.html) 



> Note: Try to grab the understanding via hands-on. This will no only help you getting the concept but also help you to understand the flow and process.
 


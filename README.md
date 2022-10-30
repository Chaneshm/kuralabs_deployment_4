# kuralabs_deployment_4
Optimizing application infrastructure deployment 4

Deployment 4 Documentation found here: https://github.com/Chaneshm/kuralabs_deployment_4/blob/main/Dep4Documentation.pdf

Welcome to Kura Labs’ deployment 4 documentation. In this deployment we are utilizing terraform in order to provision a vpc as well as deploying a web server to one of the subnets through the use of an ec2 instance.

# Intro
To start we must create our Jenkins Server. For this deployment we must also installed terraform on our jenkins machine. To streamline this process I have appended terraform installation to a userdata script which also installs jenkins.

# AWS IAM Config
We will be using an AWS IAM user in order to deploy our infrastructure to the cloud. To do this we must first create an IAM user that has the AdministratorAccess policy. You must have both keys for this user.
# Configuring Jenkins

Download the Jenkins Addon Pipeline Keep Running Step

In the Jenkins Dashboard, click on manage Jenkins and then select Manage Credentials

Now select Global

On the right, Select Add Credentials

Now enter the First credentials:

○ Select “Secret text” for Kind

○ Scope should be Global

○ Secret: Copy and Paste your aws access key

○ ID: AWS_ACCESS_KEY

○ Select Create

Now enter the Second credentials:

○ Select “Secret text” for Kind

○ Scope should be Global

○ Secret: Copy and Paste your aws secret key

○ ID: AWS_SECRET_KEY

○ Select Create

Before you build your pipeline and execute, observe the Jenkinsfile, initTerraform folder and all files in the initTerraform folder.

Once you have successfully run your deployment and check your application. Add a destroy stage to the Jenkinsfile

The updated jenkinsfile can be found at https://github.com/Chaneshm/kuralabs_deployment_4/blob/main/Jenkinsfile

You may now build your pipeline

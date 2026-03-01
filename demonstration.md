📌 DEMONSTRATION – Launching EC2 Using Terraform (Local State)
Hey, actually to understand IaC I decided to launch an EC2 instance by using Terraform. Here I will say what are the steps I followed and what troubleshooting I have done to make the project successful.

Firstly, login to your AWS Console and create an access key under your profile by clicking on Security Credentials. Make sure these are very private and secure, and not supposed to be shared with anyone. While working in a production environment, it can create more vulnerabilities.

Ok, create an access key. Open your CMD. Here I will use WSL Ubuntu, which is provided by default in Windows, along with PowerShell. We will use WSL Ubuntu, or if you are comfortable with Windows PowerShell, you can do this demo using PowerShell commands.

Next, go to AWS CLI documentation and install it using the official documentation. Download the file, extract the zip file, and install AWS CLI. After installation, check whether it is installed or not by using:

"aws --version"

Then you need to configure it with your AWS account to talk with AWS API services. That’s why we create access keys — to allow the CLI to communicate and implement creating resources using CLI. It will reflect in the UI while we are doing it.

Configure your AWS account by using:

"aws configure"

Give your credentials and complete the login.

After configuration, clone my repository by using:

git clone "https://github.com/ChaitanyaArasada/my_first_terraform_project
"

After that, go inside the repository and do:

ls -a

You will find my_first_terraform_project. Now:

"cd my_first_terraform_project"

Inside that:

cd "aws"
cd "local_state"

Then run:

ls

You will find a file called main.tf.

While doing this demo, it is always good to go with local_state and see what is inside the file using:

"cat main.tf"

You will see the details of what we are going to create. The script tells that Terraform talks to the API requesting to create an EC2 instance.

Ok, then let’s go to Terraform. Search in Google for Terraform. It is developed by HashiCorp. Install your supported version. I installed it using wget for Ubuntu by following documentation.

Also see the documentation of AWS Terraform — we will find all the details about how to write scripts according to our infrastructure.

Install Terraform and check whether Terraform is installed or not by using:

"terraform -version"

Later, initialize Terraform by using:

"terraform init"

So that Terraform can talk to local files and understand what we are creating and what is inside the file.

Then we know that Terraform lifecycle to implement is:

First use:

"terraform plan"

It will tell what Terraform is going to create.

Then:

"terraform apply"

It shows what it is creating and asks for your confirmation.

Confirm by typing:

yes

Then you will see it creates the EC2 instance. It will give all the information about the EC2 name, instance ID, public IP address, and private IP address. This means we successfully completed this demo.

Make sure as a DevOps engineer we need to build our infrastructure to be cost optimized. Check cost estimation while building infrastructure for your enterprise — this is very important.

Lastly, to delete and remove the created instance using Terraform, we use:

"terraform destroy -y"

This will tell you that it is collapsing the infrastructure and ask for your confirmation. This is best practice before running the destroy command.

After running destroy, you will see in your AWS UI that the instance is shutting down.

🎯 Objective


The objective of this demonstration was to understand Infrastructure as Code (IaC) by provisioning an AWS EC2 instance using Terraform with local state management. This implementation shows how Terraform communicates with AWS APIs to automate infrastructure creation instead of using the AWS Console manually.

🛠 Step 1: Create AWS Access Keys

Login to AWS Console

Navigate to Profile → Security Credentials

Create a new Access Key
<img width="1880" height="716" alt="access keys" src="https://github.com/user-attachments/assets/2f728cd2-d2e0-4b90-8687-1dca5f58af44" />

⚠️ Important Note:
Access Keys are highly sensitive credentials. In production environments, they must be securely stored and never shared publicly, as exposing them can lead to serious security vulnerabilities.

🖥 Step 2: Setup Environment (WSL / Ubuntu / PowerShell)

For this demo, WSL Ubuntu was used. However, the same steps can be executed using Windows PowerShell.

☁ Step 3: Install AWS CLI

Download and install AWS CLI from official AWS documentation.

After installation, verify using:

<aws --version>

This confirms that AWS CLI is successfully installed.
<img width="1920" height="906" alt="Screenshot (199)" src="https://github.com/user-attachments/assets/bb916bbd-7249-4b42-a9f3-ac0466492eb7" />


🔐 Step 4: Configure AWS CLI

To allow the CLI to communicate with AWS APIs, configure your credentials:

<aws configure>

Provide:

AWS Access Key

AWS Secret Key

Default region

Output format

This configuration enables CLI-based interaction with AWS services. Any resource created via CLI or Terraform reflects in the AWS Console UI because both communicate through AWS APIs.

📥 Step 5: Clone Terraform Project Repository

Clone the repository:

<git clone https://github.com/ChaitanyaArasada/my_first_terraform_project>

Move inside the project:

<ls -a>
<cd my_first_terraform_project>
<cd aws>
<cd local_state>
<ls>

Inside this directory, you will find:

main.tf

To inspect the file:

<cat main.tf>

This file contains the Terraform configuration that defines the EC2 instance resource. Terraform reads this file and sends API requests to AWS to provision the infrastructure.

🏗 Step 6: Install Terraform

Terraform is developed by HashiCorp. Install Terraform using official documentation (Ubuntu installation via wget was used in this demo).

Verify installation:

<terraform -version>
<img width="1920" height="906" alt="Screenshot (199)" src="https://github.com/user-attachments/assets/76f77b16-d6d2-49dc-8bb0-769057974126" />


If the version is displayed, Terraform is installed successfully.

🔄 Step 7: Initialize Terraform

Before provisioning resources, initialize Terraform:

<terraform init>

Explanation:
This command initializes the working directory, downloads required provider plugins (AWS provider), and prepares Terraform to read local configuration files.

📋 Step 8: Terraform Plan

Preview infrastructure changes:

<terraform plan>
<img width="1920" height="968" alt="terraform-plan" src="https://github.com/user-attachments/assets/8ffb7c14-1569-4f06-8574-a76ba5cde068" />

This command:

Reads the configuration file

Compares desired state with current state

Displays what resources will be created

It does not create resources yet — it only shows the execution plan.

🚀 Step 9: Apply Infrastructure

Execute:

<terraform apply>
<img width="1920" height="981" alt="terraform-apply" src="https://github.com/user-attachments/assets/f2fb68e5-d769-4857-bf7d-e20e0c86486f" />

Terraform will display planned actions and request confirmation.

Type:

yes

Terraform will:

Send API request to AWS

Create EC2 instance

Display output including:

Instance ID

Public IP

Private IP

Resource details

After successful execution, the EC2 instance becomes visible in the AWS Console.
<img width="1920" height="720" alt="instance-running" src="https://github.com/user-attachments/assets/299de989-41fa-48f1-ad58-387d7e89cc91" />

💰 Cost Optimization Awareness

As DevOps engineers, infrastructure must always be cost-optimized. Before deploying resources in enterprise environments, cost estimation and resource sizing should be carefully reviewed. Even for demo purposes, unnecessary resources should not be left running.

🧨 Step 10: Destroy Infrastructure
<img width="1920" height="940" alt="instance-destroyed" src="https://github.com/user-attachments/assets/50af9c45-715c-4bf0-ab86-896c125b69c5" />

To remove created infrastructure:

<terraform destroy -y>

Terraform will:

Ask for confirmation

Send API requests to terminate the EC2 instance

Collapse the infrastructure defined in the configuration

After execution, you can verify in AWS Console that the instance is shutting down and terminated.
<img width="1920" height="714" alt="instance-shutting-down" src="https://github.com/user-attachments/assets/14e3d01b-6631-4bff-890f-1c74f6893798" />

🧠 Key Concepts Learned

Infrastructure as Code (IaC)

Terraform lifecycle (init → plan → apply → destroy)

How Terraform communicates with AWS APIs

AWS CLI configuration

Local state management

Secure handling of Access Keys

Cost awareness in cloud environments


🏁 Conclusion

This demonstration successfully shows how Terraform can automate AWS EC2 provisioning using local state management. Instead of manually launching instances from the AWS Console, infrastructure was defined in code and provisioned through API communication. This reflects modern DevOps practices used in real-world cloud environments.

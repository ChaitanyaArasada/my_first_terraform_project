📌 DEMONSTRATION – Launching EC2 Using Terraform (Local State)
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
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f0d0074a-fca7-4757-9b90-f99c754e8291" />

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
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e188934f-3bb7-4f22-88cc-ede9b8bde14e" />

If the version is displayed, Terraform is installed successfully.

🔄 Step 7: Initialize Terraform

Before provisioning resources, initialize Terraform:

<terraform init>

Explanation:
This command initializes the working directory, downloads required provider plugins (AWS provider), and prepares Terraform to read local configuration files.

📋 Step 8: Terraform Plan

Preview infrastructure changes:

<terraform plan>

This command:

Reads the configuration file

Compares desired state with current state

Displays what resources will be created

It does not create resources yet — it only shows the execution plan.

🚀 Step 9: Apply Infrastructure

Execute:

<terraform apply>

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

💰 Cost Optimization Awareness

As DevOps engineers, infrastructure must always be cost-optimized. Before deploying resources in enterprise environments, cost estimation and resource sizing should be carefully reviewed. Even for demo purposes, unnecessary resources should not be left running.

🧨 Step 10: Destroy Infrastructure

To remove created infrastructure:

<terraform destroy -y>

Terraform will:

Ask for confirmation

Send API requests to terminate the EC2 instance

Collapse the infrastructure defined in the configuration

After execution, you can verify in AWS Console that the instance is shutting down and terminated.

🧠 Key Concepts Learned

Infrastructure as Code (IaC)

Terraform lifecycle (init → plan → apply → destroy)

How Terraform communicates with AWS APIs

AWS CLI configuration

Local state management

Secure handling of Access Keys

Cost awareness in cloud environments

🔍 Troubleshooting Faced During Implementation

Some common issues encountered and resolved:

AWS CLI not recognized → Fixed by verifying installation path

Incorrect credentials during <aws configure> → Reconfigured properly

Terraform provider download issue → Resolved after <terraform init>

Region mismatch error → Ensured correct region in CLI configuration

These troubleshooting steps ensured successful infrastructure provisioning.

🏁 Conclusion

This demonstration successfully shows how Terraform can automate AWS EC2 provisioning using local state management. Instead of manually launching instances from the AWS Console, infrastructure was defined in code and provisioned through API communication. This reflects modern DevOps practices used in real-world cloud environments.

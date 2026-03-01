Hi Abhishek,

I hope you are doing well. My name is Chaitanya, and I have been following your content since February 2025. I have been learning from your AWS DevOps Zero to Hero course as part of my upskilling journey. Considering the current uncertainty in the job market, I am focusing on strengthening both cloud-based DevOps skills and on-premises DevOps tools to build a well-rounded foundation.

While learning Terraform in your AWS DevOps course, you consistently emphasize the importance of understanding automation properly and building strong fundamentals. You mention that to truly understand infrastructure automation, we should have clarity on CI/CD concepts and revisit the relevant playlists whenever needed. That guidance helped me connect the bigger picture between infrastructure provisioning and automation.

During the Terraform demo project where we provision an EC2 instance, I encountered a real-time issue while running terraform apply. The AMI ID specified for the us-west-2 region was no longer valid, and Terraform returned an error stating that the AMI ID was incorrect.

Initially, I wasn’t aware that AMI IDs are region-specific and may change periodically. Instead of getting stuck, I approached it as a troubleshooting opportunity.

I logged into the AWS Console, selected the correct region, navigated to EC2 → AMIs, identified the updated AMI ID, and modified the value inside main.tf.

Your sessions on Git and Linux were extremely helpful here. Since I had already cloned the repository locally, I followed the proper workflow:

git status to check changes

git add . to stage

git diff to verify

git commit -m "Updated AMI ID in main.tf"

git push

I also used Vim to edit the file directly and then pushed the changes.

After updating the configuration, I executed:

terraform init

terraform plan

terraform apply

This time, the EC2 instance was created successfully.

Before deprovisioning the infrastructure, I followed best practices. Instead of directly running terraform destroy, I first executed:

terraform plan -destroy

This clearly showed that Terraform was about to remove the complete infrastructure. Then I ran:

terraform destroy

Terraform asked for confirmation by requiring me to type “yes” before proceeding. As we know, AWS resources incur costs (except within free tier limits), so properly destroying infrastructure after testing is a responsible and important practice.

I am now planning to perform the same demo using a remote backend (S3 remote state) and integrate it with Jenkins for automation. I understand that storing Terraform state in S3 improves reusability, collaboration, and reliability. However, I feel I need to strengthen my hands-on experience with Jenkins before implementing that integration fully. Managing individual services feels easier now, but integrating everything into a complete automated pipeline is something I want to master properly.

I truly appreciate your structured approach to teaching — connecting Git, Linux, Terraform, CI/CD, and AWS into one practical DevOps journey.

Congratulations on building such impactful content. It genuinely helps learners like me build real confidence and practical understanding.

Thank you for your guidance.

Best regards,
Chaitanya



<img width="1920" height="874" alt="CLI" src="https://github.com/user-attachments/assets/44ce7683-ffc8-4ceb-9b1e-1cf6a8cbd397" />



<img width="1920" height="938" alt="troubleshooting1" src="https://github.com/user-attachments/assets/b392277b-cb4e-466a-93b1-485c1038e24c" />



<img width="1920" height="874" alt="git-actions" src="https://github.com/user-attachments/assets/d47eb5c8-037b-43e9-83cd-94767e9c2388" />


<img width="1920" height="960" alt="terraform-plan" src="https://github.com/user-attachments/assets/9b409e81-0f99-403d-b48d-de0ff14c27f1" />


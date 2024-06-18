Creating an EC2 Instance with Ansible
This project demonstrates how to create an EC2 instance on AWS using Ansible.

### Prerequisites
* An AWS account with an IAM user possessing EC2 permissions.
* Python, Pip, boto, boto3, and Ansible installed on your local machine.
* An SSH key pair generated using `ssh-keygen`.

### Steps
1. **Configure AWS IAM User:**
   - If you don't have an IAM user with EC2 permissions, create one in the AWS Management Console.
2. **Install Software:**
   - Install Python, Pip, boto, boto3, and Ansible on your local machine. Refer to their respective documentation for installation instructions.
3. **Prepare Local Files:**
   - Create a project directory for your Ansible project.
   - Generate an SSH key pair using `ssh-keygen`. Store the public key securely.
4. **Set Up Ansible Vault:**
   - Ansible Vault is used to store sensitive information like AWS access keys.
   - Follow the Ansible documentation to set up a vault using either a password or automated access.
5. **Create Ansible Playbook:**
   - Create a file named `playbook.yml` in your project directory.
   - Copy the provided Ansible playbook code (refer to the original article for the code) into this file. 
   - Update the playbook with your AWS credentials and desired EC2 instance configuration.
6. **Run Playbook:**
   - Open a terminal in your project directory.
   - Run the following command to execute the playbook, including tags and vault password options:

   ```bash
   ansible-playbook playbook.yml --tags create_ec2 --vault-password-file vault.pass
   ```
7. **Connect to EC2 Instance:**
   - Find the public DNS of your newly created EC2 instance in the AWS Management Console.
   - Use the `ssh` command with your private key to connect to the instance:

   ```bash
   ssh -i <your_private_key> ubuntu@<public_dns_of_instance>
   ```

**Note:** Replace `<your_private_key>` with the path to your private key file and `<public_dns_of_instance>` with the actual public DNS retrieved from the AWS console.

This README provides a basic guide.

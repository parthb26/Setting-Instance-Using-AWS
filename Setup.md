## Setup Instructions

### 1. Using the AWS Management Console
1. Log in to your [AWS Management Console](https://aws.amazon.com/console/).
2. Navigate to the **EC2 Dashboard**.
3. Click **Launch Instance** and configure the following:
   - **AMI**: Choose an Amazon Machine Image (e.g., Amazon Linux 2 AMI).
   - **Instance Type**: Select an instance type (e.g., `t2.micro` for free-tier eligibility).
   - **Key Pair**: Choose an existing key pair or create a new one for SSH access.
   - **Security Group**: Configure rules to allow required traffic (e.g., HTTP, HTTPS).
   - **Storage**: Specify the root volume size (default: 8GB).
4. Review and click **Launch** to create the instance.

### 2. Using the AWS CLI
1. Open your terminal and ensure AWS CLI is installed and configured.
2. Run the following command to create an EC2 instance:
   ```bash
   aws ec2 run-instances \
     --image-id ami-0abcdef1234567890 \ # Replace with your desired AMI ID
     --count 1 \
     --instance-type t2.micro \
     --key-name MyKeyPair \             # Replace with your key pair name
     --security-group-ids sg-0123456789abcdef0 \ # Replace with your security group ID
     --subnet-id subnet-0abcd1234efgh5678       # Replace with your subnet ID
   ```
   Replace /path/to/your-key.pem with the path to your private key file and <PUBLIC_IP_ADDRESS> with your instance's IP.
### 3. Configuring the Instance
   Update the system:
   ```bash
    sudo yum update -y
   ```
   Install necessary packages:
   ```bash
    sudo yum install -y httpd
   ```
### 4. Stopping or Terminating the Instance
  To stop or terminate the instance, use the AWS Management Console or the following CLI commands:
  - Stop the instance:
  ```bash
  aws ec2 stop-instances --instance-ids <INSTANCE_ID>
  ```
  - Terminate the instance:
  ```bash
  aws ec2 terminate-instances --instance-ids <INSTANCE_ID>
  ```

### Notes
  Always ensure your IAM user or role has the necessary permissions.
  Choose the appropriate region for your instance.

### License
  This project is licensed under the MIT License. See the LICENSE file for details.
  ```bash
This version focuses purely on creating the instance. You can handle the SSH connection in a separate README or file. Let me know if you'd like that!
```

    

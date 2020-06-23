# Learn-aws-by-doing


# Create an EC2 Instance

- You'll need to create an EC2 instance in the AWS console.

    Navigate to the EC2 portion of the console
    
    Click launch instance
    
    Allow cli connection
    
    Go through the configuration steps
    
    Create a keypair and download it to your machine
    
    Launch the instance

- Use the EC2 Instance to Create an S3 bucket with the AWS CLI and Send a message with SNS

    
    Login to your EC2 workstation using the ssh key created
    
    Update the system with sudo yum update -y
    
    Use the AWS CLI to create an S3 bucket
    
    - configure
    
    [ec2-user@ip-10-0-0-75 ~]$ aws configure
    
    AWS Access Key ID [None]:
    
    AWS Secret Access Key [None]:
    
    Default region name [None]: us-east-1
    
    Default output format [None]:
    
    - check
    
    [ec2-user@ip-10-0-0-75 ~]$ aws dynamodb list-tables
    {
        "TableNames": []
    }


    [ec2-user@ip-10-0-0-75 ~]$ aws s3 ls
    
    
    - create a s3 bucket using CLI
    
    [ec2-user@ip-10-0-0-75 ~]$ aws s3 mb s3://moh-cool-cda-test-bucket
    
    make_bucket: moh-cool-cda-test-bucket
    
    [ec2-user@ip-10-0-0-75 ~]$ aws s3 ls
    
    - 
    [ec2-user@ip-10-0-0-75 ~]$ sudo pip install boto3
    
    
    
    [ec2-user@ip-10-0-0-75 ~]$ python
    
    >>> import boto3
    
    
    >>> sns = boto3.client('sns')
    
    
    >>> phone_number = '+16457353214'
    
    
    >>> sns.publish(Message='Hellp from Mohamad!',PhoneNumber=phone_number)
    
    
    - to exit from python shell
    
    CTL c, CTL d   
    


    
      
    Install boto3 with sudo pip install boto3
    
    Open the Python interpreter with python
    
    Use the commands shown in the video to send yourself a text message with SNS
    
    
    



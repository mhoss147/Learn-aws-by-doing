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
    
    - install boto3
    
    [ec2-user@ip-10-0-0-75 ~]$ sudo pip install boto3
    
   # if you get error message follow these steps:
    
    - determine if Python 3 is already installed on the host.

            [ec2-user ~]$ yum list installed | grep -i python3
            
            
        

        - Python 3 not installed output example

        [ec2-user ~]$ yum list installed | grep -i python3
        [ec2-user ~]$

        [ec2-user ~]$ python3
        -bash: python3: command not found


        - 

        - Python 3 already installed output example:

        [ec2-user ~]$ yum list installed | grep -i python3

        python3.x86_64                        3.7.4-1.amzn2.0.4              @amzn2-core
        python3-libs.x86_64                   3.7.4-1.amzn2.0.4              @amzn2-core
        python3-pip.noarch                    9.0.3-1.amzn2.0.1              @amzn2-core
        python3-setuptools.noarch             38.4.0-3.amzn2.0.6             @amzn2-core

- [ec2-user ~]$ whereis python3


            python3: //usr/bin/python3 /usr/bin/python3.7 /usr/bin/python3.7m /usr/lib/python3.7 /usr/lib64/python3.7 /usr/include/python3.7m /usr/share/man/man1/python3.1.gz
            
            
- Create a virtual environment under the ec2-user home directory 


[ec2-user ~]$ python3 -m venv my_app/env


- Activate the virtual environment and install Boto 3

[ec2-user ~]$ source ~/my_app/env/bin/activate

(env) [ec2-user ~]$
    
 - Make sure that you have the latest pip module installed within your environment.
 
 (env) [ec2-user ~]$ pip install pip --upgrade
 
 
 - Use the pip command to install the Boto 3 library within our virtual environment.
 
 (env) [ec2-user ~]$ pip install boto3
 
   
    [ec2-user@ip-10-0-0-75 ~]$ python
    
  # send text messages
  
    
    >>> import boto3
    
    
    >>> sns = boto3.client('sns')
    
    
    >>> phone_number = '+16457353214'
    
    
    >>> sns.publish(Message='Hellp from Mohamad!',PhoneNumber=phone_number)
    
    
    - to exit from python shell
    
    CTL c, CTL d   
    


    
      
    Install boto3 with sudo pip install boto3
    
    Open the Python interpreter with python
    
    Use the commands shown in the video to send yourself a text message with SNS
    
    
    



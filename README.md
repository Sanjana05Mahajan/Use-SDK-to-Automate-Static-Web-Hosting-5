Use SDK to Automate Static Web Hosting-5
📌 Project Overview
This project demonstrates how to automate static website hosting on AWS using Python SDK (boto3) and Amazon S3.

The main objective of this project is to upload website files automatically to an S3 bucket using Python scripts instead of manual uploading. This automation helps simplify deployment and improves efficiency in cloud operations.

This project provides practical understanding of AWS SDK automation and static website hosting concepts.

🎯 Objective
Automate static website deployment
Upload files to S3 using Python
Reduce manual deployment work
Learn AWS SDK automation
Host static website on Amazon S3
🧰 AWS Services & Tools Used
1. Amazon S3
Used to host the static website files.

2. boto3
AWS SDK for Python used to automate S3 operations.

3. Python
Used to write automation scripts.

4. AWS IAM
Used to provide permissions for accessing AWS services.

🏗️ Project Architecture
The project workflow includes:

Creating S3 bucket
Enabling static website hosting
Writing Python automation script
Uploading website files using boto3
Making files publicly accessible
Accessing hosted website through S3 endpoint
⚙️ Step-by-Step Implementation
Step 1: Create S3 Bucket
Open AWS Console
Go to S3 Dashboard
Click Create Bucket
Enter unique bucket name
Disable Block Public Access
Create bucket
Step 2: Enable Static Website Hosting
Open bucket properties
Enable:
Static Website Hosting
Add:
Index document: index.html
Save changes.

Step 3: Configure Bucket Policy
Add public access policy to allow website access.

Example policy:

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
Step 4: Install boto3
Install boto3 using pip:

pip install boto3
Step 5: Configure AWS Credentials
Run:

aws configure
Provide:

AWS Access Key
Secret Access Key
Region
Output format
Step 6: Create Python Automation Script
Create Python file:

upload.py
Example script:

import boto3

s3 = boto3.client('s3')

bucket_name = 'your-bucket-name'

files = ['index.html']

for file in files:
    s3.upload_file(file, bucket_name, file)

print("Website uploaded successfully")
Step 7: Upload Website Files
Run the script:

python upload.py
Website files will automatically upload to S3 bucket.

Step 8: Access Hosted Website
Open S3 static website endpoint URL in browser.

Verify website loads successfully.

📸 Project Screenshots
🔹 S3 Bucket
image
🔹 Static Website Hosting
image
🔹 Bucket Policy
image
🔹 Python Script
image
🔹 Upload Process
image
🔹 Website Output
image
✅ Features
Automated deployment
Static website hosting
Faster uploads
Reduced manual work
Cloud automation using Python
Easy file management
Scalable storage
📚 Learning Outcomes
Through this project, I learned:

How Amazon S3 works
Static website hosting configuration
How boto3 automates AWS services
Python scripting for cloud automation
Bucket policy configuration
AWS SDK integration concepts
🚀 Future Improvements
Add CI/CD pipeline
Automate bucket creation
Add CloudFront CDN
Configure HTTPS support
Add automated file synchronization
🏁 Conclusion
This project successfully demonstrates static website hosting automation using Amazon S3 and Python SDK (boto3). The automation process reduces manual deployment effort and improves efficiency in cloud operations.

👩‍💻 Author
Sanjana Mahajan

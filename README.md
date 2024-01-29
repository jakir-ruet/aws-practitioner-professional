[![Youtube][youtube-shield]][youtube-url]
[![Facebook-Page][facebook-shield]][facebook-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

## Visit Us [Lapis Soft](http://www.lapissoft.com)

### AWS Certified DevOps Engineer Professional

This is designed for individuals who have experience working in a DevOps role and using AWS services. This certification validates your knowledge and skills in various areas related to implementing and managing continuous delivery systems and methodologies on the AWS platform. Key topics covered in the AWS Certified DevOps Engineer – Professional exam include:

- ***SDLC Automation:*** Implementing and managing continuous delivery systems and methodologies.
- ***Configuration Management and Infrastructure as Code (IaC):*** Implementing and managing the deployment pipeline, including infrastructure as code (IaC).
- ***Monitoring and Logging:*** Implementing monitoring and logging systems on AWS.
- ***Policies and Standards Automation:*** Implementing systems that are highly available, scalable, and self-healing on the AWS platform.
- ***Incident and Event Response:*** Designing, managing, and maintaining tools to automate operational processes.
To prepare for the exam, it's recommended to have hands-on experience with various AWS services and understand how to design, manage, and maintain tools for automating operational processes. Additionally, reviewing the official exam guide provided by AWS, along with relevant AWS documentation and whitepapers, can help you prepare effectively.

1. AWS CLI
   - Control multiple AWS services from this command line.
   - How to [Install?](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
   - Let's me check `aws --version`
   - If its okay then we will see `aws-cli/2.15.4 Python/3.11.6 Darwin/23.2.0 exe/x86_64 prompt/off`
   - Configuration using security credential
     - Go to AWS Management Console > Services > IAM
     - Select the IAM User Name: Your User Name [_**NB**_: You must use IAM's Information only not Root User]
     - Click on `Security credentials`
     - Click on `Create access key`
     - Copy Access ID & Secret access key
     - Go to your Terminal and implement as below format
     - `aws configure`
     - AWS Access Key ID [None]: Put your ID here and press Enter.
     - AWS Secret Access Key [None]: Put your secret key here and press Enter
     - Default region name [None]: us-east-1
     - Default output format [None]: json
   - Let's me check whether the configuration is done.
     - `aws ec2 describe-vpcs`
     - If it is done then we will see the details of the default vpc.

## Courtesy of Jakir

LinkedIn [Profile](https://www.linkedin.com/in/jakir-ruet/)
Facebook [Profile](https://www.facebook.com/jakir.ruet)
GitHub [Profile](https://github.com/jakir-ruet)
Skype [Profile](https://web.skype.com/?openPstnPage=true)

## Have a good day, stay with me

[youtube-shield]: https://img.shields.io/badge/-Youtube-black.svg?style=flat-square&logo=youtube&color=blue&logoColor=red
[youtube-url]: https://www.youtube.com/@LapisSoft/featured
[facebook-shield]: https://img.shields.io/badge/-Facebook-black.svg?style=flat-square&logo=facebook&color=pink&logoColor=blue
[facebook-url]: https://www.facebook.com/GoLapisSoft/
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=red
[linkedin-url]: https://www.linkedin.com/company/lapis-soft/



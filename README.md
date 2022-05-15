# ServianTechChallenge

AWS Cloudformation template is used to achieve this challenge.
AWS Components: 
![image](https://user-images.githubusercontent.com/105404955/168459184-8eb8314a-8cd9-4171-a9d5-6a0df403b0aa.png)


Infrastructure Architecture:

![image](https://user-images.githubusercontent.com/105404955/168459155-ed8a8ed5-d21c-4c15-816d-e36f6847d09a.png)


 
Explanation: 

•	Inbound Traffic is routed through an Application load Balancer exposed to the internet.

•	NAT Gateways are used for ECS Fargate to connect with Internet to download Images from Docker hub. It’s deployed in twp AZ for high availability.

•	ECS Cluster creates Fargate instances in 2 AZ’s if it met CPU Usage target.

•	ALB is hosted in public subnet to connect with Internet.

Execution: 

•	Provide customised IP addresses to create VPC and Container related information in master.yml file as per requirement.

•	Import master.yml file whie creating CloudFormation stack as the template and create it.

•	Upon creation is successful, it automatically creates the environment for ServianTechChallenge app to run.







CI CD Design: 

![image](https://user-images.githubusercontent.com/105404955/168459165-1121384d-27c8-4f22-ad96-9b0e31be59c2.png)

 
Code Pipeline can orchestrate the deployment of Cloud formation stack execution.

Handling Environment Variables for the Docker Container:

-	SSM Parameter store can be used for this. 

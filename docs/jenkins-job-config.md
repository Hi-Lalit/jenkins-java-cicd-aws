# Jenkins Freestyle Job Configuration

## Source Code Management
- GitHub repository
- Branch: main

## Build Step
Execute shell:
mvn clean package

## Post-Build Action
- Deploy to Container plugin
- WAR file: webapp/target/*.war
- Tomcat URL: http://<EC2-IP>:8080

## SSH Configuration
- Connected Jenkins to EC2 using PEM key
- Example:
ssh -i /var/lib/jenkins/.ssh/ec2.pem ubuntu@<EC2-IP>

## Trigger
- GitHub Webhook (push-based)
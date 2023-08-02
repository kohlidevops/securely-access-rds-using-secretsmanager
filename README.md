# How to securely access the RDS Instance using Secrets Manager
**To securely access Amazon RDS instance using secrets manager**

**Step-1: Create RDS Instance**

Navigate to AWS RDS console - create new RDS instance with MySQL engine

![rds1](https://github.com/kohlidevops/securely-access-rds-using-secretsmanager/assets/100069489/bb62f8b1-c38b-4a59-a19a-2320e5b127cf)

**Step-2: Create a table in RDS Database**

Connect the MySQL Database with MySQL client from local machine
Create a employees table in demodb

![rds2](https://github.com/kohlidevops/securely-access-rds-using-secretsmanager/assets/100069489/c7d85a88-f2cf-4790-9617-b4170b141313)

**Step-3: To insert a values into employees table**

To copy the code using below link and paste it on local machine

https://github.com/kohlidevops/securely-access-rds-using-secretsmanager/blob/main/access-rds-from-localmachine

Then run the code from local machine

Install mysql-connector if doesn't exist

pip3 install mysql-connector

![rds3](https://github.com/kohlidevops/securely-access-rds-using-secretsmanager/assets/100069489/7b5263b9-92e9-49a3-b41c-8551905954b8)

To check the employees table

![rds4](https://github.com/kohlidevops/securely-access-rds-using-secretsmanager/assets/100069489/6d91cb38-e1cb-49ba-b052-bbcdd839e3f0)

**Step-4: Create a secret in Secrets Manager**

To create a new secret with secret type - Credentials for Amazon RDS database and provide credentials

![rds5](https://github.com/kohlidevops/securely-access-rds-using-secretsmanager/assets/100069489/1d74f792-e673-414c-bdea-ec90fb853cdd)

To encrypt your credentials with KMS key and select your RDS instance

![rds6](https://github.com/kohlidevops/securely-access-rds-using-secretsmanager/assets/100069489/07f3eff6-0e5d-46b2-a2e2-5e8255bddd76)

Provide the secret name and finally review & create

![rds7](https://github.com/kohlidevops/securely-access-rds-using-secretsmanager/assets/100069489/0df9f5b2-583f-4ddb-8b56-a436d717fd7e)

![rds8](https://github.com/kohlidevops/securely-access-rds-using-secretsmanager/assets/100069489/ba9c0ebc-5856-4fa7-9b6c-bece4730a0ee)

**Step-5: To create IAM user**

To create a IAM user with limited policy - Secrets Manager Read Write Access

Create a access key and secret key for this user

![rds9](https://github.com/kohlidevops/securely-access-rds-using-secretsmanager/assets/100069489/6dddeba2-b47b-4784-9587-720d91774c50)

**Step-6: Configure the AWS**

To configure the AWS and provide the access key and secret key in local machine.

#aws configure

**Step-7: To execute the code to connect secrets manager for access RDS instance**

To copy the code using below link and paste it on local machine. In this code, we didn't add the credentials inside the code. We will access the RDS credentials such as DB name, user name, password and RDS endpoint from secrets manager.

https://github.com/kohlidevops/securely-access-rds-using-secretsmanager/blob/main/access-rds-using-secrets-manager

Run the python code again in local machine

Install boto3 in local machine, if doesn't exist

#pip3 install boto3

![rds10](https://github.com/kohlidevops/securely-access-rds-using-secretsmanager/assets/100069489/c27af322-3f8a-43de-be45-66789ba586d0)

![rds11](https://github.com/kohlidevops/securely-access-rds-using-secretsmanager/assets/100069489/56800aeb-a74b-42cf-972e-11a74e625838)


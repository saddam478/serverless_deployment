Acrhitecture diagram:


![image](https://github.com/user-attachments/assets/b19ad89f-a481-40d5-96ad-d675313ab380)


Tools and services which are used for the setup:

 Git, GitOps, AWS IAM, S3, Lambda, Api-Gateway and Cognito.  

Steps include in ci/cd pipeline:

 1. When the pipeline get triggered a sequence of steps will be executed.
 2. First the pipeline will checkout the code in its local workspace.
 3. Setup aws cli to perform actions on aws cloud and configure aws environment with access key and secret key of user [who is having access to S3 & lambda] that will be passed as secrets during the pipeline execution.
 4. Files will get deployed to s3 bucket using aws cli.
 5. Package/bundle the files and deploy to aws lambda.
 6. Api-gateway is configured in such a way that it will invoke lambda funcation and send back the reponse.
 7. once the pipeline successfully executed. you can access the api-gateway url "https://sd2okqzcke.execute-api.ap-south-1.amazonaws.com/dev"


Steps to test and verify the application:

 1. Change the content of app/logged_in.html file from "Hello world!!!" to "Hello world!!! from AWS" & vice versa and push the changes to git repo.
 2. Pipleine will get auto trigger post the changes commited.
 3. Navigate to actions and look for most recently executed job with job status as success.
 4. Now hit the api-gatway url "https://sd2okqzcke.execute-api.ap-south-1.amazonaws.com/dev" you will see "welcome to the site!!" home page.
 5. Get the user registration if its not done ealier.
 6. Once the registration is successful, kinldy login with the user credentials.
 7. If username and passsword entered correctly, you will prompt to "congratulation !!" logged in page.
 8. once you logged in and visualize "Hello World !!!", you can logged off by using the provided link.

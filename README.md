## Description

This is a simple react project created to build a CI/CD pipeline using Docker, Travis CI and AWS.

## Requirements

- Github account
- TravisCI account linked to your Github account
- AWS account

## Configuration

    1. In your AWS account, navigate to Elastic Beanstalk and create a new web environment using Docker as a platform.
    
    2. While Beanstalk is being created, navigate to the IAM service, create a new user with programatic access 
       and attach an ElasticBeanstalkFullAccess policy to it.
       DO NOT FORGET to downlaod your access key and secret values at the end.

    3. Clone this project into your own Github repo.

    4. Navigate to Travis CI, find the Github repo you just created and go to settings.
       There, find the topic "Environment Variables" and add "AWS_ACCESS_KEY" and "AWS_SECRET_KEY"
       with the values from de .CSV you download from AWS before.

    5. In the actual project, locate the file .travis.yml and under the deploy tag update
       region, app, env, bucket_name and bucket_path according to the values from your own Beanstalk environment.
       In the end, commit and push your changes.

    6. Finally, on Travis, locate your repo again and toggle the switch to start watching your Github repo.
       After a few minutes, Travis should build and deploy your application to Beanstalk.

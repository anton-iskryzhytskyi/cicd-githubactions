0. build image `docker build -t lab-web-app .`
1. deploy ECR, `cdk deploy --app 'npx ts-node cdk/ecr.ts'`
2. get login credentials for ecr `aws ecr get-login-password --region eu-west-1 | docker login --username AWS --password-stdin 646858379215.dkr.ecr.eu-west-1.amazonaws.com`
3. tag image in ecr `docker tag lab-web-app:latest 646858379215.dkr.ecr.eu-west-1.amazonaws.com/lab-web-app:latest`
4. push image to ecr `docker push 646858379215.dkr.ecr.eu-west-1.amazonaws.com/lab-web-app:latest`
5. cdk deploy --app 'npx ts-node cdk/ecs.ts'

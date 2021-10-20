# aws-serverless
Repo to practice and learn the fundamentals on serverless development using aws, localstack and serverless framework

## Testing
To test this project with localstack you should invoke the api based on the next endpoint pattern:
http://localhost:4567/restapis/<rest_api_id>/local/_user_request_/<method_path>

So for our project the url will be similar to (depending on the rest api id genereated) :
http://localhost:4566/restapis/x7c9sxi6gv/local/_user_request_/api/v1/person

## Deployment:
Based on how the project is configure, you will have at least 2 profiles, a default one with dummy credentials and the one for the real aws account that you will use to test everything in the cloud.

So if yo execute 
```sh
aws configure list-profiles 
```
then you should get something similar to this:
- default
- personal-account

This is necessary to separate the deployments from localstack and the aws account.
Once you have configure it and execute a successful deploy in your localstack then
you can try to deploy in your real aws account by executing:

```sh
sls deploy --aws-profile personal-account --stage develop --verbose
```

Don't forget to remove all the artifacts once you have finished the exercise by executing:
```sh
sls remove --aws-profile personal-account --stage develop --verbose
```


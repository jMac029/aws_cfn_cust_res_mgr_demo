# CFN Custom Resource Manager demo
* Fork the github repo: https://github.com/tonyfruzza/aws_cfn_cust_res_mgr_demo into your own git account.
* Modify the icon list to the custom list provided through direct message
* Launch the runway project in your lab account make the necessary modifications to have a unique S3 bucket for web hosting.
* Once launched update the static html file to point to your newly launched API GW end point.
* Be prepared answer the questions in a direct message before the due date

### Questions
1. What is the URL to your forked git repo of the project?
   1. https://github.com/jMac029/aws_cfn_cust_res_mgr_demo
2. What is the URL to your web hosted static S3 bucket?
   1. S3 bucket: http://display-api-dev-jmacs-static-site.s3-website-us-west-2.amazonaws.com/
3. What is your web hosted static s3 bucket policy?
   1. 
   ```
   {
    "Version": "2008-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::display-api-dev-jmacs-static-site/*"
        }
    ]
    }
    ```
4. What is the github URL to the serverless framework plugin that was used to upload the static s3 content? 
   1. https://github.com/k1LoW/serverless-s3-sync
5. What is the name of the lambda function launched for managing the custom cloudformation resources? 
   1. cfn-res-mgr-demo-lookup
6. What is the name of the table that the state of the resources are stored in?
   1. cfn-res-mgr-dev-state
7. Which javascript library is used to draw the icons?
   1. paper-full.js
8.  Which headers need to be present from the API server to allow for CORS?
    1.  `crossDomain: true,`
    2.  `'Access-Control-Allow-Origin': '*'`
9.  What common ID type is used for the physical resource ID?
    1.  `MyCustomResource` ?
10. Do custom resource lambda functions require IAM permissions to interact with cloudformation (not including the IAM managed role permission in AWSLambdaBasicExecutionRole)?
    1.  NO, it requires IAM permission to interact with other AWS resources such as DynamoDB and CloudWatch Logs so it can write to them etc.
    2.  the name of the CF stack is within the tags of the function and updated with the ARN once it has been launched from what I can tell...

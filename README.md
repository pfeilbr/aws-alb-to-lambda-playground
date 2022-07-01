# aws-alb-to-lambda-playground

learn ALB to Lambda integration

## Demo

> based on [alexcasalboni/template.yml](https://gist.github.com/alexcasalboni/9f118ac10a59a5c4eb6bfd75d0a65773) - AWS ALB - AWS Lambda integration with CloudFormation (YAML)

lambda function code is inlined in [`template.yaml`](template.yaml)

```sh
# deploy stack
sam deploy

# check our ALB andpoint
curl http://aws-a-myLoa-MFYJ9QBS4CCL-673155384.us-east-1.elb.amazonaws.com

# output:
# <h1>Hello from Lambda via ALB</h1><pre><code>{
#   "requestContext": {
#     "elb": {
#       "targetGroupArn": "arn:aws:elasticloadbalancing:us-east-1:529276214230:targetgroup/aws-a-myTar-1OF41QMSUR19N/c81f17d663a5ef3a"
#     }
#   },
#   "httpMethod": "GET",
#   "path": "/",
#   "queryStringParameters": {},
#   "headers": {
#     "accept": "*/*",
#     "host": "aws-a-myLoa-MFYJ9QBS4CCL-673155384.us-east-1.elb.amazonaws.com",
#     "user-agent": "curl/7.79.1",
#     "x-amzn-trace-id": "Root=1-62bf13a2-7ec6c217009df4474336906d",
#     "x-forwarded-for": "100.11.104.251",
#     "x-forwarded-port": "80",
#     "x-forwarded-proto": "http"
#   },
#   "body": "",
#   "isBase64Encoded": false
# }</code></pre>

# check path based listener (`/api/*`)
curl http://aws-a-myLoa-MFYJ9QBS4CCL-673155384.us-east-1.elb.amazonaws.com/api/hello

# output:
# <h1>Hello from Lambda via ALB</h1><pre><code>{
#   "requestContext": {
#     "elb": {
#       "targetGroupArn": "arn:aws:elasticloadbalancing:us-east-1:529276214230:targetgroup/aws-a-myTar-1OF41QMSUR19N/c81f17d663a5ef3a"
#     }
#   },
#   "httpMethod": "GET",
#   "path": "/api/hello",
#   "queryStringParameters": {},
#   "headers": {
#     "accept": "*/*",
#     "host": "aws-a-myLoa-MFYJ9QBS4CCL-673155384.us-east-1.elb.amazonaws.com",
#     "user-agent": "curl/7.79.1",
#     "x-amzn-trace-id": "Root=1-62bf27ec-5b6861564ac9b30938dd1e67",
#     "x-forwarded-for": "100.11.104.251",
#     "x-forwarded-port": "80",
#     "x-forwarded-proto": "http"
#   },
#   "body": "",
#   "isBase64Encoded": false
# }</code></pre>       


# clean up
sam delete --no-prompts
```

![](https://www.evernote.com/l/AAFKcNmrSp9LmromFVQwcH5E6g6vEBMCVfsB/image.png)

## Resources

- [alexcasalboni/template.yml](https://gist.github.com/alexcasalboni/9f118ac10a59a5c4eb6bfd75d0a65773) - AWS ALB - AWS Lambda integration with CloudFormation (YAML)
- [Lambda functions as targets for Application Load Balancers](https://aws.amazon.com/blogs/networking-and-content-delivery/lambda-functions-as-targets-for-application-load-balancers/)
- [Application Load Balancer can now Invoke Lambda Functions to Serve HTTP(S) Requests](https://aws.amazon.com/about-aws/whats-new/2018/11/alb-can-now-invoke-lambda-functions-to-serve-https-requests/)
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
# output: <h1>Hello from Lambda via ALB</h1>

# clean up
sam delete --no-prompts
```

![](https://www.evernote.com/l/AAFfE-cFcjhHeZjv-CsGf-xQ7BbXmSFryYYB/image.png)

## Resources

- [alexcasalboni/template.yml](https://gist.github.com/alexcasalboni/9f118ac10a59a5c4eb6bfd75d0a65773) - AWS ALB - AWS Lambda integration with CloudFormation (YAML)
- [Lambda functions as targets for Application Load Balancers](https://aws.amazon.com/blogs/networking-and-content-delivery/lambda-functions-as-targets-for-application-load-balancers/)
- [Application Load Balancer can now Invoke Lambda Functions to Serve HTTP(S) Requests](https://aws.amazon.com/about-aws/whats-new/2018/11/alb-can-now-invoke-lambda-functions-to-serve-https-requests/)
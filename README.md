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
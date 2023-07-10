# Deploying from Console

1. Go to Inferense in Sagemaker menu.
2. Go to Endpoints Configurations.
3. Create endpoint configuration and add a Production Variant using a pretrained model and using serverless.
4. Go to Endpoints.
5. Create Endpoint using an existing endpoint configuration.
6. Invoke endpoint using this code:

```
  runtime = boto3.client("sagemaker-runtime")

  endpoint_name = "First-Abalone-Endpoint"
  content_type = "text/x-libsvm"
  payload = "17 1:2 2:0.555 3:0.435 4:0.165 5:0.97 6:0.336 7:0.2315 8:0.295"

  response = runtime.invoke_endpoint(
    EndpointName=endpoint_name,
    ContentType=content_type,
    Body=payload
  )
```
Remember to close the endpoint aftrer finishing.

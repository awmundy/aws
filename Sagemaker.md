Sagemaker Overview
- Domain
  - Has what is called a Domain, which contains an Elastic File System (EFS), list of a
  uthorized users, and a bunch of security stuff
- IDE
    - Amazon has a web based IDE for Sagemaker
    - It is possible to use Pycharm to interact with sagemaker as well
        - https://aws.amazon.com/blogs/machine-learning/use-the-amazon-sagemaker-local-mode-to-train-on-your-notebook-instance/
        - Requires installing the pycharm Software Developer Kit (SDK)
        - Requires some docker container stuff to make your local dev environment the same as the cloud one
        - Once everything is set up, there one line of code in your ml script that would determine whether
        the code is being run locally or in the cloud
- Compute
  - Sagemaker spins up servers as needed to train, do inference, etc
  - Some of scaling of the servers (i.e. to handle different amounts of data) is at least somewhat automated
- Contains many services that aim to help with a lot of the ML pipeline
  - Data prep
  - Automated model tuning
  - Data labelling
- Can be interacted with in multiple ways
  - Through your AWS account in the browser
  - Command Line Interface
  - IDE like Pycharm, once you set it up

Sagemaker Quickstart
- Create a Sagemaker domain
    - The domain is a context within which models can be dev'd and deployed
    - This probably won't be needed at the job, it's probably already existing there
    - https://console.aws.amazon.com/sagemaker?refid=gs_card
        - Click the 1 minute domain quickstart button and follow instructions, the default
        options are probably fine
    - Now when you search AWS for Sagemaker and click the link, you will be taken to your Sagemaker console
- Create a Sagemaker Studio notebook
    - This will be a browser based IDE
    - Follow the Step 2 instructions here:
        - https://aws.amazon.com/getting-started/hands-on/machine-learning-tutorial-build-model-locally/
- Deploy the model and set up endpoints for it to be accessed
    - https://aws.amazon.com/getting-started/hands-on/machine-learning-tutorial-deploy-model-to-real-time-inference-endpoint/
    - Model is saved to an S3 bucket
    - The model is then converted to a Sagemaker model using the python sagemaker library
        - It will show up in the Sagemaker Console under Inference
    - An endpoint cofiguration and endpoint are then created using the python sagemaker libary.
    This endpoint will allow the model to be used by any person/applicaton that has access
    to the endpoint
        - The endpoint configuration and endpoint are then visible in the Sagemaker console under Inference
        - NOTE: I could produce the endpoint configuration but not the endpoint due to a restriction
        by AWS for me that would require a support ticket to resolve
    - One way to interact with the endpoint is by using the AWS python library boto3
        - Serialized data is sent to the endpoint and predictions are returned
- Using Pycharm as the IDE
    - https://aws.amazon.com/blogs/machine-learning/run-your-tensorflow-job-on-amazon-sagemaker-with-a-pycharm-ide/
    - Install the Python Sagemaker SDK to allow python/pycharm to interact with Sagemaker
        - activate your env, then 'pip install sagemaker'
    - Install the AWS CLI
      - https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
    - Install Docker
      - https://docs.docker.com/get-docker/
    - Set aws credentials using aws configure
    - Set some Sagemaker environmental variables (data, model, and output paths)
    - INCOMPLETE











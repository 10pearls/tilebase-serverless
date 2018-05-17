# Tilebase Serverless

Serverless application of GDAL2Tiles from [Map tiler](http://www.maptiler.org/google-maps-coordinates-tile-bounds-projection/).

Implementation is based on AWS Serverless Application Model (SAM).

## Setup

#### Step 1:
Build AWS CodePipeline and CodeBuild configrations from the `cloudformation` folder. Simply upload the files on any S3 bucket and launch a CloudFormation stack with `main.yaml`.

This will build the following
- IAM Roles required for building/running the pipeline (pipeline-roles.yaml)
- CodePipeline for pulling source, building and publishing code (pipeline.yaml)

#### Step 2:
Edit and push code on your repository to trigger the pipeline. `saml.yaml` defined the configuration for deploying AWS Lambda functions and configuring AWS API Gateway as their event source.

#### Files:

- `saml.yaml`
Serverless Application specification
- `beta.json`
Defines the `beta/stage` environment configuration
- `buildspec.yaml`
Defines AWS CodeBuild specification


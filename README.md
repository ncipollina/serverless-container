# serverless-container
This repository contains the source code for my video on building and deploying C# container images to AWS Lambda via the Serverless framework.

## Project Structure

This starter project consists of:
* Function.cs - class file containing the C# method mapped to the single function declared in the template file
* serverless.yml - configuration file containing the definition of the Lambda function and all associated resources
* Dockerfile - the definition for the docker container that our serverless application will be hosted in

The generated project contains a Serverless template declaration for a single AWS Lambda function that will be exposed through Amazon API Gateway as a HTTP *Get* operation. 

## Video Links
* [YouTube](https://youtu.be/NOEvrRr74Uw)
* [Odysee](https://odysee.com/serverless-container-csharp:71c98553fe63a1835a2c1284509435e260fb8c8d)
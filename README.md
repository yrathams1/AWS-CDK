Name: 
Dynamo DB Global Table CDK Deploy using Typescript with custom IAM role/policy naming convention

Description:
When trying to deploy a Dynamo DB global table, CDK generates nested stacks with many unexpected default roles. If your customer AWS environment mandates to deploy roles and policies with a fixed set of custom prefixes, then this is the work-around.

Usage:
1. Pre-requisites:
  a. CDK v2 Installation on your machine from which you want to run this script
  https://docs.aws.amazon.com/cdk/v2/guide/getting_started.html
  https://docs.aws.amazon.com/cdk/v2/guide/cli.html
  b. CDK Bootstrap - cdk bootstrap is a tool in the AWS CDK command-line interface responsible for populating a given environment (that is, a combination of AWS account and region) with resources required by the CDK to perform deployments into that environment.
  https://docs.aws.amazon.com/cdk/v2/guide/bootstrapping.html
  NOTE: The roles deployed via CDK bootstrap can also have custom names. However, that implementation is not a part of this artifact.
2. After you download the typescript file, make sure to replace the following:
  a. <your-custom-prefix> with the prefix name you want
  b. <aws-region-1>, <aws-region-2>, <aws-region-3> with the AWS replication regions.
  c. <your-default-managed-policy-name> with the name you choose for your default customer managed policy.
  NOTE: You are asked to choose the default name and a Random number is appended at the last because the default name CDK assigns is lengthy and ~120 characters. Since there is a limit of 128 characters on the policy name, it is customized this way.
3. On your command line interface, type the following commands one after another:
  cdk ls <Lists the stacks in the app>
  cdk synth <Synthesizes and prints the CloudFormation template for the specified stack(s)>
  cdk deploy <Deploys the specified stack(s)>
  NOTE: Respond to another prompts during the CDK deploy stage. For example enter y/n to deploy the table?

Roadmap: 
Add an existing permissions boundary to the newly created roles

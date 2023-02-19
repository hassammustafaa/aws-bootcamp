# Prerequisites
Github Account Creation
Gitpod Account Creatuion and install extension for your browser
Create Github Codespace
Setup AWS Account 
Create Lucid Chart Account ( for architure diagrams )
Setup Honeycomb.io account
Create a Rollbar account

# Week 0 — Billing and Architecture
Q: If we sign-up for Consolidated Billing, can we get the AWS Free Tier for each account?

No, customers that use Consolidated Billing to consolidate payment across multiple accounts will only have access to one Free Tier per Organization.

Q: If I don’t use all of my free usage per month will it roll over to the next month?

No, the AWS Free Tier is applied to your monthly usage. It will expire on the 1st day of each month, and does not accumulate.

Q: If I go over the Free Tier limit in a given month, how much will I have to pay?

If your usage exceeds the monthly free tier limits, you simply pay standard, pay-as-you-go AWS service rates. See the AWS Pricing page for full pricing details.

Q: How do I know how much I’ve used and if I’ve gone over the free usage tiers?

You can see current and past usage activity by service and region by logging into your account and going to the Billing & Cost Management Dashboard. From there you can manage your costs and usage using AWS Budgets, visualize your cost drivers and usage trends via Cost Explorer, and dive deeper into your costs using the Cost and Usage Reports. To learn more about how to control your AWS costs, check out the Control your AWS costs 10-Minute Tutorial.

Q: I’m eligible for the free usage tier, but I received a charge. Why?

The AWS Free Tier is available to new AWS accounts. The free tier applies to certain participating AWS services up to a specific maximum amount of usage each month. Applicable services and usage limits are defined at aws.amazon.com/free. When an account goes over the free tier limit, the standard AWS service rates will be billed to your credit card.

If you have not exceeded the limits of the free tier, you may have been charged for other AWS services that are not covered under the free tier. Some examples include: if you are running an Amazon EC2 t2.small instance rather than a t2.micro instance, or if you are using a service not included in the offer, such as Amazon Aurora. To review your AWS usage activity, log into your Billing & Cost Management Dashboard.

# AWS Calculator
We can use AWS calculator for price calculations of different services with any charges.

# Web application access control Lucid Chart Diagram

![Web application access control](https://user-images.githubusercontent.com/121938785/219964640-71c02988-337c-46b3-a11c-645d0ea076ce.png)


Link: https://lucid.app/lucidchart/c9aca9ba-e9ce-4ac9-a54b-3ffc306c1dd3/edit?beaconFlowId=72748E484B54D0B8&invitationId=inv_0bee99df-95ee-4bf2-9869-b00534339cda&page=0_0#

# AWS CLI
You can configure AWS CLI by following steps
Step 1: Open any terminal and write $ aws configure
Step 2: Give your AWS Access Key ID 
Step 3: Give your AWS Secret Access Key
Step 4: Select your AWS Default Region and Boom.

We can also configure it using AWS Cloudshell
This command create the budget and the same time retrive the account number

# AWS Budget Creation Using CLI

aws budgets create-budget \
--account-id=$(aws sts get-caller-identity --query Account --output text) \
--budget file://aws/json/budget.json \
--notifications-with-subscribers file://aws/json/budget-notifications-with-subscribers.json
    

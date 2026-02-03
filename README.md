# aws_cost_optimiztion
# AWS Cloud Cost Optimization - Identifying Stale Resources

## Identifying Stale EBS Snapshots

In this example, we'll create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

### Description:

The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.

#PROBLEM STATEMENT IN SIMPLE WORDS

A developer created an ec2 and then he performes his tasks evryday and saves the snpashot evryday ,after 1 month he completes all of his work and then deletes the ec2 but he forget to delete the snapshots 
now the problem is aws charges for this stored snapshots 
so enorder to delte the snapshots that are associated with volume but not associated with ec2 we are creating this project 

so the architecture for this project is as follows 
we will write a python code using lambda function , the module that is going to be used in python is boto3 and this python code will talk to the aws APIs therfore 
step 1 : fetch all the snapshots 
step2 : filter the snapshots that are stale 
step3 : delte the snapshots 


 

+++
title = 'First Experiences using AWS CDK'
date = 2024-06-25T19:02:47+10:00
draft = false
comments = false
+++
I've been using AWS CDK for the first time this week and overall it's been a good experience. Having a programmatic level of control when it comes to provisioning AWS resources and being able to apply different patterns to create SOLID software (pun intended) is what I enjoy about this tool.

***My work this week***

It's pretty much just been focused on designing some microservice architectures for message queues and caching. For both of these, I've been using AmazonMQ and ElastiCache with RabbitMQ and Redis engines respectively. CDK has been great for allowing me to do cost-saving tasks such as dynamically allocating instance types depending on what mode a stack is being deployed in.

***Docs can be tricky***

This could be due to my inexperience but one thing I am finding which is the docs can be a little bit all over the place to traverse. In my previous experiences using AWS, this is not a new concept I've discovered. That being said, this could be dependent on what type of resource you are working with (e.g. EC2 constructs were a lot easier for me to navigate compared to using `aws_elasticache`)

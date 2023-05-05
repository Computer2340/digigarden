---
title: "Infrastructure as Code"
---
When working with the cloud, you will have many different pieces of disposable infrastructure as part of your tech stack and platform solution. While your infrastructure can be cheaper in the cloud, it will most assuredly be more complicated. In order to ensure that each time you promote code between environments. As a human, you are fallible and prone to mistake making. How do you make sure your complicated infrastructure is consistent when you deploy it multiple times? Easy! You make an uncompromising, unwavering, unfeeling computer do it.

When you use an infrastructure as code tool like [[notes/Terraform|Terraform]], [[CloudFormation]], the [[AWS]] [[CDK]], or [[Pulumi]], you use some manner of programming language to describe your infrastructure. This means that your description of your infrastructure can be redeployed over and over consistently. In fact, repeatability is the main reason to use infrastructure as code, and it has some added benefits beyond just deploying the same thing to multiple environments.

# Consistency
Sorry, I know I just said it provides benefits outside of this, but I just wanted to make sure it was clear: A great thing about repeatable infrastructure is that all of your environments have the same set-up. You will still hear sporadically “But it works on my machine” but you should experience far less “Well it worked in the dev environment.” This consistency gives you deployment confidence as you promote your code from environment to environment. Additionally, you will also know that the tests you ran in one environment were valid and helpful for ensuring that no issues made it into production.

# Reusability
As you look at your code architecture, you might notice some patterns. You seem to have many serverless functions triggered by messaging queues. What if you could create a template for a messaging queue that triggers a lambda and reuse that template multiple times? Well, with infrastructure as code, you can! In [[notes/Terraform|Terraform]] there are modules, in [[CloudFormation]] there are nested stacks, and in [[CDK]] you can create functions and classes that return larger compositions of infrastructure.

# Testability
Do you actually need slightly different configurations per environment, but do need to guarantee certain interactions work every time? For example, do you have an external vendor interested in data in your staging environment that you don't want to reveal too much information about your automated test suite in your user acceptance testing environment? With infrastructure as code, you could write a test guaranteeing core interactions with a piece of information in a data store. Then write a configuration for a single environment to grant access to that information while also restricting it in all your other environments.

Further, you can also create mockup tests that would spoof your existence outside your organization to ensure that your infrastructure isn't telling the world more about your data than you mean it to. For advance testing purposes, you can make use of tools like Terratest for [[notes/Terraform|Terraform]] or regular testing tools for [[CDK]] or [[Pulumi]]. Most people though will find themselves using tools like [[checkov]], [[tfsec]], or other code validation tools that ship with basic sanity checks.

# Conclusion
> So should I be using infrastructure as code?

Yes.
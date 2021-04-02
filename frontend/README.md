# Cloud Resume Challenge Azure style

This is an example of the [Cloud Resume challenge](https://cloudresumechallenge.dev/instructions/) using Azure services.

Live demo is [here](https://www.gwynethpena.com/)

## Instructions

### 1. Certification

```Your resume needs to have the AWS Cloud Practitioner certification on it. This is an introductory certification that orients you on the industry-leading AWS cloud – if you have a more advanced AWS cert, that’s fine but not expected. No cheating: include the validation code on the resume. You can sit this exam online for $100 USD. If that cost is a dealbreaker for you, let me know and I’ll see if I can help. A Cloud Guru offers exam prep resources.```

The original challenge requires the [AWS Cloud Practitioner certification](https://aws.amazon.com/certification/certified-cloud-practitioner/) on your resume. That would be the [Azure Fundamentals AZ900](https://docs.microsoft.com/en-us/learn/certifications/exams/az-900)

## 2. HTML

```Your resume needs to be written in HTML. Not a Word doc, not a PDF. Here is an example of what I mean.```



## 3. CSS

```Your resume needs to be styled with CSS. No worries if you’re not a designer – neither am I. It doesn’t have to be fancy. But we need to see something other than raw HTML when we open the webpage.```



## 4. Static S3 Website

```Your HTML resume should be deployed online as an Amazon S3 static website. Services like Netlify and GitHub Pages are great and I would normally recommend them for personal static site deployments, but they make things a little too abstract for our purposes here. Use S3.```

We can use [Static website hosting in Azure Storage](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blob-static-website)

## 5. HTTPS

``` The S3 website URL should use HTTPS for security. You will need to use Amazon CloudFront to help with this.```

We can use [Azure CDN](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-custom-domain-name?tabs=azure-portal#map-a-custom-domain-with-https-enabled) for this.  

## 6. DNS

```Point a custom DNS domain name to the CloudFront distribution, so your resume can be accessed at something like my-c00l-resume-website.com. You can use Amazon Route 53 or any other DNS provider for this. A domain name usually costs about ten bucks to register.```
We can use [Azure CDN](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-custom-domain-name?tabs=azure-portal#map-a-custom-domain-with-https-enabled) for this. If you don't have a domain, might be a good idea to try [Azure DNS](https://docs.microsoft.com/en-us/azure/dns/dns-delegate-domain-azure-dns) for this.

## 7. Javascript

```Your resume webpage should include a visitor counter that displays how many people have accessed the site. You will need to write a bit of Javascript to make this happen. Here is a helpful tutorial to get you started in the right direction.```

 What if we used Blazor for the site, that would allow us to use c# and then we can create an Azure Function that updates a table storage or cosmos db with counter info. 

## 8. Database

```The visitor counter will need to retrieve and update its count in a database somewhere. I suggest you use Amazon’s DynamoDB for this. (Use on-demand pricing for the database and you’ll pay essentially nothing, unless you store or retrieve much more data than this project requires.) Here is a great free course on DynamoDB.```

The visitor counter will need to retrieve and update its count. We can use table storage or cosmosdb for this?

## 9. API

```Do not communicate directly with DynamoDB from your Javascript code. Instead, you will need to create an API that accepts requests from your web app and communicates with the database. I suggest using AWS’s API Gateway and Lambda services for this. They will be free or close to free for what we are doing.```

If we use an Azure Function to update cosmosDB or table storage, this will be handled by that.

## 10. Python

```You will need to write a bit of code in the Lambda function; you could use more Javascript, but it would be better for our purposes to explore Python – a common language used in back-end programs and scripts – and its boto3 library for AWS. Here is a good, free Python tutorial.```

You will need to write a bit of code in the Lambda function;
We'll use C# instead!

## 11. Tests

```You should also include some tests for your Python code. Here are some resources on writing good Python tests.```

C# tests.

## 12. Infrastructure as Code

```You should not be configuring your API resources – the DynamoDB table, the API Gateway, the Lambda function – manually, by clicking around in the AWS console. Instead, define them in an AWS Serverless Application Model (SAM) template and deploy them using the AWS SAM CLI. This is called “infrastructure as code” or IaC. It saves you time in the long run.```

Hmm, ARM then?

## 13. Source Control

```You do not want to be updating either your back-end API or your front-end website by making calls from your laptop, though. You want them to update automatically whenever you make a change to the code. (This is called continuous integration and deployment, or CI/CD.) Create a private GitHub repository for your backend code.```

We can use GitHub.

## 14. CI/CD (Back end)

```Set up GitHub Actions such that when you push an update to your Serverless Application Model template or Python code, your Python tests get run. If the tests pass, the SAM application should get packaged and deployed to AWS.```

We can use [GitHub actions too for static website in Azure Storage](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blobs-static-site-github-actions)

## 15. CI/CD (Front end)

```Create a second private GitHub repository for your website code. Create GitHub Actions such that when you push new website code, the S3 bucket automatically gets updated. (You may need to invalidate your CloudFront cache in the code as well.) Important note: DO NOT commit AWS credentials to source control! Bad hats will find them and use them against you!```

We can use Azure keyvault for any credentials, do we need separate repos for front end and backend?

## 16. Blog post

```Finally, in the text of your resume, you should link a short blog post describing some things you learned while working on this project. Dev.to is a great place to publish if you don’t have your own blog. And that’s it. When you have done all this, add my GitHub username @forrestbrazeal as a collaborator on your repositories. If you need a job in the cloud, and you have met the conditions listed above, I will give you a personalized code review, then make as much noise about you as I can to anybody who will listen (including sharing your awesome blog post!)```

We can create our separate blog posts and reference this as our instruction/

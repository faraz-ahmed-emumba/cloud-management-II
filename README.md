# Design a CI/CD on AWS CodePipeline to serve a static webpage through S3 on AWS Cloud-front, with ACM certificate
[Solution Architecture](/cloud-management-ii.jpg?raw=true)
## Modules
-  AWS S3 Bucket
-  AWS CodePipeline
-  AWS Certificate Manager
-  AWS Cloud Front

### AWS S3 Bucket
Create a S3 bucket to host the static webpages of the website. Enable "Host a Static Website" and allow public access.

### AWS CodePipeline
- Add Source Stage and link GH repo using AWS Connector App.
- Skip Build Stage as we are deploying a pre-built website.
- Add Deploy Stage

### AWS Certificate Manager
- Request a public certificate against a FQDN of website. Also, request a wildcard certificate for the same.
- Select DNS Validation

### AWS Cloud Front
Create Cloud Front Distribution with the following settings:
-   Allow OAI (Origin Access Identity)
-   Add Alternate Domain Name (CNAME)
-   Redirect HTTP to HTTPS
-   Associate SSL Certificate generated using ACM

# Huddle (Sample Website)
Say hello to Huddle, a bold, techy site template.

[Papaya](https://www.papayatemplates.com)
[@jrdnbwmn](https://www.twitter.com/jrdnbwmn)

Demo images from [Unsplash](https://unsplash.com/).
Icons from [Entypo](http://entypo.com/).

## Instructions
For local development, run `npm install` on the main directory and then `gulp` to get BrowserSync going along with all the Gulp tasks (see [Pear](https://github.com/jrdnbwmn/Pear)).

Development files are in `src`. Everything is compiled into `dist`—that’s where all your final files reside.

# Shielded-Cloud-App-3
This is a sequel, so please start from the first part.

## 🟡 Phase 4: Deploy CloudFront


1. Configure CloudFront (CDN) for Your Load Balancer
This will improve performance by caching content and reducing direct load on your instances.

Steps to Set Up CloudFront:
  1. Go to the AWS CloudFront Console

Navigate to CloudFront → Click Create Distribution.
Configure Origin Settings

Origin Domain → Enter your ALB's DNS name (e.g., App-Server-Loadbalancer-xyz.us-east-1.elb.amazonaws.com).
Origin Protocol Policy → Choose HTTPS only for secure traffic.
Allowed HTTP Methods → Choose GET, HEAD, OPTIONS, PUT, POST, PATCH, DELETE (for full support).
Enable Origin Shield → (Optional, but recommended for reducing requests to origin).
Set Default Cache Behavior

Viewer Protocol Policy → Select Redirect HTTP to HTTPS.
Allowed HTTP Methods → Select GET, HEAD, OPTIONS for static content.
Forward Headers → Choose All if your app requires it.
Object Caching → Use Managed-CachingOptimized for standard caching behavior.
Add Alternate Domain Names (Optional)

If using a custom domain, add it here and configure an SSL certificate via AWS Certificate Manager.
Review & Create Distribution

Click Create Distribution and wait for it to deploy.
Note the CloudFront Distribution Domain Name (e.g., d123.cloudfront.net).

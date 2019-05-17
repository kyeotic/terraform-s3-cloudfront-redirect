# terraform-s3-cloudfront-redirect

A Terraform module to create an AWS Cloudfront Distribution backed by an S3 Bucket

## Usage

```hcl
module "kyeotic_redirect" {
  source    = "github.com/kyeotic/terraform-s3-cloudfront-redirect?ref=1.0.0"
  site_name = "www.your-website.com"
  redirect_to =  "your-website.com"
  cert_arn  = "${var.your-cert-arn}"
}

```

## Variables

- `site_name` - The domain for your site, (e.g. `www.example.com` or `blog.example.com`)
- `redirect_to` - The domain to redirect to, (e.g. `example.com`)
- `cert_arn` - Full ARN for an AWS Certificate Manager cert in the `us-east-1` region

## Outputs

- `cloudfront_domain` - `"${aws_cloudfront_distribution.site.domain_name}"`
- `cloudfront_hosted_zone_id` - `${aws_cloudfront_distribution.site.hosted_zone_id}"`

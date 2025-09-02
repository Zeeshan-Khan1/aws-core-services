# 11. Static Web Site Hosting in S3

## Hosting a Website Directly from a Cloud Bucket

One of the most popular use cases for Amazon S3 is hosting **static websites**. A static website contains fixed content (HTML, CSS, JavaScript, images) that is delivered to the user's browser exactly as stored, with no server-side processing.

## How It Works

Instead of a traditional web server (like Apache or Nginx), you configure an S3 bucket to serve the HTML files directly. When a user requests your site, S3 fetches the corresponding file from the bucket and delivers it.

### Benefits of Hosting on S3:

-   **Cost-Effective:** You only pay for the storage and data transfer used. It's incredibly cheap for low-to-medium traffic sites.
-   **Highly Scalable:** S3 automatically scales to handle massive traffic spikes without any intervention.
-   **Highly Available & Durable:** Built on AWS's robust infrastructure.
-   **Simple:** No servers to manage, patch, or secure.

## Key Requirements

1.  **Static Content:** Your site must be built with static files (e.g., `.html`, `.css`, `.js`, `.jpg`, `.png`). It cannot run PHP, Ruby, Python, or other server-side code.
2.  **Public Read Access:** The bucket and objects must have appropriate permissions to be read by the public.
3.  **Index Document:** You must specify a default page (usually `index.html`) that S3 will serve when someone visits the root of your site.
4.  **Error Document (Optional but Recommended):** You can specify a custom error page (e.g., `error.html`) to be displayed for 4xx errors.

## The S3 Website URL

When you enable static website hosting, S3 provides you with a special website endpoint URL. This is different from the standard S3 object URL.

-   **Standard Object URL:** `https://<your-bucket-name>.s3.<region>.amazonaws.com/index.html`
-   **Website Endpoint URL:** `http://<your-bucket-name>.s3-website-<region>.amazonaws.com`

**Note:** The website endpoint uses `http`, not `https`. For a production website, you would use Amazon CloudFront and AWS Certificate Manager to serve content over HTTPS with a custom domain.

---

**Next:** [Simple Hosting of a WordPress Site](../SECTION-4-DATABASES/12-wordpress-on-ec2.md)

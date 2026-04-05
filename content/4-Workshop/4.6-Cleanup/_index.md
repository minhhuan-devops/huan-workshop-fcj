---
title : "Cleanup"
date : 2024-01-01 
weight : 6
chapter : false
pre : " <b> 4.6. </b> "
---

#### Clean up resources

To prevent incurring monthly charges after completing the workshop, it is necessary to clean up storage and destroy all created resources.

**1. Empty the Amazon S3 Bucket:**
Certain resources, such as S3 buckets containing hosted static files, must be manually emptied via the AWS Console before the Terraform `destroy` command can successfully delete the bucket itself.

- Enter **S3** in the search bar and select the **S3** service.

![Search for S3 Service](/4-workshop/4.6-cleanup/image.png)

- Select the Frontend bucket (e.g., `fpt-event-bucket`).

![Select fpt-event-bucket](/4-workshop/4.6-cleanup/image-1.png)

- Select the bucket (or its contents) and click the **Delete** button.

![Select Delete](/4-workshop/4.6-cleanup/image-2.png)

- Type **permanently delete** into the system confirmation box and perform the deletion.

![Accept permanently delete](/4-workshop/4.6-cleanup/image-3.png)

**2. Destroy infrastructure via Terraform:**
Return to your command line (Terminal), navigate to the `infrastructure` directory, and run the automated cleanup command:

```bash
terraform destroy --auto-approve
```
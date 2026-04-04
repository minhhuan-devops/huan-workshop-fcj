---
title : "Clean up"
date : 2024-01-01 
weight : 6
chapter : false
pre : " <b> 4.6. </b> "
---

#### Clean up resources

To avoid incurring future charges after completing the workshop, you must tear down the infrastructure. Because we deployed via Terraform, this process is automated:

```bash
terraform destroy --auto-approve
```

Note: Some objects (such as populated S3 buckets that contain user uploads) may need to be emptied manually via the AWS Console before the teardown script can successfully proceed.
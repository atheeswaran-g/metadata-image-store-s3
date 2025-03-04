# metadata-image-store-s3
🛠 Services Used:

S3: For image storage
	.	Lambda: To capture the upload event and process metadata
	.DynamoDB: To store image metadata
==========================================================================
👣 Steps:
1️⃣ Create an S3 Bucket:
	.Go to the AWS S3 console.
	.Click "Create bucket" → Give it a unique name like image-upload-bucket-123.
	.Leave default settings and create the bucket.
==============================================================================
2️⃣ Create a DynamoDB Table:
	.Go to the AWS DynamoDB console.
	.Click "Create table".
	.Table name: ImageMetadataTable.
	.Partition key: filename (Type: String).
	.Click "Create".
 ===============================================================================
 3️⃣ Create a Lambda Function:
	.Go to the AWS Lambda console.
	.Click "Create function" → Choose "Author from scratch".
	.Function name: StoreImageMetadata.
	.Runtime: Python 3.12 (or your preferred language).
	.Click "Create function".
 ===============================================================================
 4️⃣ Attach IAM Permissions:
	.Go to the "Permissions" tab of your Lambda function.
	.Click on the attached IAM role.
	.Click "Add permissions" → "Attach policies".
	.Add these policies:
	.AmazonS3ReadOnlyAccess → To read image metadata.
	.AmazonDynamoDBFullAccess → To write data into DynamoDB.
 ================================================================================
 5️⃣ Write the Lambda Code:
	.Go to the "Code" tab and replace the default code with this:
	.Click "Deploy" when done.
==================================================================================
6️⃣ Add an S3 Trigger:
	.Go to the "Configuration" tab of your Lambda function.
	.Click "Add trigger" → Choose S3.
	.Select your S3 bucket (image-upload-bucket-123).
	.Event type: "PUT" (This captures new uploads).
	.Click "Add".
 ====================================================================================
7️⃣Test the Flow:
	.Upload an image to your S3 bucket via the AWS S3 console.
	.Go to DynamoDB and check the ImageMetadataTable.
 ====================================================================================
 8️⃣ Cleanup (Optional):
	.Delete the S3 bucket if no longer needed.
	.Delete the DynamoDB table.
	.Delete the Lambda function.
 ====================================================================================





 

 

To verify an object's integrity using the ETag, you can follow these steps:

1. **For Single PUT Uploads**: If the object was uploaded in a single PUT operation without server-side encryption, the ETag will be the MD5 hex digest of the object data. You can calculate the MD5 checksum of the local file and compare it with the ETag provided by S3.

2. **For Multipart Uploads**: If the object was uploaded using Multipart Upload, the ETag will not be a straightforward MD5 digest. Instead, it will be the concatenated MD5 hex digests of each part's MD5 digest, followed by a hyphen and the number of parts. To verify the integrity, you would need to:
   - Calculate the MD5 checksum for each part of the file as it was uploaded.
   - Concatenate the binary representation of these checksums.
   - Calculate the MD5 checksum of this concatenated binary string.
   - Compare this value with the ETag, taking into account the number of parts.

3. **Using Additional Checksums**: Amazon S3 allows you to use additional checksum algorithms (CRC32, CRC32C, SHA-1, SHA-256) when uploading or copying your data. You can specify the algorithm and provide a precalculated checksum. Amazon S3 will calculate the checksum using the specified algorithm and compare it with the provided value. If they don't match, an error is reported¹.

4. **Using AWS Tools**: There are tools available that can help you verify the integrity of your data using the ETag. For example, scripts like `s3etag.sh` can be used to calculate the ETag of a local file and compare it with the ETag on S3³.

Remember, the ETag can be used to verify the integrity of the object as long as the object is not encrypted with server-side encryption. For encrypted objects, the ETag will not be the MD5 digest and cannot be used for integrity checks in the same way¹²³⁴.

Source: Conversation with Bing, 17/05/2024
(1) Checking object integrity - Amazon Simple Storage Service. https://docs.aws.amazon.com/AmazonS3/latest/userguide/checking-object-integrity.html.
(2) Verifying Amazon S3 multi-part uploads with the ETag hash. https://simplyexplained.com/blog/Verifying-Amazon-S3-multi-part-uploads-with-ETag-hash/.
(3) Enabling and validating additional checksums on existing objects in .... https://aws.amazon.com/blogs/storage/enabling-and-validating-additional-checksums-on-existing-objects-in-amazon-s3/.
(4) Check the integrity of an object uploaded to Amazon S3. https://repost.aws/knowledge-center/data-integrity-s3.
(5) Introducing s3verify: verify that a local file is identical to an S3 .... https://dev.to/aws-builders/introducing-s3verify-verify-that-a-local-file-is-identical-to-an-s3-object-without-having-to-download-the-object-data-1n73.
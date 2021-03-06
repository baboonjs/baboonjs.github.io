<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [@baboonjs/aws-buckets](./aws-buckets.md) &gt; [AWSBuckets](./aws-buckets.awsbuckets.md) &gt; [setEncryption](./aws-buckets.awsbuckets.setencryption.md)

## AWSBuckets.setEncryption() method

Turn default server side encryption of bucket files on or off.

<b>Signature:</b>

```typescript
setEncryption(bucketName: string, flag: boolean, options?: SetEncryptionOptions): Promise<void>;
```

## Parameters

|  Parameter | Type | Description |
|  --- | --- | --- |
|  bucketName | string | Bucket name |
|  flag | boolean | true if you want to encrypt files in this bucket by default |
|  options | [SetEncryptionOptions](./api-buckets.setencryptionoptions.md) | Options that allow specification of KMS key, encryption algo, etc. |

<b>Returns:</b>

Promise&lt;void&gt;

## Remarks

There are two options for encrypting bucket objects on the server side. Clients can either use a S3-managed key or a KMS key. For the first option, call this method without the <code>options</code> argument. or call it with <code>options.algorithm</code> set to "AES256".

Alternatively you can specify a KMS-managed key for encryption. You can do so by setting <code>options.algorithm</code> to "aws:kms" and optionally specifying your own key ID/ARN via <code>options.keyId</code>. If no key is specified, AWS will auto-generate a KMS key.

In case of KMS-managed key, this method sets the <code>BucketKeyEnabled</code> passed on to AWS to <code>true</code>. You can override this by specifying <code>options.disableBucketKey</code> to <code>true</code>.


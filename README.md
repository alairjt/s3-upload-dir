# S3-UPLOAD-DIR
Upload Directory to AWS S3

### Install

```ssh
npm install s3-upload-dir --save
```

### How To Use

##### Define AWS Environment Variables

- AWS_ACCESS_KEY_ID: User Access Key
- AWS_SECRET_ACCESS_KEY: Public Access Key


```javascript
var s3 = require('s3-upload-dir');

var params = {
    localDir: "DIR_NAME",
    s3Params: {
        Bucket: "YOUR_BUCKET_NAME"
    }
};

var uploader = s3.uploadDir(params);

uploader.on('error', function (err) {
    console.error("unable to upload:", err.stack);
});

uploader.on('progress', function () {
    console.log("progress", uploader.progressMd5Amount,
            uploader.progressAmount, uploader.progressTotal);
});

uploader.on('end', function () {
    console.log("done uploading");
    exit;
});

```
   
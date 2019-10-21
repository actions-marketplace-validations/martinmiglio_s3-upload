# s3-upload
Github Action to Upload to S3 Bucket

Uploads to S3 Bucket 

```
name: Test Run
on:
  push
jobs:
  lambda:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@master
      - run: echo "<html><head><title>GH Actions Test</title></head><body><h1>YO THIS WORKS!</h1></body></html>" > index.html
      - uses: stcalica/s3-upload@master
        with:
          bucket: temp-test-gh-action
          package: index.html
          key: index
          AWS_REGION: ${{ secrets.AWS_REGION }}
          AWS_SECRET_ID: ${{ secrets.AWS_SECRET_ID }}
          AWS_SECRET_KEY: ${{ secrets.AWS_SECRET_KEY }}
```

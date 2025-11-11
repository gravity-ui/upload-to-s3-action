# upload-to-s3-action

A generic GitHub action that uploads files to S3-compatible storage with configurable bucket and endpoint.

## Description

This action provides a flexible way to upload files or directories to any S3-compatible storage service (AWS S3, Yandex Cloud Storage, MinIO, etc.) by allowing you to configure the bucket name and endpoint URL.

## Inputs

- `src-path` (required) - Source directory or file to upload.
- `dest-path` (required) - Destination path in the S3 bucket (e.g., `/my-folder/subfolder`).
- `bucket` (required) - S3 bucket name.
- `endpoint-url` (required) - S3 endpoint URL (e.g., `https://storage.yandexcloud.net` for Yandex Cloud, `https://s3.amazonaws.com` for AWS).
- `s3-key-id` (required) - S3 access key ID.
- `s3-secret-key` (required) - S3 secret access key.
- `region` (required) - AWS region.

## Usage Example

```yaml
- name: Upload to S3
  uses: ./upload-to-s3-action
  with:
    src-path: ./build
    dest-path: /my-app/v1.0
    bucket: my-bucket-name
    endpoint-url: https://storage.yandexcloud.net
    s3-key-id: ${{ secrets.S3_KEY_ID }}
    s3-secret-key: ${{ secrets.S3_SECRET_KEY }}
    region: ru-central1
```

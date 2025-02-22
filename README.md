#Using python code source toimport to cloud storage

from google.cloud import storage

def upload_to_gcs(bucket_name, source_file_path, destination_blob_name):
    client = storage.Client()
    bucket = client.bucket(bucket_name)
    blob = bucket.blob(destination_blob_name)

    blob.upload_from_filename(source_file_path)
    print(f"File {source_file_path} uploaded to {destination_blob_name}")

upload_to_gcs("my-gcs-bucket", "localfile.txt", "uploads/localfile.txt")

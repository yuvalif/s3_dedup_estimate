# S3 Deduplication Estimation Tool
Reads ETAGs for all objects and use it to estimate duplication level

## Build
* first, you would need to install `podman` on your machine
* then execute:
```
podman build -t s3_dedup_estimate .
```

## Run
* to learn how to use the tool run:
```
podman run --rm s3_dedup_estimate`
```
This will output:
```
usage: /root/s3_dedup_estimate/s3_dedup_estimate [options]  

options:                                                   
   --sample-rate=rate                                   
        set the sampling rate (default sample 1/1)      
   --thread-count=count                                 
        set the number of threads to run (default 4 threads)        
   --endpoint=url:port                                  
        set the endpoint url of the s3 gateway (default http://127.0.0.1:8000)
   --access-key=key                                     
        set the access key to the S3 GW (default empty - take key from configuration)
   --secret-key=key
        set the secret key to the S3 GW (default empty - take key from configuration)
```
* for example, to use the tool run againts an RGW running locally and listening on port 8000, use:
```
podman run --rm s3_dedup_estimate --endpoint=http://localhost:8000 --access-key=<access key> --secret-key=<secret key>
```


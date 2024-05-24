If you’re uploading a zipped file using a curl command to a Spring Boot `@PostMapping` method, you would typically use the `-F` option to send the file as form data. Here’s an example of how you can do it:

```bash
curl -X POST [your-spring-boot-app-url]/upload \
-F "file=@/path/to/yourfile.zip;type=application/zip"
```

In this command:

- Replace `[your-spring-boot-app-url]` with the URL where your Spring Boot application is running.
- Replace `/path/to/yourfile.zip` with the actual path to the zipped file you want to upload.
- The `type=application/zip` part sets the MIME type of the file being uploaded to indicate that it’s a zip file.

[This command assumes that your Spring Boot application has a corresponding endpoint that is set up to handle `multipart/form-data` and has a parameter to receive the file, typically annotated with `@RequestParam("file") MultipartFile file` in your controller method](https://stackoverflow.com/questions/36551963/curl-post-multipart-file-to-spring-boot-rest-endpoint)[1](https://stackoverflow.com/questions/36551963/curl-post-multipart-file-to-spring-boot-rest-endpoint).
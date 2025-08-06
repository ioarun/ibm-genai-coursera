# Build the Docker image
```console
docker build -t nlp_foundation .
```
# Run the Docker container
```console
docker run -it -p 8888:8888 -v $(pwd):/workspace nlp_foundation
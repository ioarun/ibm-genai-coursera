# Build the Docker image
docker build -t nlp_foundation .

# Run the Docker container
docker run -it -p 8888:8888 -v $(pwd):/workspace nlp_foundation
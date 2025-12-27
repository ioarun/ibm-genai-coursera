# Build the Docker image
```console
docker build -t transformers .
```
# Run the Docker container
```console
docker run --rm -it -p 8888:8888 -v $(pwd):/workspace transformers
```
Then open your browser and go to `http://localhost:8888` to access Jupyter Notebook.
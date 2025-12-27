# Build the Docker image
```console
docker build -t pos_encoding .
```
# Run the Docker container
```console
docker run --rm -it -p 8888:8888 -v $(pwd):/workspace pos_encoding
```
Then open your browser and go to `http://localhost:8888` to access Jupyter Notebook.
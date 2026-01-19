# Build the Docker image
```console
docker build -t transformers .
```

# Setup GPU support (if applicable)
Make sure you have the NVIDIA Container Toolkit installed. Follow the instructions [here](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html) if you haven't done so.

```console
sudo nvidia-ctk runtime configure --runtime=docker
sudo systemctl restart docker

```


# Run the Docker container
```console
docker run --gpus all --rm -it -p 8888:8888 -v $(pwd):/workspace transformers
```
Then open your browser and go to `http://localhost:8888` to access Jupyter Notebook.
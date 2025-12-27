# Use the official Ubuntu image
FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Etc/UTC

# Update and install basic stuff
RUN apt-get update && apt-get install -y \
    curl \
    nano \
    python3 \
    pip 

# Install Python packages for attention mechanism and positional encoding notebook
RUN pip3 install "jinja2<3.1.0"
RUN pip3 install torch==2.1.0 torchtext==0.16.0 torchdata==0.6.1 Levenshtein
RUN pip3 install pandas numpy seaborn matplotlib scikit-learn pmdarima portalocker plotly dash jupyter


# Set working directory
WORKDIR /workspace

COPY attention_mechanism_and_pos_encoding.ipynb /workspace/attention_mechanism_and_pos_encoding.ipynb
COPY transformers_for_classification.ipynb /workspace/transformers_for_classification.ipynb

# Expose port for Jupyter
EXPOSE 8888

# Run Jupyter when the container starts
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]


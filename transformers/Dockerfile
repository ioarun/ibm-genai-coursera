# Use the official Ubuntu image
FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Etc/UTC

# Update and install basic stuff
RUN apt-get update && apt-get install -y \
    curl \
    wget \
    nano \
    python3 \
    python3-pip 

# Install Python packages for attention mechanism and positional encoding notebook
RUN pip3 install "jinja2<3.1.0"
RUN pip3 install torch==2.3.0 torchtext==0.18.0 torchdata==0.9.0 torchvision transformers Levenshtein spacy pdfplumber fpdf nltk
RUN pip3 install pandas numpy seaborn matplotlib scikit-learn pmdarima portalocker plotly dash jupyter 


# Set working directory
WORKDIR /workspace

COPY 1_attention_mechanism_and_pos_encoding.ipynb /workspace/1_attention_mechanism_and_pos_encoding.ipynb
COPY 2_transformers_for_classification.ipynb /workspace/2_transformers_for_classification.ipynb
COPY 3_decoder_gpt_like_models.ipynb /workspace/3_decoder_gpt_like_models.ipynb
COPY 4_pre_training_BERT.ipynb /workspace/4_pre_training_BERT.ipynb
COPY 5_data_preparation_for_BERT.ipynb /workspace/5_data_preparation_for_BERT.ipynb
COPY 6_transformers_for_translation.ipynb /workspace/6_transformers_for_translation.ipynb

# Expose port for Jupyter
EXPOSE 8888

# Run Jupyter when the container starts
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]


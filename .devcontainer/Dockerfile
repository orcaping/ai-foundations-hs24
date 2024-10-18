# Use an official Miniconda image as the base
FROM continuumio/miniconda3

# Set environment variables
ENV DEBIAN_FRONTEND=noninteractive

# Update and install dependencies
RUN apt-get update && apt-get install -y \
    wget \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Install the required Python packages using conda and pip
RUN conda install python=3.10 -y && \
    conda install pip jupyter numpy matplotlib seaborn -y && \
    conda install -c anaconda scipy -y && \
    conda install -c conda-forge scikit-learn -y && \
    pip install google-cloud-dialogflow
    

# Set the working directory
WORKDIR /exersises

# Mount local exercises directory into container
VOLUME [ "/exercises" ]

# Default command to start an interactive shell
CMD ["/bin/bash"]

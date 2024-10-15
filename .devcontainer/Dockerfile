# Use the official Python slim image
FROM python:3.10-slim

# Install system dependencies
RUN apt-get update && apt-get install -y \
    git \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Set up a working directory
WORKDIR /workspace

# Copy requirements from the root and install dependencies
COPY requirements.txt ./
RUN pip install -r requirements.txt

# Copy the .env file to the working directory
COPY .env ./

# Copy the entire project into the container
COPY . .

# Install Jupyter and dotenv to manage environment variables
RUN pip install jupyter python-dotenv

# Set up Jupyter config
RUN jupyter notebook --generate-config \
    && echo "c.NotebookApp.token = ''" >> /root/.jupyter/jupyter_notebook_config.py \
    && echo "c.NotebookApp.password = ''" >> /root/.jupyter/jupyter_notebook_config.py

# Expose Jupyter port
EXPOSE 8888

# Start Jupyter on container startup
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]

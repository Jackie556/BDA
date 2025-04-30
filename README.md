# Python Docker Project

This project demonstrates how to create a Docker container for a Python application. It includes a simple Python script, a Dockerfile to build the image, and a requirements.txt file for dependencies.

## Project Structure

```
python-docker-project
├── src
│   └── main.py
├── Dockerfile
├── requirements.txt
└── README.md
```

## Getting Started

To build and run this project, follow the steps below:

### Prerequisites

- Docker installed on your machine.
- Basic knowledge of Docker and Python.

### Building the Docker Image

1. Navigate to the project directory:

   ```bash
   cd python-docker-project
   ```

2. Build the Docker image using the following command:

   ```bash
   docker build -t python-docker-project .
   ```

### Running the Docker Container

After building the image, you can run the container with:

```bash
docker run python-docker-project
```

### Dockerfile Contents

The Dockerfile used for this project is as follows:

```dockerfile
# Use the official Python image from the Docker Hub
FROM python:3.13.2

# Set the working directory in the container
WORKDIR /app

# Copy the requirements.txt file into the container
COPY requirements.txt .

# Install the dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code into the container
COPY src/ .

# Set the command to run the application
CMD ["python", "main.py"]
```

### Requirements.txt Contents

The requirements.txt file includes the necessary Python libraries for this project. Make sure to update it with any additional dependencies you may need.

### Issues

If you encounter any issues while building or running the Docker container, please check the following:

- Ensure Docker is running.
- Verify that you are in the correct directory.
- Check for any typos in the commands.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
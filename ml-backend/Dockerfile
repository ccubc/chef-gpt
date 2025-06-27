# Use Python 3.12.7 base image
FROM python:3.12.7-slim

# Set working directory inside the container
WORKDIR /app

# Install system dependencies for things like numpy, image processing, etc.
RUN apt-get update && apt-get install -y \
    build-essential \
    libgl1-mesa-glx \
    libglib2.0-0 \
    && rm -rf /var/lib/apt/lists/*

# Copy Python files
COPY . .

# Install Python dependencies
RUN pip install --upgrade pip && pip install -r requirements.txt

# Set the port for uvicorn
EXPOSE 8000

# Command to run the FastAPI app
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]

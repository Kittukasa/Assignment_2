# Use the official Python image
FROM python:3.11-slim

RUN pip install flask

RUN apt-get update && apt-get install -y curl && apt-get clean 
# Set the working directory inside the container
WORKDIR /app

# Copy your Python script into the container
COPY app.py .

# Run the app when the container starts
CMD ["python", "-m", "flask", "run", "--host=0.0.0.0", "--port=8002"]

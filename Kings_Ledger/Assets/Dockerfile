# Use official Python image
FROM python:3.12-slim

WORKDIR /app

# Copy requirements
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy project files
COPY . .

# Render provides the PORT environment variable
ENV FLASK_APP=app.py
ENV FLASK_ENV=production

# IMPORTANT: bind to 0.0.0.0 and $PORT
CMD ["sh", "-c", "flask run --host=0.0.0.0 --port=${PORT:-5000}"]
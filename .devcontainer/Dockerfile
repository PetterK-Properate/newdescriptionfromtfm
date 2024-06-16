# Use the official Python image from the Docker Hub
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /workspace

# Install pipenv to manage dependencies
RUN pip install pipenv

# Copy the Pipfile and Pipfile.lock to the container
COPY Pipfile* ./

# Install the dependencies from the Pipfile
RUN pipenv install --deploy --ignore-pipfile

# Copy the entire project to the working directory in the container
COPY . /workspace

# Expose the Streamlit port
EXPOSE 8501

# Command to run the Streamlit app
CMD ["pipenv", "run", "streamlit", "run", "app.py"]

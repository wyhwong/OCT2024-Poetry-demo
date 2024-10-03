## Run Locally

```bash
# If you don't have poetry installed
# Caution: Poetry should be installed in a virtual environment
pip3 install poetry

# Install dependencies
poetry install

# Run timer
poetry run python3 -m timer_demo
```

## Run in Docker Container

```bash
# Build Docker image
docker build -t timer-demo:test .

# Run Docker container
docker run --rm -it timer-demo:test python3 app
```

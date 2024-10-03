# STAGE 1 - Export dependencies
FROM python:3.11-slim-buster AS base

# Convert poetry.lock to requirements.txt
RUN pip3 install poetry poetry-plugin-export
COPY ./pyproject.toml ./poetry.lock /
RUN poetry export \
    -f requirements.txt \
    -o requirements.txt \
    --without-hashes 

# STAGE 2 - Build main image
FROM python:3.11-slim-buster AS main

# Set working directory and freeze scripts
COPY --from=base /requirements.txt /tmp/requirements.txt
RUN python3 -m pip install --no-cache-dir -r /tmp/requirements.txt
COPY ./timer_demo /app

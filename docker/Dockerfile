######
# The Base Dockerfile used to work/debug/build/test cosv3-state-bucket CLI tool
######
FROM python:3.10

ARG POETRY_VIRTUALENVS_CREATE=false
ENV POETRY_VIRTUALENVS_CREATE=${POETRY_VIRTUALENVS_CREATE}

# Install poetry
RUN pip install poetry

WORKDIR /opt/code
# Copy the poetry specific files
COPY pyproject.toml pyproject.toml
COPY poetry.lock poetry.lock

# Install dependencies only.
# This line will run only if pyproject.toml or poetry.lock have changed.
# Otherwise, a cached build can safely skip this step.
RUN poetry install
# Copy the entire project
COPY . .

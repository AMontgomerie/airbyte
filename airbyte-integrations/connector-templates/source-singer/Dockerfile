FROM python:3.7-slim

# Bash is installed for more convenient debugging.
RUN apt-get update && apt-get install -y bash && apt-get install gcc && rm -rf /var/lib/apt/lists/*

WORKDIR /airbyte/integration_code
COPY source_{{snakeCase name}}_singer ./source_{{snakeCase name}}_singer
COPY main.py ./
COPY setup.py ./
RUN pip install .

ENTRYPOINT ["python", "/airbyte/integration_code/main.py"]

LABEL io.airbyte.version=0.1.0
LABEL io.airbyte.name=airbyte/source-{{dashCase name}}

FROM python:3.12.3-slim

RUN apt-get update \
    && apt-get install -y curl gnupg2 \
    && curl https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add - \
    && echo "deb http://apt.postgresql.org/pub/repos/apt/ bookworm-pgdg main" > /etc/apt/sources.list.d/pgdg.list \
    && apt-get update \
    && apt-get install -y postgresql-client-17 \
    && rm -rf /var/lib/apt/lists/*

COPY elt_script.py .

CMD ["python", "elt_script.py"]

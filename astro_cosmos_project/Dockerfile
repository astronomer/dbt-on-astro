FROM quay.io/astronomer/astro-runtime:11.7.0

# install dbt into a virtual environment
RUN python -m venv dbt_venv && source dbt_venv/bin/activate && \
    pip install --no-cache-dir dbt-databricks>=1.8.0 && pip install --no-cache-dir dbt-bigquery>=1.8.0 && pip install --no-cache-dir dbt-postgres>=1.8.0 && deactivate

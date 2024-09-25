FROM quay.io/astronomer/astro-runtime:11.7.0

# install dbt into a virtual environment
# here's a dockerfile change
RUN python -m venv dbt_venv_postgres && source dbt_venv_postgres/bin/activate && \
    pip install --no-cache-dir dbt-postgres>=1.8.0 && deactivate

RUN python -m venv dbt_venv_databricks && source dbt_venv_databricks/bin/activate && \
    pip install --no-cache-dir dbt-databricks>=1.8.0 && deactivate

RUN python -m venv dbt_venv_bigquery && source dbt_venv_bigquery/bin/activate && \
    pip install --no-cache-dir dbt-bigquery>=1.8.0 && deactivate

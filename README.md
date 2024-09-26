# dbt on Astro - Reference Implementation

This repository answers the following question: **How do I set up, run, and maintain dbt workflows for any-size teams on Astro and Airflow**?

![dbt on Astro graphic](https://www.astronomer.io/images/blog_dbt_b.jpg)

## Repository Walkthrough

This repository provides a comprehensive guide on setting up, running, and maintaining dbt workflows on Astro and Airflow. It includes detailed instructions and examples to help users understand the integration between dbt, Astro, and Airflow.

### Technology

1. [Astro](https://www.astronomer.io/docs/astro). Take Apache Airflow® to the next level by hosting it with Astro.
2. [Cosmos](https://github.com/astronomer/astronomer-cosmos). The best way to orchestrate dbt with Airflow.
3. [dbt Deploys on Astro](https://www.astronomer.io/docs/astro/deploy-dbt-project). Deploy dbt code directly to Astro, without changing your environment.
4. [Astronomer's Github Action Extension](https://github.com/marketplace/actions/deploy-apache-airflow-dags-to-astro). Set up CI/CD to your Astro deployment in just a few lines of code.

### Repository Contents

- **`astro_cosmos_project/`**: This directory contains a full [Astro project](https://www.astronomer.io/docs/astro/cli/develop-project) that defines the environment, metadata, and DAGs of your Astro deployment. For this project, we're using [Astronomer Cosmos](https://github.com/astronomer/astronomer-cosmos), the best way to orchestrate dbt with Airflow.

  - **`dags/`**: Three DAGs for rendering Astronomer Cosmos
  - **`dags/dbt`**: This directory shows an example of keeping your dbt code and DAG code **coupled together**. This is the best strategy for small teams with only one repo.

- **`dbt/`**: This directory contains dbt projects that live **outside of your Astro project directory.**. This directory can live in the same repository as your Astro project OR can live in a different repository entirely.

- **`.github/workflows/deploy-to-astro.yaml`**: This GitHub Actions workflow file automates the deployment of your Astro project to the Astronomer platform. It also independently deploys dbt projects from **`dbt/`** when code changes.

# Centrifuge Operator

[![Docker](https://img.shields.io/static/v1?label=shipped+with&message=Docker&color=287cf9)](https://www.docker.com/)
[![embrio.tech](https://img.shields.io/static/v1?label=by&message=EMBRIO.tech&color=24ae5f)](https://embrio.tech)
[![Centrifuge](https://img.shields.io/static/v1?label=for&message=Centrifuge&color=2762ff)](https://centrifuge.io/)

Centrifuge Operator is a GitHub repository that provides a Docker Compose setup to run all the required services for a pool operator to analyze their own pools. This setup includes the following services:

- `blender-influx`: A microservice that crawls data about assets from on-chain and off-chain sources.
- `blender-db`: A MongoDB database used to save the crawled data.
- `blender-outflux`: A querying and aggregation interface based on GraphQL.
- `centrifuge-pod`: A node for the Centrifuge POD (Private Off-Chain Data).

## Getting Started

To get started with Centrifuge Operator and set up the environment, follow these steps:

1. Clone the repo including the submodules with:
    ```
    git clone --recurse-submodules git@github.com:embrio-tech/centrifuge-operator.git
    ```

1. Copy the example environment file:
    ```
    cp .env.example .env
    ```

1. Set the required environment variables in the `.env` file according to your specific setup and configuration.

1. Start the services using Docker Compose:
    ```
    docker-compose up -d --build blender-db blender-influx blender-outflux
    ```

    This command will build the required Docker images (if needed) and start the specified services in detached mode.

1. To reset and delete the environment, use the following command:
    ```
    docker-compose down -v
    ```
    
    This will stop and remove all containers, networks, and volumes associated with the services.

## Additional Configuration

- You can modify the Docker Compose file (`docker-compose.yml`) to adjust the service configuration according to your needs. Refer to the Docker Compose documentation for more information on available options.

- Each individual service may have its own configuration files or settings that you can customize. Please refer to the respective service's documentation or source code for specific instructions.

## Contributing

Contributions to the Centrifuge Operator repository are welcome! If you encounter any issues, have suggestions, or would like to contribute improvements or new features, please open an issue or submit a pull request on GitHub.





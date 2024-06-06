# Dockerized Prometheus, Loki, Promtail, and Grafana Setup

This repository contains Docker configurations for setting up Prometheus, Loki, Promtail, and Grafana for log monitoring and visualization.

## Installation

To set up the monitoring stack, follow these steps:

1. **Install Docker:** If you haven't already installed Docker on your system, follow the instructions for your operating system from [Docker's official documentation](https://docs.docker.com/get-docker/).

2. **Clone Repository:**

    ```bash
    git clone <repository_url>
    ```

3. **Move YAML files:**

    Place all the YAML files provided in this repository into the same directory.

4. **Navigate to Directory:**

    ```bash
    cd <directory_where_yml_files_are_placed>
    ```

5. **Start Containers:**

    Run the following command to start all containers (Loki, Promtail, and Prometheus) using Docker Compose:

    ```bash
    docker-compose up -d
    ```

    This command will start the containers in detached mode.

6. **Start Grafana Server:**

    Start the Grafana server using:

    ```bash
    sudo systemctl start grafana-server
    ```

    Ensure Grafana is installed and configured properly on your system before starting.

7. **Access Grafana:**

    - Open your web browser and go to `http://localhost:3000` (default Grafana port).
    - Log in to Grafana (default credentials may be admin/admin, please change it on first login).
    - Navigate to "Data Sources" and add respective data sources for Prometheus and Loki.
    - Use LogQL queries to retrieve logs from Loki:
        - Refer to Loki's documentation for LogQL syntax: [Loki LogQL](https://grafana.com/docs/loki/latest/logql/)
        - Example queries can be found in Grafana's Explore section.

## Configuration

- **YAML Files:**
    - Ensure all YAML configuration files (docker-compose.yml, prometheus.yml, etc.) are in the same directory.
- **Grafana Data Source:**
    - Configure Prometheus and Loki data sources in Grafana to visualize metrics and logs.

## Notes

- Make sure Docker and Grafana are properly installed and configured on your system.
- Grafana default port is assumed to be 3000. If you've configured Grafana to use a different port, adjust the URL accordingly.

## Contributing

Contributions are welcome! If you find any issues or want to improve the setup, feel free to open an issue or create a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

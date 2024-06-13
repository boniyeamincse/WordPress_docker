# Users Guideline

This document provides instructions for accessing the services provided by the WordPress setup with Docker, Prometheus, and Grafana, as well as guidelines for setting up Grafana for monitoring.

## Access the Services

Once you have started the Docker containers, you can access the services using the following URLs:

- **WordPress**: `http://your-server-ip`
  - This URL will take you to the WordPress installation page where you can complete the setup by following the on-screen instructions.

- **Prometheus**: `http://your-server-ip:9090`
  - This URL will take you to the Prometheus interface where you can query and view metrics.

- **Grafana**: `http://your-server-ip:3000`
  - This URL will take you to the Grafana dashboard where you can set up data sources and import dashboards for monitoring.

## Grafana Setup

To set up Grafana for monitoring, follow these steps:

1. **Login to Grafana**:
   - Open your web browser and navigate to `http://your-server-ip:3000`.
   - Use the default credentials to log in:
     - Username: `admin`
     - Password: `admin`

2. **Change Default Password**:
   - Upon the first login, Grafana will prompt you to change the default password. Enter a new password and save it.

3. **Add Prometheus as a Data Source**:
   - Go to `Configuration` (the gear icon) -> `Data Sources`.
   - Click `Add data source`.
   - Select `Prometheus` from the list of data sources.
   - Set the URL to `http://prometheus:9090`.
   - Click `Save & Test` to verify the connection.

4. **Import Dashboards**:
   - Go to `Create` (the plus icon) -> `Import`.
   - You can either upload a JSON file of a dashboard or import it by ID from the Grafana.com dashboard repository.
   - Follow the on-screen instructions to complete the import.

## Notes

- Ensure your server has the following ports open:
  - Port `80` for WordPress.
  - Port `9090` for Prometheus.
  - Port `3000` for Grafana.

- You can modify the database credentials and other settings in the `docker-compose.yml` file located in the root of your project directory.

## License

This project is licensed under the MIT License. You can view the full license [here](LICENSE).


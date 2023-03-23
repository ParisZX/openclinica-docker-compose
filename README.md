# OpenClinica Docker Compose

This repository contains a `docker-compose.yml` file and an `init-db.sh` script to easily set up and run OpenClinica and its necessary PostgreSQL database using Docker Compose. The configuration is based on the [piegsaj/openclinica:oc-3.13](https://hub.docker.com/r/piegsaj/openclinica) Docker image.

## Prerequisites

- Docker and Docker Compose installed on your system
- Basic understanding of Docker and Docker Compose

## Quick Start

1. Clone this repository:

```bash
git clone https://github.com/your-username/openclinica-docker-compose.git
cd openclinica-docker-compose
```

2. Ensure the init-db.sh script is executable:
```bash
chmod +x init-db.sh
```

3. Run Docker Compose:
```bash
docker-compose up -d
```

4. Open a web browser and navigate to http://<ip.of.your.host>/OpenClinica

5. Log in with the default credentials:

Username: `root`
Password: `12345678`

## Customization
If you need to customize the OpenClinica or PostgreSQL configuration, you can edit the `docker-compose.yml` file and update the environment variables or other settings as needed.

Remember to adjust the passwords and other sensitive information according to your requirements.

## Data Persistence
This setup uses named volumes for data persistence. The data for the PostgreSQL database and OpenClinica application is stored in the following named volumes:

`ocdb-data`: PostgreSQL database data
`oc-data`: OpenClinica application data
Even if you stop and remove the containers, the data in these named volumes will be preserved. When you restart the containers, the data will be restored.

## License
This project is not affiliated with or endorsed by OpenClinica. It is a community-contributed solution to set up OpenClinica using Docker Compose, based on the [piegsaj/openclinica:oc-3.13](https://hub.docker.com/r/piegsaj/openclinica) Docker image. The OpenClinica Community Edition is free and open source, and is distributed under the [GNU LGPL license](https://choosealicense.com/licenses/lgpl-3.0/). This repository is provided "as is" without warranty of any kind.
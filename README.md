# PHP DevSuite

**PHP DevSuite** is an all-in-one **Docker-based development suite** for **Laravel, WordPress, Magento, and more**.  
It provides a robust, scalable, and easy-to-use local development environment with pre-configured services.

<p align="center">
  <img src="https://img.shields.io/badge/php-8.x-blue.svg?logo=php&longCache=true" alt="Supported PHP Versions" />
  <img src="https://img.shields.io/badge/nginx-1.x-green.svg?logo=nginx&longCache=true" alt="Supported Nginx Versions" />
  <a href="https://hub.docker.com/r/focela/php/" target="_blank"><img src="https://img.shields.io/docker/pulls/focela/php.svg?label=PHP%20Docker%20Pulls" alt="PHP Docker Pulls" /></a>
  <a href="https://hub.docker.com/r/focela/nginx/" target="_blank"><img src="https://img.shields.io/docker/pulls/focela/nginx.svg?label=Nginx%20Docker%20Pulls" alt="Nginx Docker Pulls" /></a>
  <a href="https://github.com/focela/php-devsuite/graphs/commit-activity" target="_blank"><img src="https://img.shields.io/badge/maintained%3F-yes-brightgreen.svg" alt="Maintained - Yes" /></a>
  <a href="https://opensource.org/licenses/MIT" target="_blank"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="MIT License" /></a>
</p>

## 📌 Table of Contents
- [🚀 Quick Start](#-quick-start)
- [🛠 Features](#-features)
- [📦 Services](#-services)
- [🔧 Setup](#-setup)
- [📂 Directory Structure](#-directory-structure)
- [⚙ Management](#-management)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)
- [💬 Support](#-support)

## 🚀 Quick Start

### Clone the repository
```bash
git clone git@github.com:focela/php-devsuite.git
cd php-devsuite
```

### Start the environment
```bash
./compose/bin/start
```

### Access your application
- Open **http://localhost** in your browser.

## 🛠 Features

- Pre-configured PHP & Nginx setup
- Supports Laravel, WordPress, Magento, and more
- Elasticsearch, OpenSearch, RabbitMQ support
- Customizable environment with Docker Compose
- Easy start, stop, and restart scripts
- Works seamlessly on Linux, macOS, and Windows (WSL2)

## 📦 Services

| Service       | Versions Available |
|--------------|-------------------|
| **PHP**       | 8.1, 8.2, 8.3, 8.4 |
| **Nginx**     | 1.18, 1.22, 1.24 |
| **Elasticsearch** | 7.16, 7.17, 8.4, 8.5, 8.7, 8.11, 8.13 |
| **OpenSearch** | 1.2, 2.5, 2.12 |
| **RabbitMQ**  | 3.8, 3.9, 3.11, 3.12, 3.13 |

## 🔧 Setup

### Install dependencies
Ensure you have **Docker** installed. If not, install it from [Docker Official Site](https://www.docker.com/).

### Run the project
```bash
./compose/bin/start
```

### Stop the environment
```bash
./compose/bin/stop
```

## 📂 Directory Structure

```
.
├── CODE_OF_CONDUCT.md   # Community guidelines
├── CONTRIBUTING.md      # Contribution guidelines
├── LICENSE              # MIT License
├── compose/             # Docker Compose configuration & scripts
│   ├── bin/             # Utility scripts
│   │   ├── bash
│   │   ├── cli
│   │   ├── restart
│   │   ├── setup-ssl
│   │   ├── start
│   │   └── stop
│   ├── compose.yaml     # Main Docker Compose configuration
│   ├── docker/
│   │   └── nginx/       # Nginx configurations
│   │       ├── nginx.conf
│   │       └── sites-enabled/
│   │           └── default.conf
│   └── src/             # Sample PHP application
│       └── index.php
└── images/              # Custom Docker images
    ├── php/             # PHP images
    ├── nginx/           # Nginx images
    ├── elasticsearch/   # Elasticsearch versions
    ├── opensearch/      # OpenSearch versions
    ├── rabbitmq/        # RabbitMQ versions
```

## ⚙ Management

### Restart all containers:
```bash
./compose/bin/restart
```

### Stop the environment:
```bash
./compose/bin/stop
```

### View logs:
```bash
docker-compose logs -f
```

## 🤝 Contributing

We welcome contributions! Please check:
- [CONTRIBUTING.md](CONTRIBUTING.md) for contribution guidelines.
- [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for community standards.

## 📄 License

PHP DevSuite is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for more details.

## 💬 Support

If you encounter any issues, please open an issue in the repository:  
[GitHub Issues](https://github.com/focela/php-devsuite/issues)

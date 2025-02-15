# Changelog

All notable changes to this project will be documented in this file.  
This project adheres to [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [1.0.0] - 2025-02-15
### Added
- **Initial release of PHP DevSuite** 🎉
- Pre-configured **Docker-based development suite** for:
    - **Laravel**, **WordPress**, **Magento**, and more.
- **Docker Compose setup** with support for:
    - **PHP**, **Nginx**, **MySQL**, **PostgreSQL**, **Elasticsearch**, **OpenSearch**, **RabbitMQ**.
- **Pre-built Docker images** for:
    - **PHP**: `8.1`, `8.2`, `8.3`, `8.4`
    - **Nginx**: `1.18`, `1.22`, `1.24`
    - **Elasticsearch**: `7.16`, `7.17`, `8.4`, `8.5`, `8.7`, `8.11`, `8.13`
    - **OpenSearch**: `1.2`, `2.5`, `2.12`
    - **RabbitMQ**: `3.8`, `3.9`, `3.11`, `3.12`, `3.13`
- **Utility scripts** for streamlined management:
    - `compose/bin/start` → Start all containers.
    - `compose/bin/stop` → Stop all containers.
    - `compose/bin/restart` → Restart all services.
    - `compose/bin/setup-ssl` → Generate and install SSL certificates.
- **Configuration & Security Features**:
    - `.env.example` included for easy environment variable management.
    - Pre-configured **Blackfire**, **Xdebug**, and **PHP-FPM** settings.
    - **Custom Nginx configurations** for optimized performance.

### Changed
- N/A (first release)

### Fixed
- N/A (first release)

### Removed
- N/A (first release)

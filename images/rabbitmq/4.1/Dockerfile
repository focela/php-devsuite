# RabbitMQ with Management Plugin
# Maintainer: Focela Labs <opensource@focela.com>
# Purpose: Provides RabbitMQ message broker with management interface and custom configuration

# ===================================================================
# BASE IMAGE
# ===================================================================

# Use official RabbitMQ image with management plugin on Alpine Linux
# Version: 4.1 - Update this value when upgrading RabbitMQ
# Alpine variant provides a smaller image size while maintaining functionality
FROM rabbitmq:4.1-management-alpine

# ===================================================================
# METADATA
# ===================================================================

# Image maintainer information
LABEL maintainer="Focela Labs <opensource@focela.com>"
LABEL org.opencontainers.image.description="RabbitMQ message broker with management interface"
LABEL org.opencontainers.image.version="4.1"

# ===================================================================
# CONFIGURATION
# ===================================================================

# Copy custom RabbitMQ configuration file
# This file should contain your production-specific settings such as:
# - Memory limits and disk thresholds
# - Network configuration and TLS settings
# - Queue and exchange policies
# - Authentication and authorization settings
COPY conf/rabbitmq.conf /etc/rabbitmq/rabbitmq.conf

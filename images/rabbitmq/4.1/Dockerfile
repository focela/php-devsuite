#-----------------------------------------------------------------------------
# RABBITMQ WITH CUSTOM CONFIGURATION
#-----------------------------------------------------------------------------
# RabbitMQ message broker with management UI and custom memory settings

#-----------------------------------------------------------------------------
# BASE IMAGE & BUILD ARGUMENTS
#-----------------------------------------------------------------------------
# Configurable RabbitMQ version with management UI on Alpine Linux
# Alpine variant provides smaller image size while maintaining functionality
ARG RABBITMQ_VERSION=4.1
FROM rabbitmq:${RABBITMQ_VERSION}-management-alpine

#-----------------------------------------------------------------------------
# METADATA
#-----------------------------------------------------------------------------
LABEL maintainer="Focela Labs <opensource@focela.com>" \
      description="RabbitMQ with management UI and custom memory configuration"

#-----------------------------------------------------------------------------
# CONFIGURATION FILES
#-----------------------------------------------------------------------------
# Copy custom RabbitMQ configuration with memory watermark settings
# Sets vm_memory_high_watermark.absolute = 1GB to prevent memory overflow
COPY conf/rabbitmq.conf /etc/rabbitmq/rabbitmq.conf

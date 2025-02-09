# Use RabbitMQ 3.11 with management plugin on Alpine Linux
FROM rabbitmq:3.11-management-alpine

# Maintainer information
LABEL maintainer="Focela Technologies <opensource@focela.com>"

# Copy configuration files
COPY ../shared-configs/rabbitmq.conf /etc/rabbitmq/rabbitmq.conf

# Set appropriate permissions
RUN chown rabbitmq:rabbitmq /etc/rabbitmq/rabbitmq.conf \
    && chmod 640 /etc/rabbitmq/rabbitmq.conf

# Define RabbitMQ working directory
WORKDIR /var/lib/rabbitmq

# Expose RabbitMQ ports for communication
EXPOSE 5672 15672

# Run RabbitMQ as a non-root user for better security
USER rabbitmq

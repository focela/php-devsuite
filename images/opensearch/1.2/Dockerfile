# Use OpenSearch 1.2.4 as the base image
FROM opensearchproject/opensearch:1.2.4

# Maintainer information
LABEL maintainer="Focela Technologies <opensource@focela.com>"

# Switch to root user for necessary modifications
USER root

# Install required OpenSearch plugins
RUN /usr/share/opensearch/bin/opensearch-plugin install --batch \
    analysis-icu \
    analysis-phonetic

# Set appropriate permissions for OpenSearch directories
RUN chmod -R 755 /usr/share/opensearch

# Switch back to opensearch user
USER opensearch

# Define working directory
WORKDIR /usr/share/opensearch

# Expose OpenSearch ports for communication
EXPOSE 9200 9600

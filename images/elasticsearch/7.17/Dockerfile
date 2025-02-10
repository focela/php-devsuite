# Use Elasticsearch 7.17.27 as the base image
FROM elasticsearch:7.17.27

# Maintainer information
LABEL maintainer="Focela Technologies <opensource@focela.com>"

# Switch to root user for necessary modifications
USER root

# Install required Elasticsearch plugins
RUN /usr/share/elasticsearch/bin/elasticsearch-plugin install \
    analysis-icu \
    analysis-phonetic

# Set correct permissions for Elasticsearch directories
RUN chmod -R 755 /usr/share/elasticsearch

# Switch back to elasticsearch user
USER elasticsearch

# Define working directory
WORKDIR /usr/share/elasticsearch

# Expose Elasticsearch ports
EXPOSE 9200 9300

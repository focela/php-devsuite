# Use Elasticsearch 8.7.1 as the base image
FROM elasticsearch:8.7.1

# Maintainer information
LABEL maintainer="Focela Technologies <opensource@focela.com>"

# Install required Elasticsearch plugins
RUN /usr/share/elasticsearch/bin/elasticsearch-plugin install \
    analysis-icu \
    analysis-phonetic

# Set correct permissions for Elasticsearch directories
RUN chown -R elasticsearch:elasticsearch /usr/share/elasticsearch \
    && chmod -R 755 /usr/share/elasticsearch

# Define working directory
WORKDIR /usr/share/elasticsearch

# Expose Elasticsearch ports
EXPOSE 9200 9300

# Set user to elasticsearch for security
USER elasticsearch

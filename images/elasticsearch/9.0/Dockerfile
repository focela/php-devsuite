#-----------------------------------------------------------------------------
# ELASTICSEARCH WITH ANALYSIS PLUGINS
#-----------------------------------------------------------------------------
# Elasticsearch with ICU and phonetic analysis plugins for enhanced text processing

#-----------------------------------------------------------------------------
# BASE IMAGE & BUILD ARGUMENTS
#-----------------------------------------------------------------------------
# Configurable Elasticsearch version for reproducibility
ARG ELASTICSEARCH_VERSION=9.0.2
FROM elasticsearch:${ELASTICSEARCH_VERSION}

#-----------------------------------------------------------------------------
# METADATA
#-----------------------------------------------------------------------------
LABEL maintainer="Focela Labs <opensource@focela.com>" \
      description="Elasticsearch with ICU and phonetic analysis plugins"

#-----------------------------------------------------------------------------
# PLUGIN INSTALLATION
#-----------------------------------------------------------------------------
# Install analysis plugins:
# - analysis-icu: Unicode text processing and normalization
# - analysis-phonetic: Phonetic matching (Soundex, Metaphone, etc.)
RUN /usr/share/elasticsearch/bin/elasticsearch-plugin install \
    analysis-icu \
    analysis-phonetic

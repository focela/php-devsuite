#-----------------------------------------------------------------------------
# BASE IMAGE & BUILD ARGUMENTS
#-----------------------------------------------------------------------------
# Official Elasticsearch base image with configurable version
ARG ELASTICSEARCH_VERSION=9.0.2
FROM elasticsearch:${ELASTICSEARCH_VERSION}

# Maintainer and source information
LABEL maintainer="Focela Labs (https://www.focela.com)"

# Build-time arguments for plugin configuration
ARG ANALYSIS_PLUGINS="analysis-icu analysis-phonetic"

#-----------------------------------------------------------------------------
# PLUGIN INSTALLATION
#-----------------------------------------------------------------------------
# Install Elasticsearch analysis plugins for enhanced text processing
# - analysis-icu: Unicode text analysis (normalization, collation, etc.)
# - analysis-phonetic: Phonetic matching algorithms (Soundex, Metaphone, etc.)
RUN /usr/share/elasticsearch/bin/elasticsearch-plugin install \
    ${ANALYSIS_PLUGINS}

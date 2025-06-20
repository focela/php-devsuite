#-----------------------------------------------------------------------------
# OPENSEARCH WITH ANALYSIS PLUGINS
#-----------------------------------------------------------------------------
# OpenSearch with ICU and phonetic analysis plugins for enhanced text processing

#-----------------------------------------------------------------------------
# BASE IMAGE & BUILD ARGUMENTS
#-----------------------------------------------------------------------------
# Configurable OpenSearch version for reproducibility
ARG OPENSEARCH_VERSION=3.0.0
FROM opensearchproject/opensearch:${OPENSEARCH_VERSION}

#-----------------------------------------------------------------------------
# METADATA
#-----------------------------------------------------------------------------
LABEL maintainer="Focela Labs <opensource@focela.com>" \
      description="OpenSearch with ICU and phonetic analysis plugins"

#-----------------------------------------------------------------------------
# PLUGIN INSTALLATION
#-----------------------------------------------------------------------------
# Install analysis plugins:
# - analysis-icu: Unicode text processing and normalization
# - analysis-phonetic: Phonetic matching (Soundex, Metaphone, etc.)
# Using --batch flag to skip interactive prompts during automated builds
RUN /usr/share/opensearch/bin/opensearch-plugin install --batch \
    analysis-icu \
    analysis-phonetic

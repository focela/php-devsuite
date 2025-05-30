# Elasticsearch with Analysis Plugins
# Maintainer: Focela Labs <opensource@focela.com>
# Purpose: Provides Elasticsearch with ICU and Phonetic analysis plugins for enhanced text processing

# ===================================================================
# BASE IMAGE
# ===================================================================

# Use official Elasticsearch image as base
# Version: 9.0.1 - Update this value when upgrading Elasticsearch
FROM elasticsearch:9.0.1

# ===================================================================
# METADATA
# ===================================================================

# Image maintainer information
LABEL maintainer="Focela Labs <opensource@focela.com>"
LABEL org.opencontainers.image.description="Elasticsearch with ICU and Phonetic analysis plugins"
LABEL org.opencontainers.image.version="9.0.1"

# ===================================================================
# PLUGIN INSTALLATION
# ===================================================================

# Install Elasticsearch analysis plugins
# These plugins enhance text analysis capabilities:
# - analysis-icu: Provides Unicode normalization and text analysis for international content
# - analysis-phonetic: Enables phonetic matching for improved search relevance
RUN /usr/share/elasticsearch/bin/elasticsearch-plugin install \
    analysis-icu \
    analysis-phonetic

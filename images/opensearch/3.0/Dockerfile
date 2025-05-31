# OpenSearch with Analysis Plugins
# Maintainer: Focela Labs <opensource@focela.com>
# Purpose: Provides OpenSearch with ICU and Phonetic analysis plugins for enhanced text processing

# ===================================================================
# BASE IMAGE
# ===================================================================

# Use official OpenSearch image as base
# Version: 3.0.0 - Update this value when upgrading OpenSearch
FROM opensearchproject/opensearch:3.0.0

# ===================================================================
# METADATA
# ===================================================================

# Image maintainer information
LABEL maintainer="Focela Labs <opensource@focela.com>"
LABEL org.opencontainers.image.description="OpenSearch with ICU and Phonetic analysis plugins"
LABEL org.opencontainers.image.version="3.0.0"

# ===================================================================
# PLUGIN INSTALLATION
# ===================================================================

# Install OpenSearch analysis plugins for enhanced text processing
# - analysis-icu: Provides Unicode normalization and text analysis for international content
#   Enables proper handling of non-ASCII characters, text folding, and collation
# - analysis-phonetic: Enables phonetic matching for improved search relevance
#   Supports algorithms like Metaphone, Double Metaphone, Soundex, and more
# 
# The --batch flag runs plugin installation in non-interactive mode
RUN /usr/share/opensearch/bin/opensearch-plugin install --batch \
    analysis-icu \
    analysis-phonetic

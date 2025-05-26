#----------------------------------------------------------------------
# Elasticsearch with Analysis Plugins Docker Image
#
# Purpose: Creates an Elasticsearch container image enhanced with 
# additional text analysis plugins for internationalization and 
# phonetic matching capabilities.
#
# This Dockerfile extends the official Elasticsearch base image by
# installing critical analysis plugins that enable:
# - International text processing (Unicode normalization, case folding)
# - Phonetic matching for fuzzy search (sound-alike words)
#
# Maintained by: Focela Labs <opensource@focela.com>
# Base Version: Elasticsearch 9.0.1
#----------------------------------------------------------------------

#----------------------------------------------------------------------
# BASE IMAGE CONFIGURATION
#----------------------------------------------------------------------
# Use the official Elasticsearch image as the foundation
# Version: 9.0.1 (LTS - Long Term Support)
# 
# Note: When updating the base image version, ensure compatibility
# with the analysis plugins. Plugin versions must match the 
# Elasticsearch version exactly.
FROM elasticsearch:9.0.1

#----------------------------------------------------------------------
# IMAGE METADATA
#----------------------------------------------------------------------
# Maintainer information for support, issue tracking, and updates
# This label helps identify who to contact for image-related issues
LABEL maintainer="Focela Labs <opensource@focela.com>"

#----------------------------------------------------------------------
# ELASTICSEARCH PLUGIN INSTALLATION
#----------------------------------------------------------------------
# Install essential analysis plugins to enhance Elasticsearch's
# text processing capabilities beyond the default analyzers.
#
# Plugins being installed:
# 1. analysis-icu: Provides ICU (International Components for Unicode)
#    integration for proper handling of international text including:
#    - Unicode normalization and case folding
#    - Collation for language-specific sorting
#    - Boundary analysis for word segmentation
#
# 2. analysis-phonetic: Enables phonetic analysis for matching words
#    that sound similar but are spelled differently, supporting:
#    - Soundex algorithm
#    - Metaphone and Double Metaphone
#    - Beider-Morse phonetic matching
#    - Caverphone algorithm
#
# Note: The elasticsearch-plugin command automatically:
# - Downloads plugins from the official Elastic repository
# - Verifies plugin compatibility with the ES version
# - Installs and configures plugins without manual intervention
RUN /usr/share/elasticsearch/bin/elasticsearch-plugin install \
    analysis-icu \
    analysis-phonetic

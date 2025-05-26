#----------------------------------------------------------------------
# OpenSearch with Analysis Plugins Docker Image
#
# Purpose: Creates an OpenSearch container image enhanced with 
# additional text analysis plugins for internationalization and 
# phonetic matching capabilities.
#
# OpenSearch is an open-source search and analytics engine derived
# from Elasticsearch 7.10.2, providing a community-driven alternative
# with enterprise features.
#
# This Dockerfile extends the official OpenSearch base image by
# installing critical analysis plugins that enable:
# - International text processing (Unicode normalization, case folding)
# - Phonetic matching for fuzzy search (sound-alike words)
#
# Maintained by: Focela Labs <opensource@focela.com>
# Base Version: OpenSearch 3.0.0
#----------------------------------------------------------------------

#----------------------------------------------------------------------
# BASE IMAGE CONFIGURATION
#----------------------------------------------------------------------
# Use the official OpenSearch image as the foundation
# Version: 3.0.0 (Major release with enhanced security features)
# 
# Note: When updating the base image version, ensure compatibility
# with the analysis plugins. Plugin versions must match the 
# OpenSearch version exactly.
#
# OpenSearch 3.0.0 includes:
# - Enhanced security plugin enabled by default
# - Improved performance for large-scale deployments
# - Better resource management and monitoring
FROM opensearchproject/opensearch:3.0.0

#----------------------------------------------------------------------
# IMAGE METADATA
#----------------------------------------------------------------------
# Maintainer information for support, issue tracking, and updates
# This label helps identify who to contact for image-related issues
LABEL maintainer="Focela Labs <opensource@focela.com>"

#----------------------------------------------------------------------
# OPENSEARCH PLUGIN INSTALLATION
#----------------------------------------------------------------------
# Install essential analysis plugins to enhance OpenSearch's
# text processing capabilities beyond the default analyzers.
#
# Plugins being installed:
# 1. analysis-icu: Provides ICU (International Components for Unicode)
#    integration for proper handling of international text including:
#    - Unicode normalization and case folding
#    - Collation for language-specific sorting
#    - Boundary analysis for word segmentation
#    - Support for over 60 languages
#
# 2. analysis-phonetic: Enables phonetic analysis for matching words
#    that sound similar but are spelled differently, supporting:
#    - Soundex algorithm (optimized for English names)
#    - Metaphone and Double Metaphone (improved accuracy)
#    - Beider-Morse phonetic matching (multilingual support)
#    - Caverphone algorithm (optimized for name matching)
#    - Cologne phonetic (optimized for German)
#
# Note: The --batch flag is critical for automated builds as it:
# - Accepts all plugin permissions without prompting
# - Enables non-interactive installation in CI/CD pipelines
# - Prevents build failures due to interactive prompts
#
# The opensearch-plugin command automatically:
# - Downloads plugins from the official OpenSearch repository
# - Verifies plugin signatures and compatibility
# - Installs and configures plugins without manual intervention
RUN /usr/share/opensearch/bin/opensearch-plugin install --batch \
    analysis-icu \
    analysis-phonetic

#----------------------------------------------------------------------
# SECURITY CONSIDERATIONS
#----------------------------------------------------------------------
# OpenSearch 3.0.0 includes security features enabled by default:
# - TLS/SSL encryption for node-to-node communication
# - Authentication and authorization via security plugin
# - Audit logging capabilities
#
# To run in development without security (NOT for production):
# Add environment variable: DISABLE_SECURITY_PLUGIN=true
#
# For production, configure security certificates and credentials
# according to your organization's security requirements.
#----------------------------------------------------------------------

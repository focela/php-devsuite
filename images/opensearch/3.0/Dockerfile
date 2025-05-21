FROM opensearchproject/opensearch:3.0.0

LABEL maintainer="Focela Labs (https://www.focela.com)"
LABEL org.opencontainers.image.source="https://github.com/focela/php-devsuite/"
LABEL org.opencontainers.image.description="OpenSearch 3.0.0 with ICU and Phonetic analysis plugins"

RUN /usr/share/opensearch/bin/opensearch-plugin install --batch \
  analysis-icu \
  analysis-phonetic
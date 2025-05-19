FROM elasticsearch:9.0.1

LABEL maintainer="Focela Labs (https://www.focela.com)"
LABEL org.opencontainers.image.source="https://github.com/focela/php-devsuite/"
LABEL org.opencontainers.image.description="Elasticsearch 9.0.1 with ICU and Phonetic analysis plugins"

RUN /usr/share/elasticsearch/bin/elasticsearch-plugin install \
  analysis-icu \
  analysis-phonetic

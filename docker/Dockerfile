FROM owncloud/server:10.0.7
MAINTAINER elastos.org <devops@elastos.org>

ARG VERSION
ARG BUILD_DATE
ARG VCS_REF

ARG ELA_OC_AGENT_DEB

RUN curl -sLo ela_oc_agent.deb ${ELA_OC_AGENT_DEB} && \
  dpkg -i ela_oc_agent.deb && \
  rm -f ela_oc_agent.deb && \
  cp /etc/elaoc/elaoc-agent.conf /etc/elaoc/elaoc-agent.conf.org

COPY rootfs /

LABEL \
  org.label-schema.version=$VERSION \
  org.label-schema.build-date=$BUILD_DATE \
  org.label-schema.vcs-ref=$VCS_REF \
  org.label-schema.vcs-url="https://github.com/elastos/Elastos.DittoBox.Server.git" \
  org.label-schema.name="DittoBox Server" \
  org.label-schema.vendor="elastos.org" \
  org.label-schema.schema-version="1.0"

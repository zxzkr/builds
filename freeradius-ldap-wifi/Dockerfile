#FROM freeradius/freeradius-server:latest-3.2-alpine
FROM freeradius/freeradius-server:latest

COPY ldap /etc/raddb/mods-available/ldap

COPY init /
RUN chmod +x /init

#EXPOSE 1812/udp
#EXPOSE 1813/udp

ENV TINI_ARCH "amd64"
ENV TINI_VER "v0.19.0"
#RUN curl -sL https://github.com/krallin/tini/releases/download/${TINI_VER}/tini-${TINI_ARCH} -o /tini && chmod +x /tini
ADD https://github.com/krallin/tini/releases/download/${TINI_VER}/tini-${TINI_ARCH} /tini
RUN chmod +x /tini
ENTRYPOINT ["/init"]

#FROM freeradius/freeradius-server:latest-3.2-alpine
FROM freeradius/freeradius-server:latest

COPY ./mods-available/ldap /etc/raddb/mods-available/
COPY ./mods-available/eap /etc/raddb/mods-available/
COPY ./sites-available/default /etc/freeradius/sites-available/
COPY ./sites-available/inner-tunnel /etc/freeradius/sites-available/



COPY init /
RUN chmod +x /init

#EXPOSE 1812/udp
#EXPOSE 1813/udp

ENV TINI_ARCH amd64
ENV TINI_VER v0.19.0
RUN curl -sL https://github.com/krallin/tini/releases/download/${TINI_VER}/tini-${ARCH} -o /tini && chmod +x /tini
ENTRYPOINT ["/init"]

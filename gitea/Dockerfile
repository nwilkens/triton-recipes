FROM gitea/gitea:1.22-rootless

ENV GITEA__database__DB_TYPE=postgres
ENV GITEA__server__HTTP_PORT=3000
ENV USER=git
ENV GITEA_CUSTOM=/var/lib/gitea/custom

EXPOSE 3000 22

VOLUME ["/var/lib/gitea", "/etc/gitea"]

ENTRYPOINT ["/usr/bin/entrypoint"]
CMD ["/usr/local/bin/gitea", "web", "--port", "3000"]

FROM n8nio/n8n:latest

ENV DB_TYPE=postgresdb
ENV N8N_PORT=5678
ENV NODE_ENV=production

EXPOSE 5678

VOLUME ["/home/node/.n8n"]

CMD ["n8n", "start"]

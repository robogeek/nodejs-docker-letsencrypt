FROM node:9.5-slim

ENV PORT="3000"
ENV DEBUG="app:*"

RUN apt-get update -y \
    && apt-get -y install curl python build-essential git ca-certificates 

RUN mkdir -p /app /app/bin /app/routes /app/views /app/public

COPY bin/ /app/bin/
COPY public/ /app/public/
COPY routes/ /app/routes/
COPY views/ /app/views/
COPY app.js package.json /app/

WORKDIR /app
RUN npm install --unsafe-perm

EXPOSE 3000 
CMD /app/bin/www

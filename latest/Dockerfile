FROM node:10.16-alpine

COPY . /tmp/

RUN mkdir -m 755 /app

WORKDIR /app

CMD sh -c " \
      if [ ! -e /app/.babelrc ]; then \
        cp /tmp/.babelrc /app/.babelrc; \
      fi \
      && if [ ! -e /app/package.json ]; then \
        cp /tmp/package.json /app/; \
      fi \
      && if [ ! -e /app/webpack.config.js ]; then \
        cp /tmp/webpack.config.js /app/; \
      fi \
      && yarn install --no-progress \
      && yarn run webpack \
    "

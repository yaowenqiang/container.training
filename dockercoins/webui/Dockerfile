FROM node:4-slim
RUN npm install -g cnpm --registry=https://registry.npm.taobao.org
RUN alias cnpm="npm --registry=https://registry.npm.taobao.org \
--cache=$HOME/.npm/.cache/cnpm \
--disturl=https://npm.taobao.org/dist \
--userconfig=$HOME/.cnpmrc"
RUN cnpm install express
RUN cnpm install redis
COPY files/ /files/
COPY webui.js /
CMD ["node", "webui.js"]
EXPOSE 80

FROM node:14.21.3-alpine3.17
EXPOSE 8080
#instaed of giving access to root user, creating cartgroup & adding cart user to cart group for security purpose
RUN addgroup -S cart && adduser -S cart cart
# immediately i can't user car user.nned to change ownership from root to cart user for /opt/server. After that user cart user
WORKDIR /opt/server
RUN chown -R cart:cart /opt/server
USER cart
COPY package.json .
COPY server.js .
RUN npm install
CMD ["node", "server.js"]
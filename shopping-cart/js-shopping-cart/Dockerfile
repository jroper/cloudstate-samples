FROM node:8.15
# Copy and install deps. This is done as a separate step as an optimization, so changes to the programs files
# don't require the npm install to be redone
RUN mkdir -p /opt/js-shopping-cart
COPY package.json /opt/js-shopping-cart/
WORKDIR /opt/js-shopping-cart
RUN npm install
# Now copy the entire app
COPY . /opt/js-shopping-cart
RUN npm run prestart
# run
EXPOSE 8080
CMD ["npm", "run", "start-no-prestart"]

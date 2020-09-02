FROM node:alpine 

WORKDIR '/app'

#copy files needed (package.json)
COPY ./package.json ./

#Install dependencies
RUN npm install
COPY ./ ./
#Default Command
CMD ["npm", "run", "start"]
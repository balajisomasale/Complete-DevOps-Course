Creating a Dockerfile to run the TODO App along with Mongo DB:

```
FROM node:21.7.1

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install

COPY . .
#CMD is also similar to RUN but RUN will stop after running task
CMD ["node","server"]

```

To run the Dockerfile: `docker build -t mern-backend .`

![image](https://github.com/balajisomasale/Complete-DevOps-Course/assets/35003840/bbd8f5ca-d3a1-4c10-99f3-f8852e9dfe7f)

For the frontend: ( These are as per the Git repo so that we can RUN the Todo App created by dev)

Dockerfile: 

![image](https://github.com/balajisomasale/Complete-DevOps-Course/assets/35003840/422cca3b-4fde-4ca9-8441-833995f27043)

After running both Dockerfiles for front and backend; docker images are built:

![image](https://github.com/balajisomasale/Complete-DevOps-Course/assets/35003840/fac82bc9-5dcb-466a-b8ac-11b52aa7bdfe)



Deploying MERN TODO App using Docker:

Mern Todo App: https://github.com/alokyadav1/mern-todo-app

1) we need to install mongo db using docker: docker pull mongo

$ docker run -d --network some-network --name some-mongo \
	-e MONGO_INITDB_ROOT_USERNAME=mongoadmin \
	-e MONGO_INITDB_ROOT_PASSWORD=secret \
	mongo

Edit .env as per git repository:

![image](https://github.com/balajisomasale/Complete-DevOps-Course/assets/35003840/195da511-e702-4606-ab64-1e480c10864c)

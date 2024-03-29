
Deploying MERN TODO App using Docker:

Mern Todo App: https://github.com/alokyadav1/mern-todo-app

Edit .env as per git repository:

![image](https://github.com/balajisomasale/Complete-DevOps-Course/assets/35003840/195da511-e702-4606-ab64-1e480c10864c)

1) we need to install mongo db using docker: docker pull mongo

$ docker run -d -p 27017:27017 --network some-network --name some-mongo \
	-e MONGO_INITDB_ROOT_USERNAME=mongoadmin \
	-e MONGO_INITDB_ROOT_PASSWORD=secret \
	mongo

Here, we need to specify mongo db port, username and its password so that it can be accessed to authenticate.

For Mongo DB, we need `Mongo db compass` which is same like postman and can be accessed using UI

![image](https://github.com/balajisomasale/Complete-DevOps-Course/assets/35003840/c46297dc-9bf5-46ce-a73c-bce4200645fa)

Pass the username/pwd details in authenticate tab and then connect 
![image](https://github.com/balajisomasale/Complete-DevOps-Course/assets/35003840/829bde4e-dbe8-4e6c-b21d-07d08b84c335)

Once its connected, we can see the default databases:

![image](https://github.com/balajisomasale/Complete-DevOps-Course/assets/35003840/9f09fae5-5eca-46a8-ab26-ab803c692b53)

Replace the `.env` file with latest mongo db uri: 

![image](https://github.com/balajisomasale/Complete-DevOps-Course/assets/35003840/f79c99dd-6d41-485e-abe2-2cbdfae28886)

Now, we need to install the dependencies:

`npm install` and run the backend server using `node server`

![image](https://github.com/balajisomasale/Complete-DevOps-Course/assets/35003840/84f2fdb2-4576-481a-bb69-5e5425a1ee82)

- Then Register from UI as a user and login; once successful
- check the Mongo DB:

	![image](https://github.com/balajisomasale/Complete-DevOps-Course/assets/35003840/735d1cf8-1812-48ab-9474-ce17215ec9c3)

- Now, Add a task and check in the DB:
	![image](https://github.com/balajisomasale/Complete-DevOps-Course/assets/35003840/bff8ab6e-ee3f-4430-9a20-c7183b67097e)

 	![image](https://github.com/balajisomasale/Complete-DevOps-Course/assets/35003840/9587a01b-bb1d-4574-be1e-93d1fca01c1e)

Creating a different mongo db server and then the docker container in that:

![image](https://github.com/balajisomasale/Complete-DevOps-Course/assets/35003840/5807a44f-5b52-4f86-bdb9-5232a12c25f4)


```

$ docker run -d -p 27018:27017 --network some-network --name some-mongo \
	-e MONGO_INITDB_ROOT_USERNAME=mongoadmin \
	-e MONGO_INITDB_ROOT_PASSWORD=secret \
	mongo
```
the first part with port : `27018` is the port for local host 

we can verify same using mongo db compass to check if the DB is created or not:

![image](https://github.com/balajisomasale/Complete-DevOps-Course/assets/35003840/b34542fd-c2c1-4786-b4f1-440feeb33e73)


In this way, we can create multiple mongo db databases by just using docker commands like `docker run` along with username,pwds and ports based on scenario. 
- similarly, we will create a `DOCKERFILE` that executes all the tasks that helps us to create a docker container, run the TODO App along with Mongo DB.



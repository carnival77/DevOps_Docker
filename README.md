# DevOps_Docker
Implemented Web Poll service employing Docker in Epitech.

The application you are working on during this project is a simple poll web application. Poll is a Python Flask
web application that gathers the votes to push them into a Redis queue. The Java Worker consumes the
votes stored in the Redis queue, then pushes it into a PostgreSQL database. Finally, the Node.js Result web
application fetches the votes from the DB and displays the result.

structure : 
![DevOps_structure](https://user-images.githubusercontent.com/52997401/86203711-9fe57d00-bba0-11ea-99a5-8e1a9546814f.png)


Result screen : 
![DevOps_result](https://user-images.githubusercontent.com/52997401/86203389-d79ff500-bb9f-11ea-8962-a5c42e433790.png)

Your docker-compose file should contain:
5 services:

poll: build your poll image and redirect port 5000 of the host to the port 80 of the image.

redis: use an existing image of redis and open port 6379

worker: build your worker image.

db: representing the database that will be used by the apps. You must use an existing image of postgres.

result:build your result image and redirect port 5001 of the host to the port 80 of the image.

3 networks:

poll-tier to allow poll to communicate with redis

result-tier to allow result to communicate with db

back-tier to allow worker to communicate with redis and db

1 volume:

db-data will make the database data persistent, if the container dies.

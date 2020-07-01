# DevOps_Kubernetes
Implemented Web Poll service employing Kubernetes in Epitech.

The application you are working on during this project is a simple poll web application. Poll is a Python Flask
web application that gathers the votes to push them into a Redis queue. The Java Worker consumes the
votes stored in the Redis queue, then pushes it into a PostgreSQL database. Finally, the Node.js Result web
application fetches the votes from the DB and displays the result.

structure : 
![DevOps_structure](https://user-images.githubusercontent.com/52997401/86203711-9fe57d00-bba0-11ea-99a5-8e1a9546814f.png)


Result screen : 
![DevOps_result](https://user-images.githubusercontent.com/52997401/86203389-d79ff500-bb9f-11ea-8962-a5c42e433790.png)

required files : 
1 load balancer, 2 databases and 3 services, two of which will be routed using Traefik.

3 services :
poll
result
worker

2 databses : 
redis
postgres

1 load balancer : 
traefik

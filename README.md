# AspnetMicroservices
AspnetMicroservices
#Chap 2
## 006 Setup Mongo Docker Database for Catalog.API Microservices
	docker pull mongo
	docker run -d -p 27017:27017 --name shopping-mongo mongo
	docker logs -f shopping-mongo
	docker exec -it shopping-mongo /bin/bash
	mongo
	
	show dbs
	use CatalogDb
	db.createCollection('Products')
	db.Products.insertMany([{ Name: "Asus Laptop", Category: "Computers", Summary: "Summary", Description: "Description", ImageFile: "ImageFile", Price: 54.93 },{ Name: "HP Laptop", Category: "Computers", Summary: "Summary", Description: "Description", ImageFile: "ImageFile", Price: 88.93 }])
	db.Products.find({}).pretty()
	db.Products.remove({})
	show colletions
	
	

docker-compose -f .\docker-compose.yml -f .\docker-compose.override.yml down
docker-compose -f .\docker-compose.yml -f .\docker-compose.override.yml up -d

docker stop $(docker ps -aq)
docker rm $(docker rm -aq)
docker rmi $(docker rmi -q)
docker system prune

## 019 Mongo GUI Options for MongoDb Docker Image
docker run -d -p 3000:3000 mongoclient/mongoclient
# Chap 3
## 004 Setup Redis Cache Docker Database for Basket.API Microservices
docker pull redis
docker images
docker run -d -p 6379:6379 --name aspnetrun-redis redis
docker ps
docker logs -f aspnetrun-redis
docker exec -it aspnetrun-redis /bin/bash
redis-cli
ping
set key value
get key
set name [keyname]
get name

##014 Test on Docker environment - Basket.API and Redis into Docker-Compose File
docker ps
docker stop [container_id]
docker ps -a
docker rm [container_id]

docker-compose -f docker-compose.yml -f docker-compose.override.yml up -d
##015 Container management with Portainer
docker-compose -f docker-compose.yml -f docker-compose.override.yml up -d
##004 Setup PostgreSQL Docker Database for Discount.API Microservices
docker-compose -f docker-compose.yml -f docker-compose.override.yml up -d
# Chap 4
##015 Test on Docker environment - Discount.API and PostgreSQL into Docker-Compose
docker-compose -f docker-compose.yml -f docker-compose.override.yml up -d
docker-compose -f docker-compose.yml -f docker-compose.override.yml down
docker ps
docker ps -a
docker compose

#Chap 5
##005 Managing PostreSQL Database Operations in Discount Grpc
docker-compose -f docker-compose.yml -f docker-compose.override.yml up -d
docker ps

#Chap 6
##005 Test and Run Discount Grpc and Basket Microservice
docker ps
docker-compose -f docker-compose.yml -f docker-compose.override.yml up -d

Set multi startup project (Basket.API, Discount.Grpc)
Testing ...
docker-compose -f docker-compose.yml -f docker-compose.override.yml down
##008 Test on Docker environment - Basket.API integrate Discount.Grpc into DC
docker-compose -f docker-compose.yml -f docker-compose.override.yml up --build
docker-compose -f docker-compose.yml -f docker-compose.override.yml up -d
docker-compose -f docker-compose.yml -f docker-compose.override.yml down
#Chap 7
##031 Adding SqlServer image into Docker-Compose File for Multi-Container Docker Env
docker-compose -f docker-compose.yml -f docker-compose.override.yml up -d
docker ps
#Chap 8
##005 Adding RabbitMQ image into Docker-Compose File for Multi-Container Docker Env
docker-compose -f docker-compose.yml -f docker-compose.override.yml up -d

# IfAThenB
IfAThenB - a routine automation application.

This project consists of 3 microservices + mongoDB database.

## Setup
### Clone this repo with all submodules
```sh
git clone --recursive https://github.com/Bulduper/IfAThenB.git
cd ./IfAThenB
```
### Set enviromental variables
Copy ENV variables templates `.env.template` and set ENV variables in global `.env` file.

```sh
cp .env.template .env
#edit ENVs in .env file
```

### Build docker images
```sh
#cd to parent repo
docker build -t ifathenb-gateway:latest ./IfAThenB-Gateway
docker build -t ifathenb-listener:latest ./IfAThenB-Listener
docker build -t ifathenb-executor:latest ./IfAThenB-Executor
```
### Run docker containers
```
docker compose -f ./ifathenb-compose.yaml up
```

## Trigger types
- HTTP trigger (on http call)
- CRON trigger (recurrent, described by cron pattern)

## Action types
- HTTP request 
- send email

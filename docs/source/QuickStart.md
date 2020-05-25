## Quick Start

#### Generate the data and docker-compose file

```shell script
sudo docker run --rm -v $(pwd):$(pwd) -w $(pwd) fleval:v1 sh -c "python3 4_distribute_data.py && python3 5_generate_docker_compose.py"
```

#### Start the Experiment

```shell script
sudo docker-compose up -d
```

#### View the results

Go to http://127.0.0.1:8200/dashboard to see the results.

Here's an example of the [dashboard](./dashboard.png).

#### Stop the Experiment

Stop and remove the containers

```shell script
sudo docker-compose stop
sudo docker-compose rm
```

Manual stop and remove all the containers

```shell script
sudo docker stop $(sudo docker ps --filter ancestor=fleval:v1 -aq)
sudo docker rm $(sudo docker ps --filter ancestor=fleval:v1 -aq)
```

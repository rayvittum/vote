# Learning Project Vote App

## This github repo is designed around teaching central devops ideas and tools. 

## Prerequisites- have a 3 node swarm (managers), have a custom domain name from https://hover.com/tcZ9z4co 

## Steps to launch tools:

#### 1. ```vim proxy.yml``` (change traefik label entries to your custom domain)
#### 2. ```docker node update --label-add jenkins=jenkins < manager node name >``` (temporary until I add swarm volume tool)
#### 3. ```docker stack deploy -c proxy.yml proxy``` 
#### 4. ```vim swarm-project.yml``` (change traefik labels)
#### 5. ```docker stack deploy -c swarm-project.yml vote```



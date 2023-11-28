# AHI_mindLAMP
Test Environment for mindLAMP for AHI Program
WIP

Sections to include: 
* Setting up the Server
* Setting up Activities 
* Setting up Sensors 
* Creating Users/User Groups
* Assigning Credentials
* Adding Activities and Sensors
* User Perspective
* Extracting data using Python 
* Extracting data using Requests



## instructions
- Modified the docker-compose to include traefik in it 
- Modified to remove swarm, this is just for testing purposes

## deployment
- when it first runs, it will generate a admin password that you will be able to see in the terminal, it will look something like:
```
server_1         |       ┌────────────────────────┬────────────────────────────────────────────────────────────────────┐
server_1         |       │        (index)         │                               Values                               │
server_1         |       ├────────────────────────┼────────────────────────────────────────────────────────────────────┤
server_1         |       │ Administrator Password │ '34b8b1................f6cd' │
server_1         |       └────────────────────────┴────────────────────────────────────────────────────────────────────┘

```

## api documentation issues 

- INSERT DOCUMENTATION HERE FOR ISSUES THAT YOU PREVIOUSLY FOUND 


## api notes for connecting 

- Example endpoint of how to connect: 
```python
import requests 

test_url = 'http://localhost:3000/api/v1/users/login'

test_data = {
    "username": "admin",
    "password": "34b8b1................f6cd"
}

```

## api notes for creating dummy data 


## api notes for pulling down dummy data 

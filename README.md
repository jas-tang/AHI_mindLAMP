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



## Setting up the Server
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

## Logging in as as an Admin

WIP

## Creating an Investigator and your first User

Create an Investigator by clicking the add button. 
![](https://github.com/jas-tang/AHI_mindLAMP/blob/main/images/1.png)
![](https://github.com/jas-tang/AHI_mindLAMP/blob/main/images/2.JPG)

Create a user with a group. 
![](https://github.com/jas-tang/AHI_mindLAMP/blob/main/images/3.JPG)


## Setting up Surveys

Go to this [link](https://docs.lamp.digital/start_here/instruments) to download all the available surveys in JSON formatting. 

From the user or group you created, add the JSON files for the surveys here. 
![](https://github.com/jas-tang/AHI_mindLAMP/blob/main/images/5.png)

Add and import activities. Surveys are listed as activities. 
![](https://github.com/jas-tang/AHI_mindLAMP/blob/main/images/4.png)

## Setting up Activities / Games

WIP

## Setting up Sensors

Start by importing the package, requests. 

We are going to use an HTTP Post request to an endpoint to post sensors to the mindLAMP API. 

```python
import requests
```

Set endpoint equal to your endpoint. 
```python
endpoint = 'https://mindlamp.api.{YOUR_ENDPOINT}.com/sensor_spec'
```

Next, we include the headers in the HTTP request. The headers specify the content type to JSON and includes the authentication needed. 
```python
headers = {
    'Content-Type': 'application/json',
    'Authorization': 'Basic {USER}:{PASSWORD},
    }
```

Next, we include what is needed from the POST request. Replace "activity_recognition" with any of the Sensor types you need from this [link](https://docs.lamp.digital/using/sensors/). 
```python
bodytosend = {"name":"lamp.activity_recognition"}
```

Now, we create the HTTP POST request and print out the results. 
```python
response = requests.post(endpoint, headers=headers, json=bodytosend)
print(response.status_code)
print(response.text)
```

The Sensors should now be able to be added to a user/group from this screen. 
![](https://github.com/jas-tang/AHI_mindLAMP/blob/main/images/6.JPG)


## Creating additional Users/User Groups
Return this this screen to create a User or Group. 
![](https://github.com/jas-tang/AHI_mindLAMP/blob/main/images/3.JPG)

It's important to note to create multiple users if you have multiple, separate people using the application. When creating a new user, a new participant ID will be generated for each individual. 
This will be important later when we try to extract the data.

## Assigning Credentials
Go back to the user screen and click on the key icon to manage credentials. 
![](https://github.com/jas-tang/AHI_mindLAMP/blob/main/images/7.png)

Press the '+' icon to create additional credentials.  
![](https://github.com/jas-tang/AHI_mindLAMP/blob/main/images/8.JPG)

Fill in the information needed for the user.  
![](https://github.com/jas-tang/AHI_mindLAMP/blob/main/images/9.JPG)

After which, the user can log in with the newly created credentials. Each participant ID, meaning each user or user group you created, can have multiple credentials. 
Assigning multiple credentials however, does not create more users or user groups. Instead, create additional users or user groups and assign credentiaals to them as needed.

## User Perspective
WIP

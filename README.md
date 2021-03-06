# Home Automation

As someone who has leaned into the world of smart devices, I have found it frustrating to have an app for every appliance. Limiting control to just my phone means others can't exercise control and if I lose my phone it's all over. My goal is to create a solution that solves these issues (while providing some extra fetures along the way).

This is largely meant to be a learning opportunity for me. The solution will be specific for my use cases, but feel free to take what works for you.

## Features

### Todo List
The todo list is made using shelve. For shelve documentation see:
[Shelve Documentation](https://docs.python.org/3/library/shelve.html)

### Roku
For a full list of actions see:
[Roku API Documentation](https://developer.roku.com/docs/developer-program/debugging/external-control-api.md)

### Hue Lights
For a full list of actions see:
[Hue API Documentation](https://developers.meethue.com/develop/hue-api/)

## EFK stack
If you choose to deploy through Kubernetes, you can view the logs through an EFK stack.

## Standalone Instructions
For those who just want to run the flask app.

1. Install Dependencies
```
pip install Flask
pip install shelve
```

2. Export the necessary info for the app 

```
export roku_ip='<ROKU IP>'
export hue_ip='<HUE IP>'
export hue_username='<HUE USERNAME>'
```

3. Setup up Nginx and Guincorn  
Because Flask recommends that you do not use their development server in a production environment.  
To set up a porper server, you can follow [these steps](https://www.e-tinkers.com/2018/08/how-to-properly-host-flask-application-with-nginx-and-guincorn/) to set up your server.

4. Connect to Raspberry Pi.  
To figure out the ip address type the following into the command line:  
``` 
ifconfig wlan0 
```

### Optional
If you don't want to connect to your pi through an ip address, connect via the hostname.  
By default the pi's hostname will be **raspberrypi.local**  
If you want to change it you can follow [these steps](https://www.tomshardware.com/how-to/raspberry-pi-change-hostname)


## Kubernetes Instructions
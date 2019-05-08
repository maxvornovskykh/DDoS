# DDoS
Simplest possible sandbox to play with slowloris atack [script](https://github.com/tj/slowloris)

# Description
App consists of two services:
* victim - simple static site behind nginx proxy
* attacker - nodejs script that simulates slowloris attack

# Build
To build images:
```
docker-compose build
```
in the root project directory.

# Run
To launch services:
```
docker-compose up
```
After that, victim starts and attacker starts DDoS attack on it. 
Victim site returns 400 and 408 codes for slow requests and corresponding logs are printed to containers' logs.

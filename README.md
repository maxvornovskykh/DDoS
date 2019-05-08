# DDoS
Simplest possible sandbox to play with Slowloris Attack ([This script is used, thx tj](https://github.com/tj/slowloris))

# Description
App consists of two services:
* victim - simple static site behind nginx proxy
* attacker - nodejs script that simulates slowloris attack

The attacker service attacks victim by sending slow long running requests and the victim service mitigates the attack effects.

Nginx configs to mitigate the effect:
* Closes slow connections
* Limits the rate of requests
* Limits the number of connections
* Uses caching to smooth traffic spikes
* Default worker_connections limit increased

In addition to configurations described above, the next OS configs should be considered in real environment:
* User open file limit
* System open file limit

All limiting values in nginx config are set for demonstration purpose and should be reconsidered for the real project.

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

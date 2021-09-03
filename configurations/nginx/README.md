# Nginx
***

This contains an example configuration for nginx for a Dispike bot.
***

## Info:
- A valid Certificate keypair is required.

***

## Setup + Running


*Example Dispike Bot*
```python
# sample.py

from dispike import Dispike

bot = Dispike(...)
```


### Run Dispike
You can either:
- Use the provided ``.run`` function in your dispike instance. 
  - You'll need to bind to a unix sock (dispike.sock)
    - ```python bot.run(unix_socket="unix:/dispike.sock")```
- Run the bot using [Uvicorn](https://www.uvicorn.org/deployment/) (or Hypercorn) and reference ``.referenced_application`` attribute on an initalized Dispike object.
  - ```uvicorn sample:bot.referenced_application --port XXXX``` (Requires nginx configuration change, or you can bind to a socket instead and keep the configuration.)
  
- Run [Nginx](https://www.nginx.com/resources/wiki/start/topics/tutorials/commandline/)
You can keep Dispike running in the background by using a process manager such as Supervisor or PM2.

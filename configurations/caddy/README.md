# Caddy (v2)
***

This contains an example configuration for Caddy for a Dispike bot.
***

## Info:
- This configuration is **only for v2 of Caddy**.
- A valid Certificate keypair is required ([caddy can generate one for you](https://caddyserver.com/docs/automatic-https#automatic-https))

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
  - You'll need to bind to a local ip address (127.0.0.1) and bind to 9000.
    - ```bot.run(port=9000)```
- Run the bot using [Uvicorn](https://www.uvicorn.org/deployment/) (or Hypercorn) and reference ``.referenced_application`` attribute on an initalized Dispike object.
  - ```uvicorn sample:bot.referenced_application --port 9000``
  
- Run [Caddy](https://caddyserver.com/docs/getting-started)
- You can run dispike in the foreground and let caddy run the background.

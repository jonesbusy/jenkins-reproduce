Used to reproduce some Jenkins bug in isolated environment

## Steps to reproduce

Start controller

`docker-compose up -d jenkins`

Take the agent secret and update the docker-compose-agent.yaml file

Start agent

`docker-compose up -d agent`

That's all folks!

> [!NOTE]
> DOn't use such configuration in production. It's unsecure

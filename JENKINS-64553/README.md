Used to reproduce some Jenkins bug in isolated environment

## Steps to reproduce

Ensure you have set $GH_TOKEN on your environment (it's used for GitHub API). Only public read access is required to avoid rate limit.

Go in folder and run `docker-compose up` to start Jenkins

That's all folks!

> [!NOTE]
> DOn't use such configuration in production. It's unsecure

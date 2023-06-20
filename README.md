# openapi-gen-go-gin

An example API written with the Go Gin web framework to demonstrate generating an OpenAPI v3 specification.

# Getting started

These steps assume you have Go and Curl installed.

Note: It'll be easiest to follow along if you run steps 2-4 in their own terminal windows or panes.optic

1. Install deps, `go mod tidy`.
1. Start the app, `go run main.go`. It will run on port `8080`. 
1. Start the Optic proxy, `optic capture --reverse-proxy openapi.yml http://localhost:8080`.
1. Send traffic to the Optic proxy by running, `./curl.sh`.
    - Take a peek inside this script too. It's just running `curl` commands for the API endpoints.
1. Stop the app and the proxy with `ctrl-c` in their respective terminals.
1. Write the captured traffic to `./openapi.yml`, `optic update openapi.yml --all`

If you take a look at newly generated `openapi.yml` file you see 3 documented endpoints that correspond to the `./curl.sh` file. You can change the endpoints, add or remove them, and rerun steps 2-5 to update your OpenAPI file.
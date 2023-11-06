# Stripe CLI Bash
Stripe bash script and environment for running one-off commands using the Docker
Stripe-CLI

## Installation
1. Clone this repo
2. Create environment file by running `cp .env.example .env`
3. Fill in the environment variables in the `.env` file
4. Run `./stripe <command>` to run a command using the Stripe-CLI

# Tips

## Forwarding events to webhook endpoints in Docker containers

When running the Stripe `listen` command to forward events to a webhook endpoint
running in a Docker container, you may need to use the `host.docker.internal`
hostname to forward events to the container as well as skipping certificate
verification. For example:

```bash
./stripe listen --forward-to https://host.docker.internal:/path/to/endpoint/ \
    --skip-verify
```

_Reference: [GitHub Docker and Port Mapping](https://github.com/stripe/stripe-cli/issues/547)_

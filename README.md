# What

This is a docker image of caddy built with [caddy-dns/cloudflare](https://github.com/caddy-dns/cloudflare).

# Why

You can use this for many things, I use it mostly to add TLS to my website without using untrusted certs.

# How

It's very easy; generate an API key and fill in a few values!

1. Generate an API key that allows TLS certs to be configured; Cloudflare has instructions.
2. Fill in your API key in the `docker-compose.yml` file
3. Make a `./data` directory for persistence of generated certs
4. Change the domain to be published in the `Caddyfile` (e.g. `example.my_domain.com`)
5. Change the email the `Caddyfile`; caddy uses this email for the ACME account managing the site's certificates; you should be able to set it to your Cloudflare email)
6. Set what site you want to proxy in the `Caddyfile`. The example given is proxying `localhost:8000`.
7. `docker-compose up` or `docker compose up` depending on what you have installed.

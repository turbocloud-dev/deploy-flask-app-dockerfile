# Flask App Dockerfile Example

This repository includes an example Dockerfile for a Flask app. By using this Dockerfile, you can deploy the app almost anywhere, including Hetzner, DigitalOcean, OVH, Scaleway, AWS, or even a Raspberry Pi.

## Prerequisites

### Prepare your project

1. Copy the Dockerfile from this repository into the root folder of your project.
2. Verify that the path to the main Python file is correct in the Dockerfile. For example, ensure the `CMD` line points to your app's entry point: `CMD ["src/main.py"]`.
3. Ensure `requirements.txt` is located in the root of your project's folder.

### Prepare a server

Set up a new server on your cloud provider with:
- A public IP address
- SSH access from your development machine
- A fresh Ubuntu 22.04 installation.

Ensure the following ports are open:
- **22** (SSH)
- **80** (HTTP)
- **443** (HTTPS)

Note: Some cloud providers, such as AWS, close ports by default. Make sure to open these ports before proceeding with deployment.

## Deploy with a Single Command

### From a Local Machine

Run the following command from your project directory:

```bash
cd my_project
curl https://turbocloud.dev/deploy | bash -s -- -i server_ip -p service_port
```

Replace `server_ip` with your server's IP address and `service_port` with the desired service port.

### From GitHub or Bitbucket with CI

1. SSH into your server:

```bash
ssh root@server_ip
```

2. Run the following setup command:

```bash
curl https://turbocloud.dev/setup | bash -s
```

3. Deploy the app using the **Turbocloud** CLI:

```bash
turbocloud
```

## Step-by-Step Guide

For detailed instructions, refer to the [Self-hosting Handbook](https://turbocloud.dev/book/deploy-flask-app/).

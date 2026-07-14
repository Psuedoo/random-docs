# Joining a Game Server

All game servers are managed through [CubeCoders AMP](https://admin.psuedo.dev){ target="_blank" rel="noopener" } — the Application Management Panel. When a game server is set up, connecting to it depends on how your access is configured.

---

## Connection Methods

There are three ways to connect to a game server, depending on how Psuedo has configured access:

### Tailscale (Easiest)

If you're connected to the **Tailnet** (our Tailscale network), you can connect directly to the game server using the Tailscale IP of the server host and port. No port forwarding or nginx configuration is needed.

1. Make sure you're connected to Tailscale and are a member of our Tailnet.
2. Use the Tailscale IP of the server host (typically `amp`) and the port provided by Psuedo.
3. Connect as you normally would from any game client.

If you aren't part of our Tailnet yet, ping Psuedo to get added.

### SWAG Nginx (Reverse Proxy)

Some game servers may be exposed through our **SWAG Nginx** reverse proxy. This allows external access without Tailscale, using a friendly domain name.

1. Psuedo must configure the appropriate nginx proxy rules.
2. Once set up, you'll receive a domain and port (e.g., `game.psuedo.dev:25565`).
3. Connect using that address from your game client.

### Port Forwarding (Manual)

If the server uses direct port forwarding, Psuedo must manually forward the game server's port through the firewall.

1. Psuedo configures a port forward on the router/firewall.
2. You connect using the **public IP** and the forwarded port.
3. Port forwarding is only an option when you need a public game server and the other two methods aren't viable.

---

## Game Server Panel

All server management happens at the AMP panel:

[Open AMP Panel](https://admin.psuedo.dev){ .md-button .md-button--primary target="_blank" rel="noopener" }

If you're having issues from an operator standpoint, reach out to Psuedo for help or reference the [CubeCoders AMP docs](https://discourse.cubecoders.com/docs/){ target="_blank" rel="noopener" }.

---

## Connection Checklist

Before trying to connect, confirm with Psuedo:

- [ ] Which game server you want to join
- [ ] Which connection method is available (Tailscale, Nginx, or port forwarding)
- [ ] The IP / domain and port to use
- [ ] Whether you need a password or whitelist entry
- [ ] That the server is currently running

---

## FAQ

### Why can't I connect from outside the Tailnet?

This is by design. Most game servers are intentionally not exposed to the public internet. Connect to the Tailnet first, or ping Psuedo about getting external access set up through the nginx reverse proxy.

---

### My connection is slow or laggy.

Tailscale connections may have higher latency than a direct connection. If performance is an issue, ping Psuedo about setting up a direct connection via port forwarding or nginx.

---

### I'm on the Tailnet but still can't connect.

Make sure you're using the correct **Tailscale IP**. If the port is wrong or the server isn't running, the connection will fail. Verify the address with Psuedo.

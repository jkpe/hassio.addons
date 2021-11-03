# Home Assistant Add-on: Cloudflare Tunnel

![Project Stage][project-stage-shield]

_[Cloudflare Tunnel](https://github.com/cloudflare/cloudflared) provides you with a secure way to connect your resources to Cloudflare without a publicly routable IP address. With Tunnel, you do not send traffic to an external IP — instead, a lightweight daemon in your infrastructure (cloudflared) creates outbound-only connections to Cloudflare’s edge. This way, your origins can serve traffic through Cloudflare without being vulnerable to attacks that bypass Cloudflare._

## Prerequisites
1. A domain name registered with a Cloudflare Account

## Configuration
1. Browse here and generate a certificate for the tunnel to use: https://www.cloudflare.com/a/warp
2. Upload your certificate to Home Assistant at path /config/cert/argo.pem
3. Set the following fields in the add-on's configuration tab:
   - hostname (this is the domain name you intend to host Home Assistant at. Example: `home.example.com`
4. Start the add-on
5. Check the logs and you should see `Starting tunnel tunnelID=` followed by your new tunnel's UUID.
6. Create a new DNS record in the Cloudflare Dashboard. When you create a tunnel, Cloudflare generates a subdomain of cfargotunnel.com with the UUID of the created tunnel. You can treat that subdomain as if it were an origin target in the Cloudflare dashboard. Example: `CNAME` record `home.example.com` pointing to `12345678-xxxx-xxxx-xxxx-123456123456.cfargotunnel.com`

![Supports aarch64 Architecture][aarch64-shield]
![Supports amd64 Architecture][amd64-shield]
![Supports armhf Architecture][armhf-shield]
![Supports armv7 Architecture][armv7-shield]
![Supports i386 Architecture][i386-shield]

[aarch64-shield]: https://img.shields.io/badge/aarch64-yes-green.svg
[amd64-shield]: https://img.shields.io/badge/amd64-yes-green.svg
[armhf-shield]: https://img.shields.io/badge/armhf-yes-green.svg
[armv7-shield]: https://img.shields.io/badge/armv7-yes-green.svg
[i386-shield]: https://img.shields.io/badge/i386-yes-green.svg
[project-stage-shield]: https://img.shields.io/badge/Project%20Stage-Development-yellowgreen.svg


Original work based on: https://github.com/wlatic/hassio.addons

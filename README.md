# forge2-dashboard

A Homepage dashboard for everything running on forge2 — Control Center, the
TV boards, QuoteCard Forge, the card API — laid out in `dashboard/services.yaml`.

## Run it

On forge2:

```sh
git clone https://github.com/jayjaybeonone/solid-invention.git /opt/forge2-dashboard
cd /opt/forge2-dashboard
docker compose up -d
```

Dashboard is then at http://198.23.150.34:3003 (port 3000 belongs to the card API).

## Auto-deploy

`.github/workflows/deploy.yml` runs on every push to `main`: it SSHes into
forge2, pulls, and restarts the stack. It needs three repository secrets
(Settings → Secrets and variables → Actions):

- `FORGE2_HOST` — 198.23.150.34
- `FORGE2_USER` — root
- `FORGE2_SSH_KEY` — private key whose public half is in forge2's
  `/root/.ssh/authorized_keys`

## Edit the layout

Change `dashboard/services.yaml`, push, and the runner redeploys it.

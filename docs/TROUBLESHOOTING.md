# Troubleshooting & FAQ

Common questions and issues for Cubewise Distro. If your problem is not covered here, open an issue using the templates in this repository.

## Checking that Distro is running

Distro exposes readiness and version endpoints on its service port (default `4444`):

- `GET /readyz` — confirms background startup has completed.
- `GET /api/v1/version/` — returns the running Distro version (with a valid license).

## Common issues

| Symptom | Guidance |
|---|---|
| `/readyz` returns `503 starting` | Background startup is not finished yet. Wait and retry, and check the application log. |
| HTTP `401` "License check failed" | The service is running but has no valid license yet. Add the license file (`license.json`) and re-verify. |
| Non-GET API calls return `401` | CSRF protection is active. Use the web UI flow or a supported API key / token. |
| Database initialization fails | Confirm the database URL is correct, the host is reachable, and the database user has privileges to create the database or run migrations. |
| Host port already in use | Change the host port (container: `DISTRO_HTTP_PORT`; Windows: the service port on the Runtime Configuration page) and reopen the firewall port. |
| Browser export fails or times out | Confirm the bundled browser and driver are present, the application can write to its download / export / screenshot folders, and the source system (TM1Web / UX / PAW / NextGen) is reachable. |
| Export produces a blank or missing file | Confirm the source asset is reachable and the profile has a valid output / distribution target. Attach the export history and log when reporting. |

## Where are the logs?

- **Container deployment:** `data/log/cubewise_distro.log`
- **Windows installer:** the log under the Distro install directory.

Include the relevant log snippet (with credentials redacted) when you open a bug report.

## Deployment methods

Distro can be installed as:

- **Windows installer (NSIS)** — runs Distro as a Windows service; requires an external PostgreSQL or SQL Server database.
- **Container (Podman / Docker Compose)** — a self-contained Linux release package that includes a PostgreSQL service.

For full installation, configuration, and admin guidance, use the documentation provided with your deployment package.

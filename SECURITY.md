# Security Policy

GeoProteoNet is an academic prototype, not a production medical application. Do not deploy it to the public internet or use it with real patient information.

## Supported version

Security fixes, if any, are applied to the current `main` branch. This project has no formal support or response-time guarantee.

## Reporting a vulnerability

Please report suspected vulnerabilities privately through GitHub's repository security reporting feature, if enabled. If private reporting is unavailable, contact the repository owner through their GitHub profile before publishing details.

Please do not include API keys, credentials, patient information, or private medical images in issues or reports.

## Data and credentials

- Keep local `.env` files, databases, and uploaded images out of version control.
- Treat any credential previously committed to a public branch or history as exposed; revoke or rotate it.
- Use only synthetic or properly de-identified sample data for development.
- Configure authentication, authorization, access controls, and deployment-specific CORS origins before any broader deployment.

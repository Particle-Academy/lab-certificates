# lab-certificates

Signed lab-run certificates for Particle Academy releases, one file per release at `<package>/<version>.json`.

Each is canonical JSON signed with Ed25519 by the Fancy lab (`php artisan lab:certify`). The public key is `public-key.ed25519`.

The tag hook and every publish workflow verify the certificate for the exact commit and version before a release. A missing or invalid certificate refuses the release.

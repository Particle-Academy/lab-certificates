# lab-certificates

Signed lab-run certificates for Particle Academy releases, one file per release at `<package>/<version>.json`.

Each is canonical JSON signed with Ed25519 by the Fancy lab (`php artisan lab:certify`). The lab's public keys are in `lab-cert-keys.json`, each with the window it was valid in; a record names its key with `key_id`, and one with no `key_id` was signed by the first key. The first key was retired on 2026-11-18: it verifies the certificates it had already issued, listed by signature, and nothing else. This copy is for people. The verifiers pin their own copy and never read keys from here.

The tag hook and every publish workflow verify the certificate for the exact commit and version before a release. A missing or invalid certificate refuses the release.

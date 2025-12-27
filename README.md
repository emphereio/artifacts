# Emphere Artifacts

  Public artifacts for verifying Emphere container images.

  ## Cosign Public Key

  All Emphere base images are signed using [Cosign](https://github.com/sigstore/cosign). Use the public key in this repository to verify image signatures and SBOM attestations.

  ### Verify Image Signature

  ```bash
  cosign verify --key https://raw.githubusercontent.com/emphereio/artifacts/main/cosign.pub IMAGE

  Verify SBOM Attestation

  cosign verify-attestation --key https://raw.githubusercontent.com/emphereio/artifacts/main/cosign.pub --type cyclonedx IMAGE

  Example

  # Verify the Debian 12 base image
  cosign verify \
    --key https://raw.githubusercontent.com/emphereio/artifacts/main/cosign.pub \
    us-central1-docker.pkg.dev/prj-p-eka/bases/debian-12:latest

  Key Fingerprint

  You can verify the key fingerprint:

  curl -s https://raw.githubusercontent.com/emphereio/artifacts/main/cosign.pub | openssl ec -pubin -text -noout

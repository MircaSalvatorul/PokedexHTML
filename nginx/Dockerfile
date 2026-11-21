# Front door from Lab 3: nginx terminates TLS in front of OpenSearch Dashboards.
# Pinned by tag and digest, so the build never floats.
FROM nginx:stable-alpine-slim@sha256:8c950211a641ec5b23f265450517001f6bcca533666120ebe36cb4cff3d00a55

# Apply available Alpine security patches (fixes CVE-2026-86144 in libxml2)
RUN apk upgrade --no-cache

# Site config only. Certificates stay out of the image and are mounted at runtime
# from certs/ (git-ignored), exactly as in compose.yaml.
COPY frontdoor.conf /etc/nginx/conf.d/default.conf

EXPOSE 443

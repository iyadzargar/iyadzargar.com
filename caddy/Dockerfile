# SPDX-FileCopyrightText: 2026 Iyad
# SPDX-License-Identifier: Apache-2.0

# The 2.11.8 images include the fixes for GHSA-r766-rf9f-588h and GHSA-f278-mgc7-46j3.
# xcaddy builds v2.11.9 on top for GHSA-q34h-28rj-5hjm (FastCGI header spoofing) and
# GHSA-mgcc-cww5-fp2q (go-jose). The official caddy:2.11.9 images aren't published yet,
# so bump these tags to 2.11.9 once they are.
FROM caddy:2.11.8-builder AS build
RUN xcaddy build v2.11.9 --with github.com/mholt/caddy-ratelimit@v0.1.0

FROM caddy:2.11.8
COPY --from=build /usr/bin/caddy /usr/bin/caddy

# bilbycast-manager releases

Official binary releases of **bilbycast-manager**, the control-plane and management UI for the Bilbycast broadcast transport suite. Published by **Softside Tech Pty Ltd** (ACN 606961077).

The bilbycast-manager source is proprietary and is not published in this repository. This repository exists to host **release artifacts only**, so that licensed customers can download official binaries without needing access to the private source repository.

## Licence

bilbycast-manager is licensed under the **bilbycast-manager End-User Licence Agreement** (EULA). A copy is included as [`LICENSE`](LICENSE) and published at [`https://bilbycast.com/eula`](https://bilbycast.com/eula).

**By downloading, installing, or using any binary distributed from this repository, you agree to be bound by the EULA.** If you do not agree, do not download or install the Software.

- The EULA restricts production use to the **Node Limit** and **feature set** encoded in your Licence Key.
- Commercial use beyond the scope of your Licence Key requires a new or updated Order.
- Reverse engineering, redistribution, SaaS resale, appliance embedding, and Licence Key circumvention are prohibited — see EULA §4 (Restrictions) and §5 (Licence Keys and enforcement).
- Usage may be audited — see EULA §6 (Audit and compliance verification).
- Data-handling practices are described in the Privacy Policy at [`https://bilbycast.com/privacy`](https://bilbycast.com/privacy).

Third-party open-source components bundled with the Software are listed in [`NOTICE`](NOTICE). Those components remain licensed under their respective open-source licences.

## Installation

Each release publishes a static musl Linux x86_64 tarball with no runtime dependencies. Check the [Releases](../../releases) tab for the most recent build.

```bash
# Download the latest release
curl -LO https://github.com/Bilbycast/bilbycast-manager-releases/releases/latest/download/bilbycast-manager-x86_64-linux.tar.gz
curl -LO https://github.com/Bilbycast/bilbycast-manager-releases/releases/latest/download/bilbycast-manager-x86_64-linux.tar.gz.sha256

# Verify the checksum
sha256sum -c bilbycast-manager-x86_64-linux.tar.gz.sha256

# Extract and start
tar xzf bilbycast-manager-x86_64-linux.tar.gz
cd bilbycast-manager-*/

export BILBYCAST_JWT_SECRET=$(openssl rand -hex 32)
export BILBYCAST_MASTER_KEY=$(openssl rand -hex 32)

./bilbycast-manager setup           # one-time: init DB + first admin user
./bilbycast-manager serve --config config/default.toml
```

Each tarball contains:

```
bilbycast-manager-<version>/
  bilbycast-manager        # binary (static musl)
  migrations/              # SQLite migrations (auto-applied on startup)
  config/default.toml      # default configuration
```

Complete installation, TLS, and configuration documentation is published at [`https://bilbycast.com/getting-started`](https://bilbycast.com/getting-started).

## Enquiries

- **General enquiries**: `contact@bilbycast.com`

## Source code availability

The bilbycast-manager source code is proprietary. Access to source is provided to commercial licensees under negotiated terms; contact `contact@bilbycast.com` to discuss source-availability options for your deployment.

Related open-source projects in the Bilbycast suite — bilbycast-edge, bilbycast-relay, bilbycast-srt, bilbycast-rist, bilbycast-libsrt-rs, bilbycast-fdk-aac-rs, bilbycast-ffmpeg-video-rs, bilbycast-bonding — are published under open-source licences at [`https://github.com/Bilbycast`](https://github.com/Bilbycast).

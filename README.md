# GAM snap (`gam-bp`)

An unofficial snap package of [GAM](https://github.com/GAM-team/GAM), the
command line tool for Google Workspace admins.

The snap is published on two tracks, one per GAM major version:

- **`7`** (default) — GAM 7, actively maintained. See [README-v7.md](README-v7.md).
- **`latest`** — GAM 6, legacy. See [README-v6.md](README-v6.md).

The two majors are not configuration-compatible, so each lives on its own
track. GAM 7 is the default, so a plain install gets it:

    sudo snap install gam-bp                          # GAM 7 (default track)
    sudo snap install gam-bp --channel=latest/stable  # GAM 6 (legacy)

## Migrating from v6 to v7

GAM 6 (the `latest` track) is legacy and will likely never be updated again.
Migrate to the `7` track when convenient:

    sudo snap refresh gam-bp --channel=7/stable

Because GAM 6 and GAM 7 store their configuration differently, you will need to
**reauthorise** after switching. See [README-v7.md](README-v7.md) for the GAM 7
configuration and migration details.

Snap recipe: https://github.com/barryprice/snap-gam

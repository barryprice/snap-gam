# GAM 7

GAM is a command line tool for Google Workspace admins to manage domain and
user settings quickly and easily.

This is an unofficial snap package of GAM 7. Because GAM does not yet honour
freedesktop's `XDG_CONFIG_HOME` (upstream issues #791 and #792 remain open),
the snap sets `GAMCFGDIR` so each user's configuration lives under their own
snap area, enabling a multi-user install:

https://github.com/GAM-team/GAM/issues/791

https://github.com/GAM-team/GAM/issues/792

## Installing

GAM 7 is published to the `7` track, which is the snap's default. GAM 6 remains
on the `latest` track, as the two majors are not configuration-compatible:

    sudo snap install gam-bp --channel=7/stable

(Use `--channel=7/edge` for pre-release builds.)

For simplicity's sake, it's also recommended to add a snap alias:

    sudo snap alias gam-bp.gam gam

## Configuration

Per-user settings are stored in `$HOME/snap/gam-bp/common/.config/`

Global (immutable) settings are staged in
`/snap/gam-bp/current/lib/python3.14/site-packages/`

This snap adds two opinionated global settings, disabling both update checks
(to update, refresh the snap itself instead) and short URLs.

Migrating existing authorisation settings from a manual install to the snap is
straightforward:

    cp /path/to/manual/gam/{*.json,oauth2.txt*} ~/snap/gam-bp/common/.config/

Upstream: https://github.com/GAM-team/GAM

Snap recipe: https://github.com/barryprice/snap-gam

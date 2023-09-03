# GAM

GAM is a command line tool for Google Workspace admins to manage domain and
user settings quickly and easily.

This is an unofficial snap package, which patches the source code to enable a
multi-user install, while we await resolution of upstream issues:

https://github.com/GAM-team/GAM/issues/791

https://github.com/GAM-team/GAM/issues/792

Per-user settings are stored in $HOME/snap/gam-bp/common/.config/gam

Global (immutable) settings are stored in /snap/gam-bp/current/lib/python3.10/site-packages/

This snap adds two opinionated global settings, disabling both update checks
(to update, refresh the snap itself instead), and also disabling short URLs.

Migrating existing authorisation settings from a manual install to the snap is
straightforward:

    cp /path/to/manual/gam/{*.json,oauth2.txt*} ~/snap/gam-bp/common/.config/gam/

For simplicity's sake, it's also recommended to add a snap alias:

    sudo snap alias gam-bp.gam gam

Upstream: https://github.com/GAM-team/GAM

Snap recipe: https://github.com/barryprice/snap-gam

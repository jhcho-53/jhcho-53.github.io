# CLAUDE.md

Personal homepage (al-folio v1.x, Jekyll) for Jaehyeon Cho, deployed to https://jhcho-53.github.io with an empty `baseurl`.
See `README.md` for which file holds which content and for the local build commands.

- al-folio v1.x is a thin starter: layouts/includes/Sass live in `al_*` gems. To change rendering, shadow the gem file locally
  (see `docs/ARCHITECTURE.md`), don't patch the gem.
- Plugins must be listed in both `Gemfile` and `_config.yml`; features fail silently otherwise.
- Builds need a UTF-8 locale (`LANG=en_US.UTF-8`) because the folder path contains Korean characters.
- Build output goes outside OneDrive (`-d /tmp/...`); gems go to `$HOME/.cache/homepage-bundle`.
- Never publish the phone number from `CV_JJH.pdf`; that file is git-ignored and excluded from the build.

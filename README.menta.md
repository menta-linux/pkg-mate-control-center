# pkg-mate-control-center (Menta Linux)

Debian packaging of mate-control-center 1.28.2 (from debian-mate-team on Salsa, 1.28.1-1).

Changes:
- New upstream 1.28.2.
- Patches from upstream PRs (quilt, `debian/patches/3001-3004`):
  [#832](https://github.com/mate-desktop/mate-control-center/pull/832) default-applications icon names,
  [#839](https://github.com/mate-desktop/mate-control-center/pull/839) keybindings Wayland crashes
  (commit 2 adapted to 1.28.2: it needs a non-X11 guard that exists only on master),
  [#840](https://github.com/mate-desktop/mate-control-center/pull/840) keyboard Wayland crash,
  [#841](https://github.com/mate-desktop/mate-control-center/pull/841) typing-break on Wayland.
- Built with meson: the typing-break Wayland idle monitor (ext-idle-notify-v1) is meson-only.
  Wayland is auto-detected and required via Build-Depends. Upstream 1.28.2 has no
  wayland or in-process build option, and this package has no panel applets.

Versioning: `<upstream>-<rev>mentaN` (`1.28.2-1menta1`); bump with `dch -i`.
CI builds on push to `master`; a `menta/<version>` tag publishes a GitHub release.
Needs the menta libmate-desktop/marco/mate-settings-daemon-dev if Debian's are too old.

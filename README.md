# Librewolf Gentoo

Librewolf packaging for Gentoo.

## Usage

### Manual way

Create the `/etc/portage/repos.conf/librewolf.conf` file as follows:

```
[librewolf]
priority = 50
location = /var/db/repos/librewolf
sync-type = git
sync-uri = https://codeberg.org/librewolf/gentoo.git
auto-sync = Yes
```

Then run `emaint sync -r librewolf`, Portage should now find and update the repository.

### Eselect way

On terminal:

```bash
sudo eselect repository add librewolf git https://codeberg.org/librewolf/gentoo.git
```

And then run `emaint sync -r librewolf`, Portage should now find and update the repository.

## Contributing

Before submitting an issue please verify that the issue doesn't occur on Gentoo's `www-client/firefox` package.

## Packaging Workflow

To make things easy to update the `www-client/librewolf` and `www-client/librewolf-bin` ebuilds are based on the `www-client/firefox(-bin)` ebuilds from Gentoo's default repository.

_Personally I use `diff -aur <librewolf ebuild> <firefox ebuild>` when making version bumps._

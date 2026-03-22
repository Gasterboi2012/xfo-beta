# xfo-beta &nbsp; [![bluebuild build badge](https://github.com/gasterboi2012/xfo-beta/actions/workflows/build.yml/badge.svg)](https://github.com/gasterboi2012/xfo-beta/actions/workflows/build.yml)

This is a custom Fedora Kinoite image i developed to suit my needs, this image isnt very customized and only contains preinstalled apps, fonts, and nvidia drivers.
Because this image was developed for my purposes only, it is not advised to use this and rather, make your own image.
i do not plan to add any custom "logos" besides changing the fastfetch

## Installation

> [!WARNING]  
> [This is an experimental feature](https://www.fedoraproject.org/wiki/Changes/OstreeNativeContainerStable), try at your own discretion.

To rebase an existing atomic Fedora installation to the latest build:

- First rebase to the unsigned image, to get the proper signing keys and policies installed:
  ```
  rpm-ostree rebase ostree-unverified-registry:ghcr.io/gasterboi2012/xfo-beta:latest
  ```
- Reboot to complete the rebase:
  ```
  systemctl reboot
  ```
- Then rebase to the signed image, like so:
  ```
  rpm-ostree rebase ostree-image-signed:docker://ghcr.io/gasterboi2012/xfo-beta:latest
  ```
- Reboot again to complete the installation
  ```
  systemctl reboot
  ```

The `latest` tag will automatically point to the latest build. That build will still always use the Fedora version specified in `recipe.yml`, so you won't get accidentally updated to the next major version.

## You can also build the image from source (Which is reccommended)

-First, install bluebuild
 
  https://github.com/blue-build/cli

-Then, build
```
sudo bluebuild generate-iso --iso-name xfo-oper-sys.iso image ghcr.io/gasterboi2012/xfo-beta
 ```

# Build Yay Packages Faster

Use RAM for builds and let `makepkg` use all CPU cores.

1. Edit `/etc/makepkg.conf`:

   ```sh
   sudo editor /etc/makepkg.conf
   ```

2. Uncomment and set the build directory:

   ```conf
   BUILDDIR=/tmp/makepkg
   ```

   This uses RAM only if `/tmp` is mounted as `tmpfs`.

3. Set `MAKEFLAGS` to use all CPU cores:

   ```conf
   MAKEFLAGS="-j$(nproc)"
   ```

   Large builds (such as Firefox, Chromium, or Unreal Engine 4) can use too much
   memory and freeze your system. For those, build on disk instead:

   ```sh
   BUILDDIR="$HOME/build_disk" makepkg -si
   ```

Clear Yay's package cache with:

```sh
yay -Sc
```

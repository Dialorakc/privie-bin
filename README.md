# Privie
Currently in beta. Source code will be released
under GPL License when v0.10 is reached.

     /\_/\
    ( o.o )  privie v0.03
     > ⋈ <   (purr responsibly)

*pronounced "prri-vie" if you're feeling fancy*

## What is Privie?
Privie is a lightweight, fast text editor designed for the terminal with vim-style keybindings. Built for developers who want speed and efficiency without the bloat.

### Features
- **Fast**: Written in C/C++ for maximum performance
- **Vim Keybindings**: Configured with vim keybindings for maximum speed
- **Purrfect**: Absolutely no bugs (i think ( ・-・) ?)

## Installation guide
1. Runtime Dependencies
    ```bash
    # Arch
    sudo pacman -S ncurses gcc-libs libdrm wayland libffi

    # Debian/Ubuntu
    sudo apt install libncurses6 libtinfo6 libstdc++6 libdrm2 libwayland-client0 libffi8

    # Fedora
    sudo dnf install ncurses-libs libstdc++ libdrm wayland-devel libffi

    # Gentoo
    sudo emerge sys-libs/ncurses sys-devel/gcc x11-libs/libdrm dev-libs/wayland dev-libs/libffi
    ```

2. Installation
    ```
    git clone https://github.com/Dialorakc/Privie.git
    cd Privie
    chmod +x privie_v0.03-1(Wayland)
    ./privie_v0.03-1(Wayland)
    ```
    ```bash
    ## To install system-wide
    git clone https://github.com/Dialorakc/Privie.git
    cd Privie
    chmod +x privie_v0.03-1(Wayland)
    sudo mv privie_v0.03-1(Wayland) /usr/local/bin/vie

    vie <filename>
    ```
> [!NOTE]
> You may need to run it with sudo, depending on your distro.
#
> [!IMPORTANT]
> if you are on gentoo or compiled the kernel, ensure legacy /dev/fb* devices are enabled

```bash
cd /usr/src/linux
sudo make menuconfig
```

*Navigate with your arrow keys to*
```
Device Drivers ---->
    Graphics support ---->
        Frame buffer Devices ---->
            [*] Provide legacy /dev/fb* devices
```

> Ensure your kernel has Direct Rendering Manager (DRM) enabled for your specific GPU (Intel, AMD, and Nvidia), for Wayland support

```bash
cd /usr/src/linux
sudo make menuconfig
```

*Navigate with your arrow keys to*
```
Device Drivers ---->
    Graphics support ---->
        <*> Direct Rendering Manager (XFree86 4.1.0 and higher hardware support)
```

> Inside the DRM menu, select the driver for your specific hardware:

```
# For Intel Integrated Graphics
    <*> Intel 8xx/9xx/G3x/G4x/HD Graphics

# For AMD/Radeon
    <*> Amdgpu (AMD GPU)

# For NVIDIA (Open Source)
    <*> Nouveau (NVIDIA)

# For Virtual Machines (QEMU/KVM/VirtManager)
    <*> Virtio GPU driver
```

> [!NOTE]
> if [*] or <*> (built-in) or < M > (module) is already present, it has been enabled and you can skip this step.
> Otherwise, press y to enable it and exit, make sure to save the new configuration

### Rebuild your Kernel
> ```bash
> sudo make -j$(nproc) #or the number of you cpu threads, eg. for 5 cpu threads -j5
> sudo make modules_install
> sudo make install

> Once done, update your grub and reboot
> ```bash
> sudo grub-mkconfig -o /boot/grub/grub.cfg
> ```


> everything is tested in the tty
> once i get it working, it would be ported to x11 and wayland, since they do not support direct fb access

## Usage
### Available Vim Keybinds
> - h, j, k, l (Navigation(left, down, up, right))
> - d (Delete line)
> - D (Delete to end of line)
> - a, i, A, I (write behind cursor, write a cusor position, write at the end of the line, write at the begining of the line)
> - g, G (move to the top of the file, move to the bottom of the file)
> - w, q (write and quit)
> - ctrl + t (switch between editor and terminal)

### Command-Line Flags
```bash
vie [OPTIONS]

Options:
  -V, --version      Display version information
  -T, --terminal     Launch in terminal mode
  -h, --help         Display help with examples
```

## Testing & Feedback
This is beta software! Please report bugs and suggestions:

- Issues: [GitHub Issues](https://github.com/Dialorakc/privie-bin/issues)
- Discussions: [GitHub Discussions](https://github.com/Dialorakc/privie-bin/discussions)

## Known Limitations

- Mainly tested in TTY (framebuffer mode)
- Currently working on Wayland support (minor bugs/errors are present)
- Full X11 support coming after TTY and Wayland versions are stable
- Limited vim keybindings in current version

## License
Copyright © 2026 Dialor "Dialorakc" Emma. This project is licensed under the PBL-2.0 License - see the [PBLv2 License](LICENSE) file for details.
Source code will be released under GPLv3 when v0.10 is reached.

## Contributing
Not accepting code contributions yet (since source code is not public), but i welcome:

- Bug reports
- Feature suggestions
- Documentation improvements
- Testing on different distributions

## Acknowledgments
Special thanks to:

- The vim community for inspiration
- Ncurses library developers
- Everyone testing and providing feedback

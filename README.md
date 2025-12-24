# Privie
Currently in beta. Source code will be released
under GPL License when v0.1 is reached.

     /\_/\
    ( o.o )  privie v0.02
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
    # Arch/Manjaro
    sudo pacman -S ncurses gcc-libs

    # Debian/Ubuntu
    sudo apt install libncurses6 libtinfo6 libstdc++6

    # Fedora
    sudo dnf install ncurses-libs libstdc++

    # Gentoo
    sudo emerge sys-libs/ncurses sys-devel/gcc
    ```

2. Installation
    ```
    git clone https://github.com/Dialorakc/Privie.git
    cd Privie
    chmod +x privie
    ./privie
    ```
    ```bash
    ## To install system-wide
    git clone https://github.com/Dialorakc/Privie.git
    cd Privie
    chmod +x privie
    sudo mv privie /usr/local/bin/vie

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

> [!NOTE]
> if [*] is already present, it has been enabled and you can skip this step.
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
> h, j, k, l (Navigation(left, down, up, right))
> d (Delete line)
> D (Delete to end of line)
> w, q (write and quit)
> t (open terminal mode)

### Command-Line Flags
```bash
vie [OPTIONS] <filename>

Options:
  -V, --version      Display version information
  -T, --terminal     Launch in terminal mode
```

## Testing & Feedback
This is beta software! Please report bugs and suggestions:

- Issues: [GitHub Issues](https://github.com/Dialorakc/privie-bin/issues)
- Discussions: [GitHub Discussions](https://github.com/Dialorakc/privie-bin/discussions)

## Known Limitations

- Mainly tested in TTY (framebuffer mode)
- Full X11 and Wayland support coming after TTY version is stable
- Limited vim keybindings in current version

## License
Copyright © 2025 Dialor "Dialorakc" Emma. This project is licensed under the Privie Beta License(PBL) - see the [PBL License](LICENSE) file for details.
Source code will be released under GPLv3 when v0.1 is reached.

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

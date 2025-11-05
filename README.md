# about-cross-compilation
some info related to cross-compilation

# linux
- develpoment
    - https://toolchains.bootlin.com/ you can download prebuild toolchains including very old ones (click "view all toolchains to see them")
    - zig https://ziglang.org can be used as cross-compilation toolchain and it DOES allow you to select preffered glibc version
- running
    - well I run linux on my hardware. 
# windows
- development
    - mingw package on ubuntu/debian/fedora/anywhere really
- running
    - wine
# macos
- development
    - https://github.com/tpoechtrager/osxcross
    - https://github.com/LcJuves/osx-cross-compiler
- running
    - https://www.darlinghq.org/
# android
- development
    - android studio
    - https://pypi.org/project/sdkmanager/
- running
    - I have cheap android device
    - emulator if your hadware is good enough
    - x86_64 android using waydroid or something similar
# ios
- development
    - https://github.com/xtool-org/xtool
- running
    - hard qemu setup (but I have weak pc)

# web
- development
    - emscripten
- running
    - browser

# gameboy
- development
    - https://github.com/gbdk-2020/gbdk-2020/
    - https://github.com/bandithedoge/devkitNix

# gameboy advance
- development
    - arm-none-eabi-gcc + libtonc https://github.com/gbadev-org/libtonc
    - https://github.com/bandithedoge/devkitNix

# nes (nintendo entertainment system)
- development
    - https://github.com/gbdk-2020/gbdk-2020/

# sega mega drive
- development
    - https://github.com/andwn/marsdev

# ps vita 
- development
    - sdk https://github.com/psvsdk/psvsdk


# dos
- development
    - open-watcom-v2  https://mynixos.com/nixpkgs/package/open-watcom-v2
        (or build it from source https://github.com/open-watcom/open-watcom-v2)
    - djgpp https://mynixos.com/nixpkgs/package/djgpp
        (origin https://www.delorie.com/djgpp/)
- running
    - dosbox-x
    - dosbox

# devkitpro 
can be installed by https://github.com/bandithedoge/devkitNix
supports following targets:
## 🕹️ Nintendo

- Game Boy Advance (GBA)
    
    - target: `arm-eabi`
    - toolchain: `devkitARM`
    
- Nintendo DS (NDS)
    
    - target: `arm-eabi` (dual-core ARM7/ARM9)
    - toolchain: `devkitARM`
    
- Nintendo 3DS
    
    - target: `arm-none-eabi` (ARM11 + ARM9)
    - toolchain: `devkitARM` + специфичные библиотеки (`libctru`)
    
- Nintendo Switch
    - target: `aarch64-none-elf`
    - toolchain: `devkitA64`
    - SDK: `libnx`

---

## 🎮 Sega

- Sega Dreamcast
    - target: `sh-elf` (SuperH SH-4)
    - toolchain: `devkitSH4`
    - SDK: `KallistiOS (KOS)`

---

## 🖥️ Sony

- PlayStation 2
    
    - target: `mipsel-none-elf`
    - toolchain: `devkitPS2`
    - SDK: `PS2SDK`
    
- PlayStation Portable (PSP)
    
    - target: `mipsel-none-elf`
    - toolchain: `devkitPSP`
    - SDK: `PSPSDK`
    
- PlayStation Vita
    - target: `arm-vita-eabi`
    - toolchain: `vitasdk`

# gbdk-2020
https://github.com/gbdk-2020/gbdk-2020/

Supported Consoles: [(see docs)](https://gbdk.org/docs/api/docs_supported_consoles.html)

- Nintendo Game Boy / Game Boy Color
- Analogue Pocket
- Sega Master System & Game Gear
- Mega Duck / Cougar Boy
- NES

# using zig for xmake cross-compilaiton with choosing glibc version
`xmake f -p cross --toolchain=zig --cross=x86_64-linux-gnu.2.22`
`xmake build`

# HyFetch

neofetch with pride flags <3

<img alt="screenshot" src="https://user-images.githubusercontent.com/22280294/197708447-ddee6db2-1017-48f2-b507-8ddf85acef0d.png">

### Running Updated Original Neofetch

This repo also serves as an updated version of the original `neofetch` since the upstream [dylanaraps/neofetch](https://github.com/dylanaraps/neofetch) isn't maintained anymore and has been archived. If you only want to use the updated neofetch without pride flags, you can use the `neofetch` script from this repo. To prevent command name conflict, I call it `neowofetch` :)

* Method 1: `pip install -U hyfetch` then run `neowofetch`
* Method 2: `npx neowofetch`
* Method 3: `P="$HOME/.local/bin/neowofetch" && curl -L nf.hydev.org -o "$P" && chmod +x "$P"`
* Method 4: Run without install `bash <(curl -sL nf.hydev.org)`


## Installation

### Method 1: Install using pip (Recommended)

Even though hyfetch has been rewritten in Rust since 2.0.0, we also published PyPI packages with prebuilt rust binaries to allow seamless transition from the Python version. You can install the rust binaries using pip:

```sh
pip install wheel
pip install -U hyfetch
```

If a rust binary is not available for your platform (e.g. riscv64), it will automatically fall back to the v1.99.0 Python version.

### Method 2: Install using system package manager

Currently, these distributions have existing packages for HyFetch:

* Universal [Lure.sh](https://lure.sh/): `lure in hyfetch` (Thanks to [@Elara6331](https://github.com/Elara6331))
* Arch Linux: `sudo pacman -S hyfetch` (Thanks to [@Aleksana](https://github.com/Aleksanaa) and [@Antiz96](https://github.com/Antiz96))
* Fedora Linux: `sudo dnf install hyfetch` (packaged by [@topazus](http://github.com/topazus))
* Nix: `nix-env -i hyfetch` (Thanks to [@YisuiDenghua](https://github.com/YisuiDenghua))
* Nix Profile: `nix profile install nixpkgs#hyfetch`
* Guix: `guix install hyfetch` (Thanks to [@WammKD](https://github.com/WammKD))
* Slackware: `sbopkg -b hyfetch` [Slackbuild](https://slackbuilds.org/repository/15.0/desktop/hyfetch/?search=hyfetch) (Thanks to [@bittin](https://github.com/bittin) , willysr (https://github.com/willysr), jebrhansen and Urchlay)
* Homebrew: `brew install hyfetch` (Thanks to [@catumin](https://github.com/catumin) and [@osalbahr](https://github.com/osalbahr))
* openSUSE Tumbleweed: `zypper in python311-hyfetch` (Thanks to [@catumin](https://github.com/catumin))
* Gentoo: `emerge --ask app-misc/hyfetch` (Thanks to [@catumin](https://github.com/catumin))
* Debian and Ubuntu `apt install hyfetch` (for Debian flavor >= [Trixie](https://packages.debian.org/trixie/hyfetch), Ubuntu flavor >= [Noble](https://packages.ubuntu.com/noble/hyfetch)) (Thanks to [@catumin](https://github.com/catumin))

[![Packaging status](https://repology.org/badge/vertical-allrepos/hyfetch.svg?columns=4&exclude_unsupported=1)](https://repology.org/project/hyfetch/versions)

### Method 3: Install using Cargo

Since hyfetch has been rewritten in Rust since 2.0.0, you can now install it using Cargo:

```sh
cargo install hyfetch
```

> [!WARNING]
> If you install using Cargo, you would need to manually install dependencies like fastfetch if you want to use it as the backend, and Git Bash if you're on Windows.
>
> The PyPI package has all the dependencies bundled, so it's recommended to use that instead.

## Usage

When you run `hyfetch` for the first time, it will prompt you to choose a color system and a preset. Just follow the prompt, and everything should work (hopefully). If something doesn't work, feel free to submit an issue!

If you want to use the updated `neofetch` without LGBTQ flags, check out [this section](https://github.com/hykilpikonna/hyfetch#running-updated-original-neofetch)


## Questions and answers

#### Q: How do I change my config?

A: Use `hyfetch -c`

#### Q: What do I do if the color is too dark/light for my theme?

A: You can try setting the colors' "lightness" in the configuration menu. The value should be between 0 and 1. For example, if you are using dark theme and the rainbow flag is too dark to display, you can set lightness to 0.7.

Feel free to experiment with it!

![image](https://user-images.githubusercontent.com/22280294/162614553-eb758e4e-1936-472c-8ca7-b601c696c6eb.png)

#### Q: Why do you use pride flag's coloring? I don't think it looks nice at all.

A: The core idea behind HyFetch coloring isn't just to make logos look nicer, it's about representation and identity. While it's okay to assess the visual appeal, you also need to understand that the LGBTQ+ flag colors serves a much deeper purpose than just aesthetics.

For many in the LGBTQ+ community, these flags symbolize their identity, struggles, and pride. Integrating these symbols into a showcase of the tech specs they share can provide a sense of empowerment. It's combining their enthusiasm for their favorite distro / hardware with their LGBTQ+ identity.

Also, by including flag coloring along with the updated neofetch, we're also broadcasting a wider message about the importance of inclusivity and representation. It's not just a design choice, it's a statement that promotes awareness and understanding toward the LGBTQ+ community.

#### Q: When I use `hyfetch` or `neowofetch` in my MotD, no art displays. How do I get the art back?

A: Most likely, the `stdout` detection is set to auto and is removing the ascii art and colors. To change this, you can: set `args` in your hyfetch.json to `"--stdout=off"`, add `--stdout=off` to the `neowofetch` command in your motd script, or set the option in $HOME/.config/(neofetch|neowofetch)/config.conf to off.

#### Q: How can I run HyFetch on Windows?

A: Install Python > 3.7 and Git > 2.42.0 first. Then, either open Git Bash terminal or install a terminal emulator that can display RGB colors (the default Windows cmd.exe cannot, but the new [Windows Terminal](https://apps.microsoft.com/detail/9N0DX20HK701?hl=en-US&gl=US) can). Then, run `pip install hyfetch` and run `hyfetch`.


## Contributing

To make changes to our codebase, you first need to create a fork by clicking the "Fork" button on the top right. Then, you can clone your fork of the source code using `git clone https://github.com/{your username}/hyfetch.git`.

After making changes to the source code, you can run `python -m hyfetch` in the root directory of your repo to test out your changes.

If they work correctly, you can commit and push these changes using git command or Github Desktop. Then, you can create a pull request on Github so that it can go into our next release!

You can also install your version locally by running `pip install .` in the repo root.


## Change Log

### About Notation

Updates to HyFetch begins with the emoji 🌈  
Updates to `neowofetch` begins with the emoji 🖼️

### TODO

* [ ] (Important!) Refactor flag storage & coloring to support non-stride patterns
* [ ] Config menu: Allow left-right arrow keys for pagination

### Nightly

Note: You can install the latest nightly version by using:

```sh
cargo install --git https://github.com/darkwolf1000/somefetch
```

<!-- CHANGELOG STARTS HERE --->

### 2.0.1

(changelog is generated by Gemini from commit history)

**🦀 The Rust Rewrite!**

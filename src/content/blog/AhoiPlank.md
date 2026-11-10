---
title: "AhoiPlank"
description: "Reinventing the Plank!"
pubDate: 2026-11-10
---

Last time I was writing about my `AhoiCpp` journey. This time, it is a public project I am crafting with it. I called it [AhoiPlank](https://github.com/martuscellifaria/AhoiPlank).

`AhoiPlank` is a launcher/runner for Wayland, written in C++ and Qt 6. I designed it to have its looks customizable, and try to keep it minimalistic in terms of code.

I know there is `rofi`, `wofi`, and a bunch of fancy alternatives written in fancy languages, but since none of these projects was done by me, let us reinvent the plank once more and see what happens.

My main goal is to test `AhoiCpp`'s capabilities of scaffolding Qt 6 projects. Also to refresh my Qt skills that were a bit rusty.

`AhoiPlank` integrates perfectly with Wayland compositors and tiling window managers such as `Sway` and `Hyprland`. I tested it on both x86_64 and aarch64 architectures, both on Arch and Ubuntu 26.04. The step by step from the repo worked for all builds.

Currently you can run it on standard mode, for launching .desktop applications, on bookmark mode, for loading your bookmarks and opening on your browser, and dotfiles mode, where you can browse through your configs and open them in a selected terminal-based editor (yes, no vscode!).

I plan to add more modes, like ssh, custom runners, and maybe a dock mode, but I this last I am not sure yet. Also improve the fuzzy finding to memorize last searches and so on.

There is a small roadmap in the repo, so next features will be there beforehand.

More than just free to test, please feel invited and welcomed to clone, compile, test and modify!

Alex

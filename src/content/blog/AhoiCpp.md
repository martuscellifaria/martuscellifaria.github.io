---
title: "AhoiCpp"
description: "My personal development environment for neovim"
pubDate: 2026-11-07
---

For a couple of years, I started learning neovim, and went full on tinkering my personal development environment.
Everything really great, keybindings are mastered, telescope for fuzzy finding, but there was an elephant in the room.

The elephant was: I program in C++ on my daily basis (I like the language a lot, and have been doing it for over a decade now).

Neovim is extreme extensible, there are plugins for every but language, from Javascript to Python, to Rust, to Zig, lintering, formatting, but then when it comes to C++, you can get some syntax highlighting and other stuff, clangd, clang-tidy. But what about the good stuff? Compiling with a key stroke? Creating new files, classes, automating CMake generation? Fetching external libraries from Git? Do I really need to do everything manually? Does it really require me to type `:q`, then `rm -rf build`, then `mkdir build && cd build && cmake .. && make`, then `nvim` once I tested my stuff? Although I use `tmux` to have multiple terminals, this was getting old. And what's the point? Neovim is so great, why would one want to leave it?

This went from questions to a mental roadmap. And from the mental roadmap I started getting into the plugin development. Time to learn another language. Fine, it is lua, we both come from Brazil. The language is fairly simple to hop along if you have already programmed some Python, Go, Ruby, some C-like language, or messed around with neovim configuration. This idea turned into Alex's Highly Opinionated Interfaces C++ Plugin, or [AhoiCpp](https://github.com/martuscellifaria/ahoicpp.nvim).

It is a personal project and a personal plugin, but it enables such a flow, that I started even adding things that I don't use at all on my work, such as support to `Qt6`, just for the sake of completeness.

I worked (and still work) on a legacy Windows ATL/MFC based project, so I have to use VisualStudio sometimes (and Tortoise SVN, if you would believe it). The way VisualStudio handles through the .sln and .vcproj files is such a nightmare, as well as when you create a class, it drops you an automatic violation of the rule of five, so the compiler will do whatever it wants to with your copies and moves. New class on a project in `AhoiCpp`? Alright, you press `<leader>cm`, pick a name and it is done for you. You get the rule of zero from the gecko and a commented out rule of five example to remember you to adding it. This is a small detail, but I think it is a neat one towards tackling some footguns.

Dependency management is also a known pain of C++. Run `<leader>ce` and fetch your external by just pasting the remote git from it.

My two most used keybindings are also `<leader>cpc` for compiling and `<leader>cpx` for executing the target binary on a terminal tab inside neovim. If some compiler error occurs, the usual 30000 lines of incomprehensible errors get stored on a build.log file, that pops on a tab and you can read it and take your time to find the actual errors.

I recently incorporated a Dockerfile to the project scaffolding with a `devcontainer`. This allows the user (if on Linux), to do cross compilation targeting Windows and Linux on x86_64 and aarch64.

A bunch of things to say about this, but these are the highlights for now. If you want to learn more about AhoiCpp, I recommend going to the repo and reading the README.md. Or even better, add the following to your neovim init.lua file:

```lua
{
	'martuscellifaria/ahoicpp.nvim',
	config = function()
	      require('ahoicpp').setup()
	end,
}
```

Thanks for reading,

Alex

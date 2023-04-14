<!-- PROJECT SHIELDS -->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]

<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/Magnushhoie/fuz">
  </a>
  <h1 align="center">
<picture>
  <img alt="Image Alt Text"  src="https://github.com/Magnushhoie/fuz/blob/main/img/logo.png?raw=true" width="250"/
</picture>
         ></h1>
  <p align="center">
    Fuzzy search your notes in the terminal. Ultra-fast incremental searching and editing using ripgrep and vim. Personally used for 4+ years.
  </p>
</p>

</p>
<p align="center">
<a href="https://asciinema.org/a/540480" target="_blank">
<img src="https://github.com/Magnushhoie/fuz/blob/main/img/fuz.gif?raw=true" width="500"/>
</a>
</p>

Why use Fuz?
- Point to a directory of text files
- Fuz instantly and interactively returns search matches (see above)
- Search results are opened directly in terminal (or preferred app)
- Supports markdown and code highlighting
- File contents are memory mapped for faster results
- Cleverly ignores large binary files and hidden directories
- Works well with Obsidian / Roam like note-taking apps, managing code snippets and project notes

## Installation and usage

```bash
# Download and install
git clone https://github.com/Magnushhoie/fuz/
cd fuz && chmod +x fuz

# Run setup and point to a directory you want to fuz
./fuz --setup

# Interactively search all files with fuz
fuz
```

## Requirements (pick one option)

```bash
# For MacOS, first install brew (https://brew.sh/) then run
brew install fzf rg bat

# Alternatively use conda: https://conda.io/docs/user-guide/install/
conda install -c conda-forge fzf ripgrep bat 

# On Ubuntu (requires sudo)
sudo apt-get install fzf ripgrep
sudo apt install bat
# Batcat should be aliased to bat to work with fuz
mkdir -p ~/.local/bin
ln -s /usr/bin/batcat ~/.local/bin/bat
```

- [fzf](https://github.com/junegunn/fzf)
- [ripgrep](https://github.com/BurntSushi/ripgrep)
- [bat](https://github.com/sharkdp/bat)

## Documentation

```
USAGE:
  fuz [options] <FILENAME or SEARCH-TERMS>

Fuz interactively fuzzy searches a directory and
opens selected files at search result.

Use --edit to list files and edit in vim,
or --open for system default app

Skips large (1M+) or binary files, and hidden directories including .gitignore
Default searches 5 directories down, follows symlinks and shows up to 50K lines per file.

Project homepage: https://github.com/Magnushhoie/fuz


EXAMPLES:
- Search file-contents, open with less:
    fuz

- Search filenames, edit (-e) with vim:
    fuz --edit

- Open search directory or file in system browser
    fuz --open


OPTIONS:
  --setup            Set fuz default search directory in .zsh/.bashrc
  -p, --path         Directory to search
  -o, --open         Open search directory or file with system default application
  -e, --edit         Open file with vim editor (instead of 'less'), enables --names option
  -n, --names        Only show filenames
  -c, --create       Create new file in search directory: --create <FILENAME>
  -d, --max-depth    Max search depth (5)
  -m, --max-lines    Max lines read per file (50000)
  -s, --max-size     Max file-size to search (1M)
  -f, --fuzzy-search Enable fuzzy instead of exact search
  --dir              Print search directory to terminal
  -h, --help         Print this help and exit
```

## Compatibility
Compatible with bash 3.2+ and zsh 5.9+. Tested on MacOS Mojave/Big Sur and Ubuntu 21.04.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/Magnushhoie/fuz.svg?style=for-the-badge
[contributors-url]: https://github.com/Magnushhoie/fuz/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/Magnushhoie/fuz.svg?style=for-the-badge
[forks-url]: https://github.com/Magnushhoie/fuz/network/members
[stars-shield]: https://img.shields.io/github/stars/Magnushhoie/fuz.svg?style=for-the-badge
[stars-url]: https://github.com/Magnushhoie/fuz/stargazers
[issues-shield]: https://img.shields.io/github/issues/Magnushhoie/fuz.svg?style=for-the-badge
[issues-url]: https://github.com/Magnushhoie/fuz/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/Magnushhoie/fuz/blob/master/LICENSE.txt

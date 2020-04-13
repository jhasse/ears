# ears [![Build Status](https://travis-ci.org/jhasse/ears.svg?branch=master)](https://travis-ci.org/jhasse/ears) [![Build status](https://ci.appveyor.com/api/projects/status/7s7wo0m97x70f3w6?svg=true)](https://ci.appveyor.com/project/jhasse/ears) [![](http://meritbadge.herokuapp.com/ears)](https://crates.io/crates/ears)


__ears__ is a simple library to play sounds and music in [Rust](https://www.rust-lang.org).

* Provides an access to the OpenAL spatialization functionality in a simple way.
* Accepts a lot of audio formats, thanks to libsndfile.

## Building

You need to install OpenAL and libsndfile on your system:

### Linux

Fedora:

```
sudo dnf install openal-soft-devel libsndfile-devel
```

Debian or Ubuntu:

```
sudo apt install libopenal-dev libsndfile1-dev
```

### Mac

```
brew install openal-soft libsndfile
```

### Windows

Install [MSYS2](http://www.msys2.org/) according to the instructions. Be sure to
use the default installation folder (i.e. `C:\msys32` or `C:\msys64`), otherwise
compiling won't work. Then, run the following in the MSYS2 shell:

```
pacman -S mingw-w64-x86_64-libsndfile mingw-w64-x86_64-openal
```

## Examples

```
cargo run --example basic
cargo run --example many_sounds
cargo run --example music
cargo run --example record
cargo run --example simple_player
```

## Functionality

__ears__ provides two ways to play audio files:

* The Sound class, which represents light sounds who can share a buffer of samples with another
  Sound.
* The Music class, which represents bigger sound and can't share sample buffers.

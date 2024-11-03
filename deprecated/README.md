
## homebrew-newt (DEPRECATED)

This Homebrew instance provides Apache `newt`, used to experiment with [mynewt](https://mynewt.apache.org/).

To run the install script:

```bash
$ caffeinate bash
$ exec bash "${HOME}/Downloads/opt-install-scripts.git/install-homebrew-newt.sh"
```

The alias to add these tools to the PATH is `newt`.

```bash
$ alias anewt='; export GOPATH=${HOME}/dev/go; export PATH=${HOME}/opt/homebrew/jekyll/bin:GOPATH/bin:${PATH}'
```

## homebrew-gme (DEPRECATED)

This Homebrew instance provides tools used during [GNU MCU Eclipse]((http://gnuarmeclipse.github.io)) binary tools builds, like [QEMU](http://gnuarmeclipse.github.io/qemu/), [OpenOCD](http://gnuarmeclipse.github.io/openocd/) and [Windows Build Tools](http://gnuarmeclipse.github.io/windows-build-tools/).

To run the install script:

```
$ caffeinate bash
$ exec bash ${HOME}/Downloads/opt-install-scripts.git/install-homebrew-gme.sh
```

The alias to add these tools to the PATH is `agme`.

```
$ alias agme='export PATH=${HOME}/opt/homebrew/gme/bin:${PATH}'
```

This formula is keg-only, which means it was not symlinked into /Users/ilg/opt/homebrew/gme,
because macOS provides the BSD gettext library & some software gets confused if both are in the library path.


## homebrew/gae (DEPRECATED)

This Homebrew instance provides tools used during [GNU ARM Eclipse]((http://gnuarmeclipse.github.io)) binary tools builds, like [QEMU](http://gnuarmeclipse.github.io/qemu/), [OpenOCD](http://gnuarmeclipse.github.io/openocd/) and [Windows Build Tools](http://gnuarmeclipse.github.io/windows-build-tools/).

To run the install script:

```bash
$ caffeinate bash
$ exec bash "${HOME}/Downloads/opt-install-scripts.git/install-homebrew-gae.sh"
```

The alias to add these tools to the PATH is `agae`.

```bash
$ alias agae='export PATH=${HOME}/opt/homebrew/gae/bin:${PATH}'
```

## homebrew/gcc

This Homebrew instance provides GCC 6 & GCC 7, used during µOS++ test builds.

To run the install script:

```console
$ caffeinate bash "${HOME}/opt/install-scripts.git/install-homebrew-gcc.sh"
```

The alias to add these tools to the PATH is `agcc`.

```console
$ alias agcc='export PATH=${HOME}/opt/homebrew/gcc/bin:${PATH}'
```

## homebrew/xbb (DEPRECATED)

It was moved to [xpack/xpack-build-box.git](https://github.com/xpack/xpack-build-box).

## texlive (DEPRECATED)

This is a local instance of [TeX Live](https://tug.org/texlive/), used to build the OpenOCD & QEMU manuals.

It generally includes the same packages as the MacTex distribution, and is **very large** (> 4.5 GB).

To run the install script:

```sh
ahb

caffeinate bash "${HOME}/Downloads/local-instal-scripts.git/install-texlive.sh"
chmod -R a-w "${HOME}/.local/texlive"
```

The alias to add these tools to the PATH is `atl`.

```sh
alias atl='export PATH=${HOME}/.local/texlive/bin/x86_64-darwin:${PATH}'
```

Notes:

- homebrew blacklisted TeX, (_"Installing TeX from source is weird and gross"_), but, apart from size and install time, there are no other problems
- however, due to its size, it is better to keep TeX separate from the Homebrew instances, which can now be reinstalled more easily
- the current script installs TeX Live 2016, the medium scheme (1015 packets)
- the GCC manuals fail with `-scheme basic` (! I can't find file `texinfo.tex'.)
- the OpenOCD manual passes with `-scheme basic`

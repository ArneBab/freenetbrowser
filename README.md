freenetbrowser - easy, secured Freenet opennet usage for *nix
======================================

Access content in Freenet with minimal fuss:
Installs Freenet if needed, creates a secured browser-profile
to minimize risk of leaking information.

See NEWS for user-visible changes.
See ChangeLog or the history for detailed changes.

## Usage

    ./freenetbrowser [--help | [options]] [url]"
    
    options:
        -i | --install      		install Freenet, if needed; replaces proxy setup (with backup) if FOLDER sset
        -d | --directory FOLDER		use FOLDER as Freenet FOLDER. Default: ~/Freenet
    
    examples:
    
    ./freenetbrowser http://127.0.0.1:8888/USK@.../foo/17
            open url http://127.0.0.1:8888/USK@.../foo/17
            with existing proxy settings; if there are none, create them for ~/Freenet
    ./freenetbrowser USK@.../foo/17
            open url http://freenet:local/USK@.../foo/17
            (you can also use SSK and CHK)
    ./freenetbrowser -i ~/FreenetFolder
            install freenet to ~/FreenetFolder
    ./freenetbrowser -d ~/FreenetFolder USK@.../foo/17
            open USK@.../foo/17 with proxy settings for ~/FreenetFolder

## Requirements

- curl
- wget
- gnupg for installing
- Java openjdk 9 or later
- icecat, waterfox or firefox

## Install

    $ ./bootstrap.sh && make install

To install only for the current user, use

    $ ./bootstrap.sh --prefix=$HOME/.local && make install

Also see

    $ make help

For details on installing a release, see INSTALL

## Contributors

See AUTHORS

Licensed under GPLv3 or later.

(this is the default of conf. To use a different license, replace
COPYING and the header in the main code file)

## Release Process

* Check/Update NEWS
* Increase version in configure.ac (see semver.org)
* Commit, merge to stable and tag (see branching[1])

Then do:

    $ ./bootstrap.sh && make distcheck

[1]: See do a release in
     http://www.draketo.de/branching-strategy#action-maintainer


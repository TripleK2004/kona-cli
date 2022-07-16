# Kona-CLI

This is a simple UNIX Shell Script (runs on korn shell), which uses the [Konachan API](https://konachan.com/help/api) to download wallpapers from the Konachan databse. Downloads sample wallpapers first and then downloads the full wallpaper in jpeg format to save bandwidth.

It has three main functionality:

1. Grab the latest posts. When ran for the first time downloads latest 21 posts. Once the latest wallpaper id has been cached, only newly uploaded wallpapers will be downloaded later on.

Usage: ```kona-cli gn``` gn for "get new"

2. Download the higher resolution jpeg image of the given 6 digit id. No sample image will be downloaded. Makes sense since you made the choice :)

Usage: ```kona-cli id  308134```

3. Download wallpapers based on query tags.

Usage: ```kona-cli se 5 yae_miko``` se for "search"

The first field takes number of sample wallpapers to view. The second field takes search string. Moebooru API, on which Konachan is based on uses underscore `(_)` separated names for tags with whitespaces. So better use underscores instead of whitespaces as shown in the example.

The wallpapers are downloaded to `$XDG_DATA_HOME/backgrounds` or `$HOME/.local/share/backgrounds`.

## Why Konachan ?

Konachan focuses on desktop anime wallpapers rather than other image boards (Danbooru/Gelbooru) which use any resolution images.


## Dependencies

* jq
* ksh
* curl
* [sxiv](https://github.com/bakkeby/sxiv-flexipatch.git)


## Credits

* [CoolnsX](https://github.com/CoolnsX)
    1. pointed out recurring code
    2. forking curl id caching into background improves speed

* [justchokingaround](https://github.com/justchokingaround)
    1. changes taken from the [commit](https://github.com/justchokingaround/kona-cli/commit/0c1ecca0480679fb054cb59d32ea25e6f8fc4a7d), removed redundant curling of latest id
    2. sed condition check #10, doesn't manipulate the json data when a full json is recieved

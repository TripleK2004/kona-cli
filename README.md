# Kona-CLI

This is a simple UNIX Shell Script (runs on korn shell), which uses the [Konachan API](https://konachan.com/help/api) to download wallpapers from the Konachan databse. Downloads sample wallpapers first and then downloads the full wallpaper in jpeg format to save bandwidth.

It has two main functionality:

1. Grab the latest posts. When ran for the first time downloads latest 21 posts (according to the api documentation). Once the latest wallpaper id has been cached, only newly uploaded wallpapers will be downloaded later on.

Usage: ```kona-cli gn``` gn for "get new"


2. Download wallpapers based on query tags.

Usage: ```kona-cli se 5 yae_miko``` se for "search"

The first field takes number of sample wallpapers to view. The second field takes search string. Moebooru API, on which Konachan is based on uses underscore `(_)` separated names for tags with whitespaces. So better use underscores instead of whitespaces as shown in the example.


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
    2. forking curl id caching (line 12) into background improves speed

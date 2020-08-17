# youtube-album

Downloads a video from Youtube and splits tracks based on a tracklist. It'll also try to save ID3 Tags.

The next iteration of [2trax](https://github.com/lvm/2trax) but rewritten and simplified.

## Usage

```
usage: youtube-album [-h] [-o OUTPUT_DIRECTORY] [-t TRACKLIST] [-i] [-vt] [-bt] [-k] [-V] video

positional arguments:
  video                 Use this audio as source

optional arguments:
  -h, --help            show this help message and exit
  -o OUTPUT_DIRECTORY, --output-directory OUTPUT_DIRECTORY
                        Save the audio files in this directory. Default: /home/mauro/Music
  -t TRACKLIST, --tracklist TRACKLIST
                        Use this file to cut the audio
  -i, --info            Don't download just get the info
  -vt, --verify-tracklist
                        Verify a Tracklist format
  -bt, --build-tracklist
                        Build a Tracklist format from a tracklist (?) From: 1. Song 1 04:03 2. Song 2 04:09 ... To: 1. Song 1 04:03 2. Song 2 08:12 ...
  -k, --keep-original   Keep original (non-sliced) mp3
  -V, --verbose         Show stdout messages
```

Download the album to the default directory

```
$ youtube-album https://www.youtube.com/watch?v=UlFNy9iWrpE
```


Download the album to the default directory using only the Youtube Video ID.

```
$ youtube-album UlFNy9iWrpE
```

Download the album to the default directory using only the Youtube Video ID and keep the unsliced MP3

```
$ youtube-album UlFNy9iWrpE -k
```

Download the album to a  given directory

```
$ youtube-album https://www.youtube.com/watch?v=UlFNy9iWrpE -o /path/to/music
```

Download the album to a given directory using a given tracklist

```
$ youtube-album https://www.youtube.com/watch?v=UlFNy9iWrpE -o /path/to/music -t my-fav-things.txt
```

Download the album to a given directory using a "song list" that needs to be "built" (See **Building a slice-able tracklist**)

```
$ youtube-album https://www.youtube.com/watch?v=UlFNy9iWrpE -o /path/to/music -bt -t my-fav-things.txt
```

Verify the tracklist format. This won't download anything, but print a list with the contents of the tracklist.

```
$ youtube-album https://www.youtube.com/watch?v=UlFNy9iWrpE -vt -t my-fav-things.txt
```

Just get JSON info about the video.

```
$ youtube-album https://www.youtube.com/watch?v=UlFNy9iWrpE -i
```

### Tracklist formats

Youtube (these days) uses something called "chapters" which splits the video in small chunks (ie: Chapters), this script will use that in case you don't specify a `tracklist file`. But if you still want to define a `tracklist file` or if the Video doesn't has a "tracklist", some of the formats allowed are:

* `<track no>. <time> - <track name>`
* `<track no>.<track name> <time>`
* `<track no>. <track name> <time>`
* `<track no>. <track name> - <time>`
* `<time> <track>`
* `<time> - <track name>`
* `<time> <track no>) <track>`
* `<time> <track no>. <track>`
* `<time> <track no>.<track name>`

### Building a slice-able tracklist

Sometimes there isn't a tracklist available but there's a _song list_ with their respective length. Here's an example:

> From the album "Hypnotic Blood Art" by "Prosanctus Inferi"

```
1. Dark Scarp of Hell 04:53
2. Pulpit Sycophants 04:09
3. Sheol Below 04:05
4. Hypnotic Blood Art 04:33
5. Blood Synod 04:05
6. Torture Enraped 04:28
7. Bellicose Spiritual Violence 05:05
8. Void Called as Black Bonds 03:45
9. Geist Enthralled 04:14
10. Washed in the Blood 03:31
11. The Fearful Pit 04:24
```


## Dependencies

* https://pypi.org/project/youtube_dl/
* https://pypi.org/project/eyeD3/ [optional]

## LICENSE 

See [LICENSE](LICENSE)

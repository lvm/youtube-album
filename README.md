# youtube-album

Downloads a video from Youtube and splits tracks based on a tracklist.

The next iteration of [2trax](https://github.com/lvm/2trax) but rewritten and simplified.

## Usage

```
usage: youtube-album [-h] [-o OUTPUT_DIRECTORY] [-t TRACKLIST] [-vt] [-V] video

positional arguments:
  video                 Use this audio as source

optional arguments:
  -h, --help            show this help message and exit
  -o OUTPUT_DIRECTORY, --output-directory OUTPUT_DIRECTORY
                        Save the audio files in this directory. Default: ~/Music
  -t TRACKLIST, --tracklist TRACKLIST
                        Use this file to cut the audio
  -vt, --verify-tracklist
                        Verify a Tracklist format
  -V, --verbose         Show stdout messages

```

Download the album to the default directory

```
$ youtube-album https://www.youtube.com/watch?v=UlFNy9iWrpE
```

Download the album to a  given directory

```
$ youtube-album https://www.youtube.com/watch?v=UlFNy9iWrpE -o /path/to/music
```

Download the album to a given directory using a given tracklist

```
$ youtube-album https://www.youtube.com/watch?v=UlFNy9iWrpE -o /path/to/music -t my-fav-things.txt
```

Verify the tracklist format. This won't download anything, but print a list with the contents of the tracklist.

```
$ youtube-album https://www.youtube.com/watch?v=UlFNy9iWrpE -vt -t my-fav-things.txt
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

## Dependencies

https://pypi.org/project/youtube_dl/

## LICENSE 

See [LICENSE](LICENSE)

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

## LICENSE 

See [LICENSE](LICENSE)

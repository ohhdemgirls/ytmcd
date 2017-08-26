# ytmcd
YouTube Music Channel Downloader.

Basically a sensible selection of youtube-dl flags to download music from music channels in bulk!

If you are using this for yourself, feel free to ignore file `downloaded` as that is for my own personal record, and be sure to edit `channels` to your own preferences.


### Remarks

Refer to the man pages for my `youtube-dl` flag choices, but here are some points worth mentioning:

* `--download-archive downloaded`: sucessful downloads will have their video ids listed here, which `youtube-dl` will ignore in subsequent runs
* `--geo-bypass`: useful for a lot of the Asian songs (thanks SONY Japan...)
* `--max-filesize 128m`: Usually amounts to 2.5 hour files with the current audio quality settings; fits most reasonable-length music mixes and avoids annoying 10-hour novelty videos
* `--add-metadata`: Writes the video title to ID3 title and the channel name to ID3 artist, in the case of MP3 files

And for some general Q/A (please correct me if I am wrong via issue or PR):

##### Why high-quality MP3 when you can get the FLAC audio?

* FLAC metadata tagging (vorbis format) is weird, ID3 on MP3 is much more common and established
* I personally don't have terabytes on terabytes of storage space
* The transcoding overhead (`youtube-dl` appears to encode FLAC from the downloaded webm audio much faster, MP3 is slower as it is a lossy compression format) acts as a great time buffer so as to not get rate-limited or ip blocked 
* I don't have super sensitive ears; MP3 at high bitrates is good enough for me in most cases, though I do download my favorite songs as FLAC

##### Why not download the native youtube MP4 AAC audio instead of transcoding from lossy to lossy (MP3)?

AFAIK and to my own experience, `--add-metadata` does not currently work with `--audio-format aac` (the tags are left empty if you read `ytmcd`-ripped AAC files with a universal tag reader like `kid3`). Metadata tags are very important to me, though if this is not the case for you, it is an easy script modification. 

##### Why no `--restrict-filenames`?

* I download lots of East Asian music and prefer to keep the original titles
* My terminal can handle unicode


### Channels

These are the channels I currently back up for myself.

In no particular order:

```
UCKioNqOX_kOCLcSIWPL_lxQ - Aviencloud
UCtkSwwONNeMC3C2aHxGeFmA - Inspira
UCJWQkiBMWCmr3BbZolEmgXw - Shinico
UC6hBefyLMtG7FXhZ55da3Vw - Artzie Music
UCUHhoftNnYfmFp1jvSavB-Q - Funky Panda™
UCIKF1msqN7lW9gplsifOPkQ - GalaxyMusic
UCYTNxR2Z4ryz88WRWiaPCdg - K - Music Sweet
UCZ7368uifluuE3Xh-XrqlWQ - Leafy Radio
UCJ6td3C9QlPO9O_J5dF4ZzA - Monstercat
UC_aEa8K-EOJ3D6gOs7HcyNg - NoCopyrightSounds
UCl4UOc8h1ZnO-inFPgAu7gw - NXS
UC3ifTl5zKiCAhHIBQYcaTeg - Proximity
UCcoYD5HDg8P-gvJU-oDYq5Q - StrobeNetwork Records
UCsPOjxg79gnqBmpUY38t_3g - VoicedOut
UC-wNjNTqCfXSKd4S1tNgWUg - Waifu Wednesdays
UCRs41MXZpAhXgiD4KjTjabg - Xefox Music
UCMOgdURr7d8pOVlc-alkfRg - xKito Music
UC7tD6Ifrwbiy-BoaAHEinmQ - Diversity
UC5nc_ZtjKW1htCVZVRxlQAQ - MrSuicideSheep
UCbKJXEbKdmiJO0tQzb1SmRg - Wejustman Music
UCvOGElQWhX8tyTxwzv1rKzg - ENM
UCKP5rY3Kr5FBZY13LzF-gpw - Universe Music
UCbfMTDftQhRySQKFCV8PfHg - GalaxyMusicNet
UCSa8IUd1uEjlREMa21I3ZPQ - CloudKid
UCM9KEEuzacwVlkt9JfJad7g - Chill Nation
UCa10nxShhzNrCE1o2ZOPztg - Trap Nation
UC8QfB1wbfrNwNFHQxfyNJsw - Rap Nation
UCFZ75Bg73NJnJgmeUX9l62g - Selected
UCgMyPaCx5-LkEx_54Ul9f-A - Futurism
UCK9Rngx643faIs9b4jxHQHw - Grizzly Music
UCSXm6c-n6lsjtyjvdD0bFVw - Liquicity
```

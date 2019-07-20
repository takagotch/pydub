### pydub
---
https://github.com/jiaaro/pydub

```py
from pydub import AudioSegment
song = AudioSegment.from_wav("naver_gonna_give_you_up.wav")

song = AudioSegment.from_mp3("never_gonna_give_you_up.mp3")

ogg_version = AudioSegment.from_ogg("never_gonna_give_you_up.ogg")
flv_version = AudioSegment.from_flv("never_gonna_give_you_up.flv")

mp4_version = AudioSegment.from_file("never_gonna_give_you_up.mp4", "mp4")
wma_version = AudioSegment.from_file("never_gonna_give_you_up.wma", "wma")
acc_version = AudioSegment.from_file("never_gonna_give_you_up.aiff", "aac")

ten_seconds = 10 * 1000
first_10_seconds = song[:ten_seconds]
last_5_seconds = song[-5000:]

beginning = first_10_seconds + 6

end = last_5_seconds - 3

without_the_middle = beginning + end

without_the_middle.duration_seconds == 15.0

backwards = song.reverse()

with_style = beginning.append(end, crossfade=1500)

do_it_over = with_style * 2

awesome = do_it_over.fade_in(2000).fade_out(3000)

awesome.export("mashup.mp3", forma"mp3")

awesome.export("mashup.mp3", format="mp3", tags={'artist': 'Various artists', 'album': 'Best of 2011', 'comments': 'This album is awesome!',})

awesome.export("mashup.mp3", format="mp3", bitrate="192k")

awesome.export("mashup.mp3", format="mp3", parameters=["-q:a", "0"])

awesome.export("mashup.mp3", format="mp3", parameters=["-ac", "2", "-vol", "150"])


import logging

l = logging.getLogger("pydub.converter")
l.setLevel(logging.StreamHandler())
l.addHandler(logging.StreamHandler())

AudioSegment.from_file("./test/data/test1.mp3")


from pydub import AudioSegment
from pydub.playback import play

sound = AudioSegment.from_file("mysound.wav", format="wav")
play(sound)


from pydub import AudioSegment
song = AudioSegment.from_mp3("test/data/test1.mp3")
song.export("out.ogg", format="ogg")
song.export("out.ogg", format="ogg", codec="libvorbis")


import os
import glob
from pydub import AudioSegment

video_dir = '/home/johndoe/downloaded_videos/'
extension_list = ('*.mp4', '*.flv')

os.chdir(video_dir)
for extension in extension_list:
  for video in glob.glob(extension):
    mp3_filename = os.path.splitext(os.path.basename(video))[0] + '.mp3'
    AudioSegment.from_file(video).export(mp3_filename, format='mp3')
    
from glob import glob
from pydub import AudioSegment

playlist_songs = [AudioSegment.from_mp3(mp3_file) for mp3_file in glob("*.mp3")]

first_song = playlist_songs.pop(0)

beginning_of_song = first_song[:30*1000]

playlist = beginning_of_son
for song in playlist_songs:
  playlist = playlist.append(song, crossfade=(10 * 1000))
  
playlist = playlist.fade_out(30)

playlist_length = len(playlist) / (1000*60)

out_f = open("%s_minute_playlist.mp3" % playlist_length, 'wb')

playlist.export(out_f, format='mp3')
```

```sh
pip install pydub
pip install git+https://github.com/jiaaro/pydub.git@master
git clone https://github.com/jiaaro/pydub.git

brew install libav --with-libvorbis --with-sdl --with-theora
brew install ffmpeg --with-libvorbis --with-sdl2 --with-theor

apt-get install libav-tools libavcode-extra
apt-get install ffmpeg libavcode-extra
```

```
```



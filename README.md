# exportMP4

## Add plugins

Edit > plugins > add Movie Render Queue

![image](https://github.com/marcelpatrick/exportMP4/assets/12215115/a78ccb1c-8397-48f2-af10-761683405bfe)

## Download Ffmpeg serializer

ffmpeg.org > download > add to a local folder

Edit > project settings > Movie Pipeline CLI Encoder > Executable Path > Pass the file location 

## 1- Aggregate audio files and Extract 

Edit > project settings > Movie Pipeline CLI Encoder > Command Line Format > Pass audio inputs as CLI arguments (Pass all your audio files as -i)

You gotta pass the file location in your local machine as input argument

```
-y -i "C:\Users\conta\OneDrive\Documents\UnrealProjects\CitySample_5_0\Content\Audio\mySounds\earth-rumble-6953.wav" -c:v libx264 -crf 20 -pix_fmt yuv420p -c:a aac -b:a 192k "C:\Users\conta\OneDrive\Documents\UnrealProjects\CitySample_5_0\Saved\MovieRenders\myAudio2.wav"
```

```
-y -i "C:\Users\conta\OneDrive\Documents\UnrealProjects\CitySample_5_0\Content\Audio\myMusic\Dark_Choir_Music_MATTIA_CUPELLI_royalty_free.wav" -i "C:\Users\conta\OneDrive\Documents\UnrealProjects\CitySample_5_0\Content\Audio\mySounds\earth-rumble-6953.wav" -i "C:\Users\conta\OneDrive\Documents\UnrealProjects\CitySample_5_0\Content\Audio\myDialogs\D_WhoeverBelieves_wav.wav" -i "C:\Users\conta\OneDrive\Documents\UnrealProjects\CitySample_5_0\Content\Audio\myDialogs\D_ThisToken_wav.wav" -i "C:\Users\conta\OneDrive\Documents\UnrealProjects\CitySample_5_0\Content\Audio\myDialogs\D_Sacrifice_wav.wav" -i "C:\Users\conta\OneDrive\Documents\UnrealProjects\CitySample_5_0\Content\Audio\myDialogs\D_Offerings_wav.wav" -i "C:\Users\conta\OneDrive\Documents\UnrealProjects\CitySample_5_0\Content\Audio\myDialogs\D_NewToken_wav.wav" -i "C:\Users\conta\OneDrive\Documents\UnrealProjects\CitySample_5_0\Content\Audio\myDialogs\D_ButFirst_wav.wav" -i "C:\Users\conta\OneDrive\Documents\UnrealProjects\CitySample_5_0\Content\Audio\myDialogs\D_Behold_wav.wav" -i "C:\Users\conta\OneDrive\Documents\UnrealProjects\CitySample_5_0\Content\Audio\myDialogs\D_and_Sacrifice_2.wav" -i "C:\Users\conta\OneDrive\Documents\UnrealProjects\CitySample_5_0\Content\Audio\myDialogs\D_AllYouNeedToDo_wav.wav" -i "C:\Users\conta\OneDrive\Documents\UnrealProjects\CitySample_5_0\Content\Audio\myDialogs\And_sacrifice.wav" -c:v libx264 -crf 20 -pix_fmt yuv420p -c:a aac -b:a 192k "C:\Users\conta\OneDrive\Documents\UnrealProjects\CitySample_5_0\Saved\MovieRenders\myAudio2.wav"
```

Sequencer > Movie Render Queue > Settings > + Setting > Exports > Add .wav > exclude all the others > Accept > select your shots > Render local

## 2- Extract video

Edit > project settings > Movie Pipeline CLI Encoder > Command Line Format > Pass your audio and all jpeg frames as input

# Overview TODO
- [X] Solve clue on old *Monsters* Interface 
- [ ]
# PHASE I
Twitter user @lost_boy84 [posted](https://twitter.com/lost_boy84/status/1531346528782237702) a burning heart emoji, the first tweet since 2020

Users viewed [website](https://183010165.com/) previously used for ARG.

It had been updated, showing a Unix interface. 

![Updated home page](monsters_home_1.jpg)

A clue was provided
##

>https://183010165.com/mdnght/I'm at the centre of your blue heart. A drink will kill me. What am I? mp4-include InRelease


Anwer is fire. The solution was to add 'fire.mp4' to the clue URL (clueRL?)
>https://183010165/mdnght/fire.mp4

<figure class="video_container">
    <iframe src="fire.mp4" frameborder="0" allowfullscreen="true"></iframe>
</figure>

note: Is now at `https://183010165.com/fire.mp4`
### FIRE.MP4 ###
Opening fire.mp4 in a text editor reveals information
* Was made in After Effects on March 15th
* Audio is `01_Golden Gate (Instrumental)_24bit_96kHz_Final_Master_3.18.22_LS_Edit.wav`
* There is an image `heroes-bg-notext.png` used in the creation
* _possibly Heroes is name of song_

# Phase II - June 1 2022 #
Old website has an update available. Running the command takes you to
`comtek.life`
Several things of note here
* Main gif is titled gifshuffle_talian_holds_the_key.gif
* Clicking presave gives long string
* Fire video moved
## Gif
* Opening in text editor reveals base image of `The Midnight Logo White.png`
* The name relates to Discord user Talian, who discovered the metadata of fire.mp4 in Phase I
* The file name hints at using gifshuffle
* running `gifshuffle -C -p "heroes-bg-notext.png" gifshuffle_talian_holds_the_key.gif` reveals a hidden message ~`/heroes/48-65-61-72-74-62-65-61-74.png`
* Appending this to the comtek.life website gives an image
# 48-65-61-72-74-62-65-61-74.png
* The name is a hexademical string for 'heartbeat'
* Inverting the colours, and rotating, reveals the text in the image as 'heartbeat'
* Running the image through openstego with password 'Heartbeat' reveals full resolution image, `Heartbeat.jpg`
## String
* Reversing the text made it decodable in base64
* Decoding it provided lyrics, presumably for song 'Heartbeat'
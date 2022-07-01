# Overview
## Solved
- [x] [Solve riddle on old *Monsters* Interface](#first-riddle) 
- [x] [Find metadata of Fire.mp4](#firemp4)
- [x] [Extract message from gifshuffle_talia_holds_the_key.gif](#main-gif)
- [x] [Extract image from 48-65-61-72-74-62-65-61-74.png](#decyphering-image)
- [x] [Decrypt console output to view song lyrics](#presave-link)

## Unsolved
- [ ] Significance of 05.08.2022 (August 5th) mentioned in MONSTERS OS page
- [ ] Significance of 06.07.2022 (July 6th) mentioned in Comtek.Life update
- [ ] What cipher/key is needed to decode [avalanche_intro.enc](#avalanche_intro.enc)
# PHASE I
Twitter user @lost_boy84 [posted](https://twitter.com/lost_boy84/status/1531346528782237702) a burning heart emoji, the first tweet since 2020

Users viewed [website](https://183010165.com/) previously used for ARG.

It had been updated, showing a Unix interface. The interface needed a specific update command to be entered to get the right output. 

![Original home screen](monsters_first_home.jpg)

`sudo apt full-upgrade -y`

This command runs an update package that provides an error message

![Updated home page](monsters_home_1.jpg)

A riddle was provided
## First Riddle
One of the final lines of the page was a riddle

>https://183010165.com/mdnght/I'm at the centre of your blue heart. A drink will kill me. What am I? mp4-include InRelease

There are two clues to the answer here

> I'm at the centre of your blue heart

Refers to the Change Your Heart Or Die vinyl record, which is blue, and has the word 'fire' etched into the center

![CYHOD Vinyl Center](heart_fire.jpg)

*Image courtesy of Discord user cpsedmonds*

>A drink will kill me. What am I?

Is an old riddle. Adding water to fire will kill it, giving the answer 'fire' again.



The solution was to add 'fire.mp4' to the clue URL (clueRL?)
>https://183010165/mdnght/fire.mp4

<video src="https://user-images.githubusercontent.com/6541033/171990189-6d677f2d-d14c-4028-9516-c934fd6151bc.mp4" controls>
</video>

note: Is now at https://183010165.com/fire.mp4, not clear why it was moved

## fire.MP4
Opening fire.mp4 in a text editor reveals metadata (information about the file)
* Audio is `01_Golden Gate (Instrumental)_24bit_96kHz_Final_Master_3.18.22_LS_Edit.wav`
*  `heroes-bg-notext.png` is referenced

![Fire.mp4 metadata](fire_metadata.jpg)

Golden Gate is a [song](https://www.youtube.com/watch?v=1UXLyW6N9LQ) by Tyler Lyle, and the audio in the video sounds like a synth cover of that. The Midnight has covered Lyles music before, with Brooklyn ([Lyle](https://www.youtube.com/watch?v=tg3YLGiDG9M), [The Midnight](https://www.youtube.com/watch?v=8Ey30-sYvuU)) and Lost & Found ([Lyle](https://www.youtube.com/watch?v=ZHhZPomMNlo), [The Midnight](https://www.youtube.com/watch?v=vDNG5AkNfcs)). The cover of Golden Gate* was included as a secret track in the *Change Your Heart Or Die* [vinyl release](https://www.reddit.com/r/TheMidnight/comments/utuvmq/not_sure_if_this_is_common_knowledge_yet_but/)

heroes-bg-notext.png is not a known reference like this, but is suspected to be named in designer shorthand for the background art (bg) of the next album (Heroes, not confirmed), and might be important

# Phase II - June 1 2022 
The old website has an update available, and the text has changed slightly from 'New Release' to 'Hot Fix'

![Monsters page prompting to run update](monsters_update.jpg)

This is a [unix command](https://www.freecodecamp.org/news/sudo-apt-get-update-vs-upgrade-what-is-the-difference/) used to upgrade packages on a system

Running the command takes you to [a new website](comtek.life) advertising an unknown upcoming release by The Midnight

![Comtek Life homepage](comtek_home.jpg)

Several things were found in here
## Comtek Homepage Info
### Main Gif
The gif on the page is seen glitching stylistically
![Glitching Gif](gifshuffle_talian_holds_the_key.gif)

Using the 'inspect element' feature of the browser, the name of this gif can be seen as `gifshuffle_talian_holds_the_key.gif`

![Gif in inspect element](gif_name.jpg)

Talian here is a reference to Discord user Talian, who was the first to find the metadata in fire.mp4 and alert the chat. The team behind the ARG are known to monitor the Discord, explaining the inclusion of this.

![Talian finds the metadata](talian_discord_message.jpg)

Gifshuffle is the name of a command line utility, included in Ubuntu (more info [here](http://manpages.ubuntu.com/manpages/bionic/man1/gifshuffle.1.html)). Gifshuffle is used to hide messages in gif files, and the inclusion of it in the name here suggests it needs to be used to extract the message.

Part of the metadata is 'heroes-bg-notext.png', which seems unrelated to anything seen so far.

Running the command
`gifshuffle -C -p "heroes-bg-notext.png" gifshuffle_talian_holds_the_key.gif` (you need to download the file from the website, then run this command in the same directory as where it is saved) reveals the hidden message
>/heroes/48-65-61-72-74-62-65-61-74.png

Adding this to the comtek.life [URL](comtek.life//heroes/48-65-61-72-74-62-65-61-74.png) provides you with an image

<img src="48-65-61-72-74-62-65-61-74.png" height="250px" width="250px"></img>

### Decyphering Image
By inverting the colours on this image and rotating 180 degrees, it becomes slightly more legible, and 'heart beat' can be slightly made out

<img src="48-65-61-72-74-62-65-61-74_inverted.png"  height="250px" width="250px"></img>

The name, 48-65-61-72-74-62-65-61-74, is also a hexadecmial string that translates to 'heartbeat'. This decoding can be done using online [tools](http://www.unit-conversion.info/texttools/hexadecimal/).

![Decoding the hex](hex_decode.jpg)

The LostBoy account tweeted a hint that something was yet to be discovered

![LostBoy hint](lostboy_lookCloser.jpg)

Tyler Lyle tweeted a clue out to assist in the next step of this clue

![Tyler Tweeting](tyler_clue.jpg)

The use of 'stego' here is a hint at 'steganography', the process of hiding content within other content, much like the Gifshuffle tool earlier. 

[OpenStego](https://www.openstego.com/) is a free tool available to extract data hidden in images, but it needs a password. The text in the image, as well as the filename, are both 'heartbeat' which is worth trying

![Using openStego](openstego.jpg)


This succeeds, and reveals the hidden image; a full resolution copy of the 'Heartbeat' image. This will be saved to the output folder, the desktop in this case.

<img src="Heartbeat.jpg" height="250px" width="250px"></img>

LostBoy then replies to their earlier tweet, confirming this was solved

![LostBoy confirmation](lostboy_nowYouSee.jpg)

### Presave Link
By clicking the Presave bar in the middle of the screen, a long string is output to the browser console. This can be viewed through inspect element
![Console Output](console_output.jpg)

The text of this is
> l1GIk5WYgU3b5BicvZkCgKManV3buVGIlZ3bsBycpBSZyVGaUpAoCfmbp92ZgAXZltGI0NXdKpAoCTXZ5BSZu9GZgQ3buBSZylJgiX3bZpAoCTXYlJGdyFWZoBic19WegwWZlZGIuF2YgU3b5BiZJpgCl1GIk5WYgU3b5BicvZkCgKManV3buVGIlZ3bsBycpBSZyVGaUpAoCfmbptmcvdHIzlJgiTXagwyc0JXdoBCdpBiZJpAoCXmYgQXmAKubhNGI19WWKAqw0VWegUmbvRGI09mbgUmcZCo419WWKQXYlJGdyFWZoBic19WegwWZlZGIuF2YgU3b5BiZJpgCgK8ajFmYg82ZgQXmAKubhNGIldHIlNXdhNGmAKOIn5WavdGIwVWZLpwajFmYg82ZgQXmAKubhNGIldHIlNXdhNGmAKOIn5WavdGIwVWZLpwajFmYg82ZgQXmAKubhNGIldHIlNXdhNGmAKOIn5WavdGIwVWZLpgCodWdv5WZgUmdvxGIzlGIlJXZoRlCgKMZlVmbgIXdvlHIn5WayJGIk5WYgUWbvNEIk92bsZGIlhGdgMHduF2dgQXYoRHI0JXYlhGI0JXZzVGZgknclZXRKAqwuV3cgEGI0NXZndWdzByc39GZhh2cgIXdvBCbsFkCgKMLzVHIm9GI0V3bgUGZh1GIzlGIkxmcvdHIlhGdgYWSKoQZtBCZuFGI19WegI3bGpAoCj2Z19mblBSZ29GbgMXagUmclhGVKAqwn5WavdGIwVWZrBCdzVnSKAqw0VWegUmbvRGI09mbgUmcZCo419WWKAqw0FWZiRnchVGagIXdvlHIsVWZmBibhNGI19WegYWSKoQZtBCZuFGI19WegI3bGpAoCj2Z19mblBSZ29GbgMXagUmclhGVKAqwn5WarJ3b3BycZCo40lGIsMHdyVHagQXagYWSKAqwlJGI0lJgi7WYjBSdvllCgKMdllHIl52bkBCdv5GIlJXmAKedvllCgKMdhVmY0JXYlhGIyV3b5BCblVmZg4WYjBSdvlHImlkCKAqwlRWayBSYgY2bgwGblhGIhBCbslGdzBycpBib39GZgcmbp12bDpAoCnXY3BiclhGdpVkCgKcesZGIuF2YgkXZoRHIlZXZpxWZiBycs92bGpwcl1Wa0VWbvNHI5F2dhByasF2dg8GdgMHduF2dgkHZvJWeyVmdFpgCgKManV3buVGIlZ3bsBycpBSZyVGa0BSZtByb0BiZv9mcwBSZoRHIlJXmAKedvllCwV3YgIXdvlHIkVmchh2cgU3b5Biblh2dgQWYlRGI5xmchVmbgMXY3BSSKAqwl52b55WYg4WagU2ZuFGajBibhNGI0JXYlhGIhBiblhGVKAqwlZ3bsBiZvBCd19GIlRWYtBycpBCZsJ3b3BSZoRHImlkCKAqwl1GIk5WYgU3b5BicvZkCgKManV3buVGIlZ3bsBycpBSZyVGaUpAoCfmbptmcvdHIzlJgiTXagwyc0JXdoBCdpBiZJpAoCXmYgQXmAKubhNGI19WWKAqw0VWegUmbvRGI09mbgUmcZCo419WWKAqw0FWZiRnchVGagIXdvlHIsVWZmBibhNGI19WegYWSKoQZklmcgEGIm9GIsxWZoBSYgwGbpR3cgMXag42dvRGIn5Wat92QKAqwskXY3BiclhGdpVkC5xmZg4WYjBSelhGdgUmdllGblJGIl12bTpwcl1Wa0VWbvNHI5F2dhByasF2dg8GdgMHduF2dgkHZvJWeyVmdFpgCgKManV3buVGIlZ3bsBycpBSZyVGa0BCd19GIuVncgQXmAKubvdHI19WWKAXdgUWbgU2c1BibhNGI19WegkHdw1WZgUmcZCo419Weg4WZodlCl52bkBCdZCo4uNXagQXagQXYoRHIm92byBHIzlGIulWYwBSZoRHIuVGaUpAoCXmdvxGIm9GI0V3bgUGZh1GIzlGIkxmcvdHIlhGdgYWS

This text can be reversed, and decoded as Base64 ([online tools](https://www.base64decode.org/) can do this)

Decoding the text reveals song lyrics

>If the world is made out of love\
>Then the pain is proof that it isn’t done\
>When you’re empty you can use me up\
>You won’t run out there is love enough

>Everybody wants to walk away sometimes\
>Some believe they can fly\
>Either way,\
>Coming down is still a hell of a ride

>If you can feel your heartbeat\
>You’re not done yet\
>You can’t be\
>If it hurts, it’s working\
>There is love enough\
>For you and me

>If the world is made out of love\
>Then a heart can change in anyone\
>I was nearly dead when you shared your cup\
>You’re the proof to me there is love enough

>Everybody wants to walk away sometimes\
>Fools believe they can fly\
>Either way\
>Coming down is still a hell of a ride

>If you can feel your heartbeat\
>You’re not done yet\
>You can’t be\
>If it hurts, it’s working\
>There is love enough\
>For you and me

>If you can feel your heartbeat\
>You’re not done yet\
>Just keep going\
>There is love enough\
>For you and me

>If the world is made out of us,\
>All our shadows suggest a sun\
>Every desert heart that wants the flood\
>Come and bring your need\
>There is love enough

>Keep going ‘cause we can’t go back\
>Keep going ‘cause we can’t go back\
>Keep going ‘cause we can’t go back\

>If you can feel your heartbeat\
>You’re not done yet\
>You can’t be\
>If it hurts, it’s working\
>There is love enough\
>For you and me

>If you can feel your heartbeat\
>You’re not done yet\
>Just keep going\
>There is love enough\
>For you and me

## Heartbeat release
June 6th, LostBoy [tweets](https://twitter.com/lost_boy84/status/1533523657498034177) a link to comtek.life, with an attached video

<video src="https://user-images.githubusercontent.com/6541033/172073978-52ef7203-805f-4ae1-8701-db246010d541.mp4" controls>
</video>

After several days of, the comtek.life page updated to link to the *Heroes* album [information page](https://themidnight.lnk.to/heroes), and now redirects to this automatically

### LostBoy Video
Yet to be understood:
- [ ] If the 'Comtek X-MP' is a significant reference to the Cray [supercomputer](https://en.wikipedia.org/wiki/Cray_X-MP)
- [ ] If the repeated 'I <3 NY' images are relevant
- [X] ~~What the audio is~~ Backing track is Heartbeat
- [X] ~~What is coming on June 8th. Suspected to be *Heartbeart*, given the cover & lyrics revealed so far~~ Heartbeat was released

## Phase III
### Homepage Update
The Comtek.life homepage has been updated, featuring a new version number and a new release date. The new date is for July 6th, and the version number is a youtube video ID

![updated home](comtek_life_update.jpg)

### YouTube Video
The ID can be added to youtube.com/watch?v= to view
<iframe width="1049" height="599" src="https://www.youtube.com/embed/FpskTb9RiE4" title="01000001 01110110 01100001 01101100 01100001 01101110 01100011 01101000 01100101" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

The name, 01000001 01110110 01100001 01101100 01100001 01101110 01100011 01101000 01100101, can be decoded from binary to read 'Avalanche'

![Avalanche decode](binary_avalanche.jpg)

Extracting the audio from the video and viewing it through a spectrogram, you can do this with Audacity, reveals the message 'Who Are Comtek Enterprises"

![Spectogram](comtek_spectogram.jpg)

Following this, LostBoy tweets asking to know more about this 'organisation'

![lostboy tweets](lostboy_comtek.jpg)

the '.org' top-level domain (TLD) is used for organisations. Using this, the website 'comtekenterprises.org' is found

### ComtekEnterprises
The homepage is just a gif

![comtek homepage](COMTEK_ENTERPRISES.gif)

Inspecting the page, in a browser like chrome, reveals a comment.

![comment on homepage](comtek_comment.jpg)

Adding this to the URL gives an [image](https://comtekenterprises.org/heroes/avalanche.jpg), avalanche.jpg

<img src="avalanche.jpg" height="250px" width="250px"></img>

The bottom right corner of the image holds a QR code

![QR Code](avalanche_qr.jpg)

When scanned, this gives the URL https://comtekenterprises.org/6176616C616E636865/avalanche_intro.enc

The directory used here, 6176616C616E636865, is the Hexadecmial equivalent of 'avalanche'

### Avalanche_Intro.enc
This file is encrypted. Running the 'file' utility on it, in Linux, reveals it is an OpenSSL file with salted password

![File Output](avalance_intro_file_check.jpg)

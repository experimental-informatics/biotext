<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/write-tmka-in-pd-1024x595.png" alt"img" style"zoom:80%;" />

# README

Pd, a free real-time computer music system.

Getting Pd from: http://msp.ucsd.edu/software.html

or from the Pure Data community site: https://puredata.info

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620175122092.png" alt"image-20210620175122092" align"left" style"zoom:50%;" />

Installation instructions are in INSTALL.txt and the HTML documentation at: http://msp.ucsd.edu/Pd_documentation/index.htm

If you download and unpack Pd, you will also find the HTML documentation locally in the file "doc/1.manual/index.htm".

**Linux** (or FreeBSD): In some Linux installations you can download Pd via "apt-get install puredata" or "dnf install puredata"; otherwise you can download the source and compile it as described in INSTALL.txt.

**Apple macOS**: Pd binaries are distributed as a "tar.gz" file. The web browser will probably download this archive into your Downloads folder. Double click to extract the archived Mac app which you can then run and/or drag into your Applications folder.

**Microsoft Windows**: Pd binaries are distributed as a self-extracting executable or as a "zip" file.

For any questions about Pd or if you wish to be notified of releases, you can browse and/or join the Pd mailing list: https://lists.puredata.info/listinfo

# what is pure data?

**[Pure Data](https://puredata.info)** (or Pd) is a real-time graphical programming environment for audio, video, and graphical processing. 

runs on anything from personal computers to embedded devices (ie [Raspberry Pi](http://puredata.info/docs/raspberry-pi)) and smartphones (via [libpd](http://puredata.info/downloads/libpd), [DroidParty (Android)](http://puredata.info/downloads/pddroidparty), and [PdParty (iOS)](http://github.com/danomatika/PdParty). It is a major branch of the family of patcher programming languages known as Max (Max/FTS, ISPW Max, [Max/MSP](http://cycling74.com/), etc), originally developed by Miller Puckette (http://crca.ucsd.edu/~msp/) at [IRCAM](http://www.ircam.fr/). Pd includes the work of many developers (http://puredata.info/), making the whole package very much a community effort.

Pd is commonly used for live music performance, VeeJaying, sound effects, composition, audio analysis, interfacing with sensors, using cameras, controlling robots or even interacting with websites. Because all of these various media are handled as digital data within the program, many fascinating opportunities for cross-synthesis between them exist. Sound can be used to manipulate video, which could then be streamed over the internet to another computer which might analyze that video and use it to control a motor-driven installation.

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/Pd_uebersicht.jpg" alt"Pd uebersicht.jpg" align"left" style"zoom:50%;" />

Programming with Pd is a interaction that is pretty close to the experience of manipulating things in the physical world. The most basic unit of functionality is a box, and the program is formed by connecting these boxes together into diagrams that both represent the flow of data while actually performing the operations mapped out in the diagram. The program itself is always running, there is no separation between writing the program and running the program, and each action takes effect the moment it is completed.

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/puredata-whatisrtp-patch_2-en.png" alt"patch_2" style"zoom:50%;" /><img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/puredata-whatisrtp-patch_1-en.png" alt"patch_1" style"zoom:50%;" />

As an FLOSS project, Pure Data is a community effort and is continuously being expanded to include more functions. The community around Pure Data have created additional functions (called "externals" or "external libraries") which are used for a wide variety of other purposes, such as video processing, the playback and streaming of MP3s or video, the manipulation and display of 3-dimensional objects and the modeling of virtual physical objects. There is a wide range of external libraries available which give Pure Data additional features. Just about any kind of programming is feasible using Pure Data as long as there are externals libraries which provide the most basic units of functionality required.

# what is FLOSS?

![Bildschirmfoto_2021-06-20_16-22-17](https://github.com/experimental-informatics/biotext/blob/master/images//images/Bildschirmfoto_2021-06-20_16-22-17.png)

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/Bildschirmfoto_2021-06-20_16-27-11.png" alt"Bildschirmfoto_2021-06-20_16-27-11" align"left" style"zoom:55%;" />

---

# what is digital audio?

### ADC / DAC

The diagram is showing how sound travels through your computer. The "Analog to Digital" & "Digital to Analog Conversion" is done by the soundcard. The "Digital System" in our case is *Pure Data.*

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/puredata-whatisdigitalaudio-analogue_digital_conversion-en.png" alt"Analogue_Digital_Conversion" style"zoom:50%;" /> *Source: [ http://en.wikipedia.org/wiki/Image:Analogue_Digital_Conversion.png](http://en.wikipedia.org/wiki/Image:Analogue_Digital_Conversion.png)*

### Frequency and Gain 

*Source: https://en.flossmanuals.net/pure-data/_full/*

First, imagine a loudspeaker. It moves the air in front of it and makes a sound. The membrane of the speaker must vibrate from it's center position (at rest) backwards and forwards. The number of times per second it vibrates makes the **frequency** (the note, tone or pitch) of the sound you hear, and the distance it travels from it's resting point determines the **gain** (the volume or loudness) of the sound. Normally, we measure frequency in **Hertz** (Hz) and loudness or gain in **Decibels** (dB).

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/puredata-whatisdigitalaudio-speaker-en.png" alt"speaker" style"zoom:50%;" /> 

A microphone works in reverse - vibrations in the air cause its membrane to vibrate. The microphone turns these acoustic vibrations into an electrical current. If you plug this microphone into your computer's soundcard and start recording, the soundcard makes thousands of measurements of this electric current per second and records them as numbers.

### Sampling Rate and Bit Depth 

To make audio playable on a Compact Disc, the computer must make 44,100 measurements (called **samples**) per second, and record each one as a **16-bit number**. One **bit** is a piece of information which is either 0 or 1, and if there are 16 bits together to make one sample then there are 216 (or 2x2x2x2x2x2x2x2x2x2x2x2x2x2x2x2  65,536) possible values that each sample could have. Thus, we can say that CD-quality audio has a **sampling rate** of 44,100 Hz and a **bit-depth** or **word length** of 16 bits. In contrast, professional music recordings are usually made at 24-bit first to preserve the highest amount of detail before being mixed down to 16-bit for CD, and older computer games were famous for having a distinctively rough 8-bit sound. By increasing the sampling rate, we are able to record higher sonic frequencies, and by increasing the bit-depth or word length we are able to use a greater **dynamic range** (the difference between the quietest and the loudest sounds it is possible to record and play).

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/puredata-whatisdigitalaudio-pcm-en.png" alt"Pcm" style"zoom:50%;" />



*An example of 4-bit sampling of a signal (shown in red). This image shows that 16 possible values can be made from 4-bits--a very low dynamic range indeed! In Pd, our scale of numbers goes from -1 to 1, with 0 in the middle. Source: http://en.wikipedia.org/wiki/Image:Pcm.svg*

*The number we use to record each sample has a value between -1 and +1, which would represent the greatest range of movement of our theoretical loudspeaker, with 0 representing the speaker at rest in the middle position.*

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/puredata-whatisdigitalaudio-waveform-en.png" alt"waveform" style"zoom:80%;" />

*Graphical depiction of a sine wave, which crosses zero from the negative to the positive domain.*

When we ask Pd to play back this sound, it will read the samples back and send them to the soundcard. The soundcard then converts these numbers to an electrical current which causes the loudspeaker to vibrate the air in front of it and make a sound we can hear.

# patching

## getting to know the interface

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210618120112061.png" alt"image-20210618120112061" style"zoom:53%;" />

## the help browser

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210618120128719.png" alt"image-20210618120128719" style"zoom:53%;" /><img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210618120229695.png" alt"image-20210618120229695" style"zoom:43%;" />

### with what we are patching?

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210618120659646.png" alt"image-20210618120659646" style"zoom:63%;" />

Pd has also a number of GUI objects to graphically control the patch and improve its visual experience.

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/Bildschirmfoto_2021-06-20_16-41-14.png" alt"image-20210618120726148" style"zoom:73%;" />

### how we patch?

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210618120159633.png" alt"image-20210618120159633" align"left" style"zoom:53%;" /><img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210618120250028.png" alt"image-20210618120250028" style"zoom:70%;" />



### we have 2 different modes of working...:

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210618120401147.png" alt"image-20210618120401147" style"zoom:53%;" />... the *edit mode* and the *play (excecute) mode*

### objects we need today

![image-20210620165950152](https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620165950152.png) 

![image-20210620170031076](https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620170031076.png)    

![image-20210620170111150](https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620170111150.png) 

![image-20210620170153359](https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620170153359.png) 

### what else do we need?

#### the ASCII-Table:<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620170353842.png" alt"image-20210620170353842" style"zoom:67%;" />

### our first program (patch)

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620171044627.png" alt"image-20210620171044627" style"zoom:40%;" /><img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620171130727.png" alt"image-20210620171130727" style"zoom:40%;" /><img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620171213897.png" alt"image-20210620171213897" style"zoom:40%;" /><img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/Bildschirmfoto_2021-06-20_17-13-48.png" style"zoom:40%;" />

### our second program (patch)

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620172020612.png" alt"image-20210620172020612" style"zoom:40%;" /><img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620172046642.png" alt"image-20210620172046642" style"zoom:40%;" /><img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620172111163.png" alt"image-20210620172111163" style"zoom:40%;" /><img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620172130905.png" alt"image-20210620172130905" style"zoom:40%;" />

## example works, based on that program

**you'll find the codes into the Biotext-Semesterapparat**

### ascii-piano (Biotext_Semesterapparat/pd-workshop tmka/keyboardpiano.pd)

![image-20210620183302658](https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620183302658.png)

### article_5 (Biotext_Semesterapparat/pd-workshop tmka/article-5/article_5.pd)

controlling your muscles through your keyboard... 

```
                         article_5 
				  [Performance]
					Muscle Accelerator on forearm, Arduino Board, Pure Data 
					...trying to write in Realtime, while every character gives an electrical feedback to finger muscles
								Thanx to Pedro Lopes!
			
				Grundgesetz für die Bundesrepublik Deutschland (GG)
					vom 23. Mai 1949 (BGBl. I S. 1)
				"(1) Jeder hat das Recht, seine Meinung in Wort, Schrift und Bild frei zu äußern 
			und zu verbreiten und sich aus allgemein zugänglichen Quellen ungehindert zu unterrichten. 
			Die Pressefreiheit und die Freiheit der Berichterstattung durch Rundfunk und Film 
			werden gewährleistet. 
			Eine Zensur findet nicht statt." 
```

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/ProprioceptiveInteraction_PedroLopes_small_crop2.png" alt"pedro lopes research home - pedro lopes research" style"zoom:67%;" />

you'll find a Video-documentaion of the performance here: https://noparts.org/whoami/#6

the pd-patch, you'll find here: 

* if you extract the zip-file, there is a patch in it calls *article_5.pd* < run & study it!
* the muscle-accelerator equipment we have in ground zero @ my office ... if you wanna experiment with it.
  * there is no propper documentation in it in how to connect to arduino and musce accelerator etc.



---

# little helpers...: 

## Documentation and resources

Please check the [documentation page](http://puredata.info/docs), where you can find [Resources to start learning](http://puredata.info/docs/ResourcesToStartLearning/), [Books about Pd](http://puredata.info/docs/BooksAboutPd/), [Manuals](http://puredata.info/docs/manuals/) and more!

Also check out the [Pure Data patch Repository](http://www.pdpatchrepo.info/)

Find Pd people on [Facebook](http://www.facebook.com/groups/4729684494/) and [Reddit](http://www.reddit.com/r/puredata/) and join us on our [mailing list](http://lists.puredata.info/listinfo/pd-list) (more on the [Community page](http://puredata.info/community) )

a good collection of pure data sources (by max neupert) to have a first step in can be found here: https://www.uni-weimar.de/kunst-und-gestaltung/wiki/Pure_Data_-_Getting_started

some more Books & helper files: 

* http://www.pd-tutorial.com/ von Johannes Kreidler
* https://www.researchgate.net/publication/242020079_The_Theory_and_Technique_of_Electronic_Music von Miller Puckette
* multimedia programming in pd https://curiousart.org/digital_proj/pd_eBook.pdf von bryan wc chung
* floss manuals: https://en.flossmanuals.net/pure-data/_full/

---

# Homework for next pd-workshop-session 

## coding a first sequenzer

#### 0. study and experiment with the following 6 objects:

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620191914732.png" alt"image-20210620191914732" style"zoom:40%;" /> < your first math object ^_*)

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620191157312.png" alt"image-20210620191157312" style"zoom:80%;" /> 

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620192351656.png" alt"image-20210620192351656" style"zoom:80%;" /> 

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620191223630.png" alt"image-20210620191223630" style"zoom:80%;" /> 

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620191333715.png" alt"image-20210620191333715" style"zoom:80%;" /> 

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/Bildschirmfoto_2021-06-20_19-14-27.png" alt"Bildschirmfoto_2021-06-20_19-14-27" style"zoom:80%;" /> 

#### 1. build a metronom

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620190327510.png" alt"image-20210620190327510" style"zoom:50%;" />

#### 2. build a counter

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620190423991.png" alt"image-20210620190423991" style"zoom:50%;" />



#### 3. build a modulo counter

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620190536457.png" alt"image-20210620190536457" style"zoom:50%;" />

#### 4. stop at a specific number

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620190903086.png" alt"image-20210620190903086" style"zoom:50%;" />

#### 5. build a simple 8-tone sequenzer 

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620190122063.png" alt"image-20210620190122063" style"zoom:50%;" />

#### 6. expand your sequenzer (optional)

<img src"https://github.com/experimental-informatics/biotext/blob/master/images//images/image-20210620193109006.png" alt"image-20210620193109006" style"zoom:80%;" />








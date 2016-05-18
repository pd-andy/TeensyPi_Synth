#TeensyPi Synth: A Contextual Reflection
[![](https://github.com/pd-andy/TeensyPi-Synth---Devised-Project/blob/master/media/TeensyPi_Thumbnail.png)](https://youtu.be/xZuaGf4bTv4 "TeensyPi Synthesiser")
###Final Project Description
The TeensyPi Synthesiser is a standalone instrument demonstrating a proof of concept, integrating technologies and software from the hacker and open-source movement. These technologies are: the Teensy, an Arduino-like micro-controller used to create the control surface of the instrument. The Raspberry Pi A+, an open-source Linux computer that acts as the 'brain' of the instrument, providing an interface between the Teensy and the software. And finally Pure Data, a graphical programming language  used to create the synthesiser in software. Due to the openness of all the technologies used the user has the power to change the instrument to their liking. Potentially adding more/new controls to the Teensy such as sliders or push buttons, or creating a new Pd patch to interface with the existing hardware. Furthermore all the components are affordable and easily sourced. The Teensy is just £12 and while the original Pi I used for the project is no longer available are for more powerful revision, the Raspberry Pi 3 Model B, is available for little over £30. Combine this with the cost of some common parts such as potentiometers, buttons and switches and the user can create an extremely capable open-source synthesiser for around £50. Ultimately the project has shifted away from my initial proposal, a modular digital synthesiser. This is for two main reasons. The initial proposal had me using multiple Teensy's to act as different synth modules, this quickly prove expensive and difficult to manage. Taking on low level C++ programming and electronics when I had little/no prior experience ended up being too large of an undertaking so the project evolved to where it is now. I was already proficient in Pure Data so it made sense to anchor my project on a process I was familiar with. Moving to the open-source model I have adopted for the final project was intuitive as I was already deeply immersed in the maker and hacker community; the proof of concept is far more useful to the community as a whole being one of openness and hackabilty rather than my original proposal.

![](https://github.com/pd-andy/TeensyPi-Synth---Devised-Project/blob/master/media/TeensyPi_Front.jpg)
###Contextual Reflection
The maker movement has recently exploded as a throwback to the '40s where DIY was a common hobby for many of the population. Similarily, the hacker movement is a statement against closed source softare and propreitary hardware, and an expression of individuality and creativity. "Circuit-bent" instruments have been commonplace for some time, often taking childrens toys and electronics and modifying the circuit in some way to create a usable instrument, often with very unique and creative results. John Richards explores the concept of hacked and DIY instruments with the ensemble 'Dirty Electronics'[1]. Instruments created by the ensemble can be found online and most notably including the Mute Synth and Mute Synth II. An extract from the documentation captures the goals of much of the hacker movement with regards to instruments; "The Mute Synth II is a statement against MPEG culture and places an onus on active participant rather than passive consumer. " John Richards suggests in his essay 'Beyond DIY in Electronic Music' that the instrument maker movement stems as a reaction to the alienation of consumer digital technology and a corporate "one-size-fits-all" mentality[2]. The same issue is discussed from the broader perspective of open source software and the maker movement as a whole in a video created by the PBS Ideas Channel[3]. Both sources address the consumers desire to hack and turn the products they have to products they truely own, as a reflection of ones self. As proprietary and closed source technology becomes more common in an aggressive capitalist market the user can no longer rely on mainstream products to satisfy their need for individuality.

 As the maker movement has grown an increasing number of open hardware devices have been released; most notably the Arduino microcontroller and Raspberry Pi computer. The uses and applications for these pieces of hardware are plenty, but the potential for such platforms to flourish within the creative arts is obvious. Tutorials for DIY MIDI controllers built with the arduino are plenty as are videos and presentations of crude synthesisers built with these low powered microcontrollers. Unfortunately due to the limitations in processing power of these microcontrollers their suitability as 'real' usable instruments is limited; while some attempt has been made, notably the Mozzi arduino library[4] and the Audino Granular Synth [5], there seems to be very little buzz around unifying the Arduino and the Pi to create a single instrument. I believe the project slots nicely into this niche, merging the PureData, Arduino/Teensy and Raspberry Pi communities. A similar project comes in the OWLPedal and OWLModular[6]. These products provide a hardware based way of running and interfacing PureData patches (although C++ dsp can be uploaded to the hardware too). While the OWL products don't use the Arduino or Pi they do post all documentation and a Bill of Materials to create your own[7]. A project that coincidentally shares the same name as the one presented here, although not the same goals, is the TeensyPi: a board that integrates both pieces of hardware for accurate temperature[8]. While the Raspberry Pi does have access to a number of GPIO pins the benefits of integrating an Arduino-like microcontroller for interfacing with controls and the outside world far outweigh the minor convinience of combining two hardware devices. In keeping with the maker movement I feel that relying on the Pi to handle the core audio processing is the absolute best choice. With easy access to all the ports on the Pi the user is able to easily upload their own PureData patches, or even use and create entire new software to interface with the integrated Teensy. The only piece of closed source software/hardware in my entire instrument is the bootloader installed on the Teensy board, which must be purchased from the PJRC store should the user wish to build their own PCB from scratch. Fortunately other open source bootloaders are available for the chip with little to no feature loss.
 
 ![](https://github.com/pd-andy/TeensyPi-Synth---Devised-Project/blob/master/media/TeensyPi_Back.jpg)
###Project Summary
Creating an affordable digital modular solution is still something I'd very much like to pursue and despite my original setbacks I feel the knowledge and skills I have gained over the course of the project as a whole have only greatened the possibility of realising that goal. Sound quality is passable, if not good. Originally the weak processing power of the Pi A++ prove to be an issue, struggling to keep up with even relatively basic audio processing. However with some optimisations to the machine and some heavy slimlining of wasted features the Pi has become more than capable to handle even moderately complex audio processing. An external audio card is an absolute requirement, either third party USB ones or one of the available "HATs" that solder onto the Pi's GPIO. Given that the Pi project has taken great strides in performance with each product revision, a user operating the project would experience none of these problems even without optimisation on the Raspberry Pi 3. At the time however it made sense to use the resources I already had available to me, purchasing another Pi would be futile as the project successfully demonstrates the proof of concept with the hardware and technologies I had available. The greatest limitation of using the project as a 'real' instrument is the significant boot time. While it is possible to attribute this to the slow speed of the A++, more likely it is the added bulk of running an entire computer/operating system just to run PureData. An embedded solution making use of libpd[9] would be far more suitable for a professional portable instrument. If I would to embark on the project once more with the goal of creating a more refined product I believe the cost can be further driven down without sacrificing, and in some cases improving, performance due to the large number of maker products making their way into the world; a notable example being the Udoo[10].

###References
[1] Dirty Electronics: Instruments - http://www.dirtyelectronics.org/mutesynth2.html

[2] Beyond DIY in Electronic Music - http://www.journals.cambridge.org/article_S1355771813000241

[3] Do Makers Propose a More Open Source Future? - https://www.youtube.com/watch?v=ct5fjHC7tL8

[4] Mozzi - http://sensorium.github.io/Mozzi/

[5] Audino Granular Synth - https://www.youtube.com/watch?v=NTob27lOpcU

[6] The OWL - https://hoxtonowl.com

[7] OWL Wiki - https://hoxtonowl.com/wiki/Main_Page

[8] TeensyPi - http://www.teensypi.com

[9] libpd.cc - http://libpd.cc

[10] Udoo - http://www.udoo.org


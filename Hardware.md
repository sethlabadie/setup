# How I Setup my Workspace


## Rant on Computer Choice

I use a Mac computer, because it is the (only) choice. Yes, Linux is an option too. Microsoft is not an option, unless you are developing for Windows or only have that option at work.

I think Apple is better because:

1. It basically has all of the Linux goodness, plus all of the Apple goodness. Microsoft has none of the Linux goodness, and none of the Apple goodness. Microsoft is a poor imitation of Apple and is clunky.
2. Apple computers are typically more powerful than generic computers, especially if you get an ARM-based system (although Linux is lightweight and gives great performance for the given hardware).
3. There is a lot--A LOT--of software that is written only for POSIX systems, and with Windows you are either SOL or you have to do a workaround.
4. You really need to use a Unix-like (POSIX) file system and be able to run Unix-like shells
5. Most sample code and helps are written for either Mac or Linux (and Mac can typically run Linux commands, either directly or with tweaks to the code). With Microsoft, you are left to interpret and recode. Go to StackOverflow and see how many questions are written for Windows. Not many.
6. The Mac ecosystem. Outside of coding, your mac integrates with your iPhone, Apple Watch, iPad, Apple TV, HomeKit, etc., and you can share your purchased apps and Apple+ with your family, and you can track your kids and your dog with an airtag, etc etc.

Plus, some additional considerations:

7. It is cooler
8. You will look like a real programmer at the cafe or the workspace

If you are forced to use a Microsoft computer at work, then fine, but install WSL (Windows Subsystem for Linux) and use that.

Props to Linux users. A great option too. But I like Mac. To each his own. We can jointly hate on Microsoft.

A plus for Mac is that it is more secure. A plus for Mac is that it is more powerful. A plus for Mac is that it is more integrated with the Apple ecosystem. A plus for Mac is that it is more user-friendly. A plus for Mac is that it is more popular. A plus for Mac is that it is more supported. A plus for Mac is that it is more stylish. A plus for Mac is that it is more fun.

A plus for Linux is that it is free. A plus for Linux is that it is efficient, and can breathe new life into old hardware. A plus for Linux is that servers are mostly run on Linux, and so you can develop on Linux and then deploy to Linux. A plus for Linux is that it is more customizable. A plus for Linux is that it is more open-source. A plus for Linux is that it is more lightweight. A plus for Linux is that it is more flexible.

Desktop or laptop is your choice. Either will work. If you are going to be traveling a lot, then a laptop is probably better. If you are going to be working from home, then a desktop is probably better. If you are going to be doing both, then you can get a laptop, with a dock, a monitor, a keyboard, and a mouse for your home office.


## Computer Choice


If you go with Mac, the desktop options are iMac, Mac Mini, Mac Studio, or Mac Pro, and the laptop options are MacBook Air and MacBook Pro. Buy whatever is in your budget, but know that the only one that is truly upgradable is the Mac Pro, and you will pay through the nose for that. Make sure you buy enough RAM up-front. With Mac, you are getting the best computer out there, but will pay a lot for it. If you are resource-constrained, either buy a Mac Mini with lots of RAM, or go with the Linux option below.

You  can set your iCloud documents folder to be your default documents folder, so files can be accessed them from any computer that is set up similarly. This will also make it much easier if you are also using a Mac Book Pro for your travel system. Just save the file on your desktop computer, and open it on your Mac Book Pro. Automatically. No need to transfer files. There are three downsides to this approach. First, you will need to pay for more iCloud storage. I pay for the 2TB plan, which is $10/month. I think it is worth it. Second, you will need to be connected to the internet to access your files. This is not a problem for me, since I am always connected to the internet. Third, your computer startup time will be dramatically increased--perhaps a half hour or more. I don't know why this is, but I think it is because the computer is trying to sync all of your files. It is irritating. I just restart my computer before I go to bed, and it is ready in the morning.

If I am using a Mac Book Pro, iMac, or Mac Mini in the future, I would like to get an external GPU (eGPU) to boost the graphics performance. I do Data Science work, so this will be helpful in doing machine learning. I will mount it underneath the desk.

If you go with Linux, you can either build your own (recommended if you want to learn some hardware, and gain bragging points), or buy a computer with Microsoft Windows on it and convert it to Linux. You will definitely get more bang for your buck with Linux compared to Mac. With enough time, energy, and tweaking, you can make Linux look and behave very well. However, there are some people that say that "Linux is only free if you don't value your time." I think that statement is a bit unfair, because ricing your system can be fun, but the statement certainly has a grain of truth.

As for which Linux distribution to use, there are roughly three major groupings. The dozens of various distributions out there are generally derived from one of these three.

1. The popular choice is Ubuntu (most installations). It is generally easier for beginners, has lots of flavors, and is well-supported and stable.
2. The second choice is the Red Hat family, to include RH Enterprise Linux, CentOS, and Fedora. These are very stable and supported distros, and generally are the best for enterprise use. If you will be ssh'ing into a server, it will probably be running RHEL or CentOS. I personally use Fedora for this reason, so that I am used to the particularities of this system.
3. The third choice is Arch (btw). Istalling Arch requires a lot more involvement, and is not for the faint-of-heart. What you get at the end is a highly-customized version of Linux, the use of the excellent Arch User Repository (AUR), and bragging rights.
4. Another consideration is that while Ubuntu and RH are well-supported, stable, and have multiple flavors for installation, they are also owned by companies (Canonical and Red Hat/IBM respectively). They could have [telemetry installed](https://www.gnu.org/philosophy/ubuntu-spyware.html) (fancy word for spyware), and development is at the [whims](https://discussion.fedoraproject.org/t/red-hat-removes-public-access-to-rhel-source-code-consequences-for-fedora-in-the-long-run/84671) of the companies involved.


## Desk Setup

I would like to get a sit-stand desk. I don't have a recommendation yet. For a desk shelf, I have seen [GroveMade](https://grovemade.com) advertised quite a bit, and it looks nice. GroveMade also makes a lot of other nice desktop components. I am open to options.

I would also like to get a Thunderbolt dock to connect to multiple monitors and other peripherals. I am not currently using a computer dock since I don't have a laptop and I am not using multiple monitors, but I would choose one that has the power to connect to multiple monitors using Thunderbolt. Thunderbolt is better and faster than HDMI, and can send data both ways. I believe that the [iVANKY FusionDock Max 1 Thunderbolt 4](https://ivanky.com/products/ivanky-docking-station-fusiondock-max-1) is the best on the market. It has two Thunderbolt 4 connections for monitors, while the competition all have only one Thunderbolt 4 connection. The two connections allow for up to four 4k monitors at 60Mhz refresh rate. Many people also mention the [CalDigit TS4](https://www.caldigit.com/thunderbolt-station-4/) as a great option.

The iMac has a built-in monitor (which is of good quality), so I don't have a separate monitor. In the future I will get a widescreen monitor, with another monitor in landscape mode to display my email program, slack, or code.

For desktop speakers, I would like a set which uses s/pidf or optical audio. I don't have a recommendation yet, but the [Klipsh R-41PM](https://www.amazon.com/dp/B07FK48JW8) might work well. Kanto speakers also look nice, with a nice wood finish, but not all models have s/pidf or optical audio.

For a keyboard, I am using the [MacTigr](https://www.daskeyboard.com/mactigr/) from Das Keyboards. It is a mechanical keyboard designed with a Mac layout. Das also offers [Dvorak keycaps](https://shop.daskeyboard.com/collections/accessories/products/das-keyboard-modern-font-dvorak-rgb-keycap-set-for-gamma-zulu-switches-translucent), if that is your typing orientation. The only gripe I have is that I wish this keyboard had backlighting. Other Das keyboards do have backlighting, but not the MacTigr. Finally, I pair this with the [Palm Rest One](https://shop.daskeyboard.com/collections/accessories/products/das-keyboard-palm-rest-one), which I think is a necessity. I am considering exploring the [Keychron](https://www.keychron.com) line, and also ergonomic keyboards such as the [MoErgo Glove80](https://www.moergo.com) and the Dactyl Manuform, but I haven't tried them yet.

For a mouse, I use the Logitech [MX Master 3 for Mac](https://www.logitech.com/en-us/products/mice/mx-master-3s-mac-bluetooth-mouse) mouse. It also needs a good mousepad. I prefer hard plastic. For this, I use the Logitech-G [G440 Gaming Mousepad](https://www.logitechg.com/en-us/products/gaming-mouse-pads/g440-hard-gaming-mouse-pad.943-000790.html). Previously, I used the SteelSeries [QCK Hard Pad](https://steelseries.com/gaming-mousepads/qck-hard), which was also really good. Both are about equal in my opinion.

For headphones, I use the Bose [QuietComfort](https://www.bose.com/p/headphones/quietcomfort-acoustic-noise-cancelling-headphones/QC-HEADPHONEARN.html?dwvar_QC-HEADPHONEARN_color=WHITE%20SMOKE) headphones (formerly QuietComfort 45), although Bose recently came out with the [QuietComfort Ultra](https://www.bose.com/p/headphones/bose-quietcomfort-ultra-headphones/QCUH-HEADPHONEARN.html?dwvar_QCUH-HEADPHONEARN_color=WHITE%20SMOKE&quantity=1). I am intrigued by the Das [Holosonic T1w](https://www.daskeyboard.com/holosonic-t1w/) headphones, which are much cheaper and also connect over wifi in addition to bluetooth.

I use a generic [bookstand](https://www.amazon.com/gp/product/B00MVBDLFC) that I bought on Amazon. There are plenty of other options.

A light is important to illuminate your workspace. BenQ [Blue Genie LED Desk Lamp](https://www.amazon.com/BenQ-Monitors-Eye-Ergonomic-White-Perfect-Architects/dp/B06Y1WN1VJ/ref=sr_1_5?crid=1D9YHUF5NVUOX&keywords=benq%2BLED&qid=1702757296&s=office-products&sprefix=benq%2Bled%2Coffice-products%2C130&sr=1-5&th=1) is a good choice. Although it is offered still on Amazon, BenQ apparently doesn't make it anymore. BenQ also offers the [e-Reading Desk Lamp](https://www.benq.com/en-us/lighting/e-reading-desk-lamp.html) and a monitor lightbar called the [ScreenBar Halo](https://www.benq.com/en-us/lighting/monitor-light.html), either which might be a good option.

For work, I need to insert a security card in order to access certain websites. For this, I use the [Cherry SmartTerminal ST-1144](https://www.cherryamericas.com/smartterminal-st-1144). It has a hefty weight and sits nicely on my desktop. Another option might be the HID [Omnikey 3121](https://www.hidglobal.com/products/omnikey-3121). Follow the advice [here for USB](https://militarycac.com/usbreaders.htm) and [here for USB-C](https://militarycac.com/usbcreaders.htm). Don't buy any cheap Chinese crap on Amazon, because you never know what [malware](https://krebsonsecurity.com/2022/05/when-your-smart-id-card-reader-comes-with-malware/comment-page-1/) it contains.


## Travel / Remote Work System

My travel package will include a Mac Book Pro. No purchase yet.

No current recommendations for a [travel or remote work bag](https://www.standardluggage.com/pages/nomad-backpack). My criteria will be that it fits a 15-inch computer snugly; has a separate compartment for documents; has a separate compartment for computer peripherals, or can hold a peripherals bag; has a separate compartment for extraneous items such as pens and keys; and folds open for TSA compliance.
Some brands that I am considering include [Nomatic](https://www.nomatic.com) and [Mous](https://www.mous.co/products/extreme-commuter-zip-backpack?variant=39993959678010).

No current recommendations for an accessories bag. My criteria will be that it fits a mouse, keyboard, and mousepad; has a separate compartment for cables; has a separate compartment for a power brick; and has a separate compartment for a power cord. All of this may not be necessary if the travel bag has enough compartments or if the keyboard has a separate travel case.

For a travel keyboard, I plan to use a Logitech-G [Pro X TKL Wireless Keyboard](https://www.logitechg.com/en-us/products/gaming-keyboards/pro-x-tkl-wireless-keyboard.html) or one of the [Keychron](https://www.keychron.com) TKL keyboards. If I go with the [MoErgo Glove80](https://www.moergo.com), it comes with a travel case.

For a mouse, I plan to use a Logitech [MX Anywhere 3 for Mac](https://www.logitech.com/en-us/products/mice/mx-anywhere-3-mac) mouse.

For a laptop bar, I plan to use a BenQ [Laptop Bar](https://www.benq.com/en-us/lighting/laptop-light.html).

A great choice for a security card reader is the Identiv [SCR3310v2](https://www.identiv.com/products/logical-access-control/smart-card-readers-writers/contact-smart-card-readers-writers/scr3310v2).

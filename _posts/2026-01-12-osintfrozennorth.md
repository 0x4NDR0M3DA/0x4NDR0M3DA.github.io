---
title: Bellingcat OSINT Challenge - The Frozen North - Writeup
time: 2026-01-12 15:00:00
categories: [osint]
tags: [osint,maritime,military]
image: /assets/posts/osintfrozennorth2026/shiptitle.png
---

My 2026 has started with a solid focus on open source intelligence. I feel like up until this point, I didn't really dive deep enough into the field, even though I've always considered OSINT as one of the most valuable tradecrafts that you can master in today's world.

Below you can find my writeup of one of the Bellingcat's OSINT challenges - **The Frozen North**. Grab something to eat, make yourself a coffee, relax and have fun!


### Image Analysis

As per the description, we are tasked with identifying the ship present on satellite image by providing its **IMO (International Maritime Organization) number** - a unique ship identifier.

fotka tutaj

First impression - well, not a lot to work with. The image isn't clear due to cloud cover, the terrain looks rather complex and snowy, the "port" itself is shorter than the vessel, no visible buildings...

A frozen north, icy port that is able to serve only one vessel at a time...This means that we are dealing with a place far north. Filename of the image is **20220901_091318-C5etx_H-.png**. Could it be date and time of the photo being taken?

No search engine could give me any sensible clue of where this is located.

Let's start with topography of the terrain. There is a coast with fair amount of snow on its edges and interior. Take a look at how it is distributed - its presence emphasizes slopes, creating a layer effect. My idea was that the terrain is not flat and has significant height differences. There are a few bodies of water immediately behind the coast with complex shorelines, a possible road heading northbound visible on the left portion of the image.

![[Pasted image 20260118130135.png]]

#### Anybody out there?

After that, I started looking for any trace of settlements / buildings / installations beside the port itself. And surely, there are **three points of interest** that could help with the investigation. I've increased exposure and contrast of the image so they are much more visible:
- a`container yard` or `warehouses` near the port,
- a complex that looks like an `arctic research outpost`,
- a `settlement with housing buildings`.

![[Pasted image 20260118134840.png]]

I focused my attention on the "research complex", because it has two rows of symmetrical, orange objects. I immediately thought that these must serve as a **fuel storage**, similar to the image below:

![[Pasted image 20260118140311.png]]

Now, the vessel itself. The superstructure is on the aft, it has two yellow cranes midship. Hard to tell if there is any cargo onboard. If you look closely however, both of those cranes are rotated in different directions. Not that it means a lot, but that might indicate that the ship could be in the middle of loading/unloading operations when photo was taken.

![[Pasted image 20260118142622.png]]

Let's trace back to the filename. Assuming that it indeed specifies date and time (**20220901_091318**) - it means that the photo was taken on **Sep 1st, 2022 at 09:13:18**, but we don't know if UTC, UTC+8, UTC-8 etc... Given that information, I tasked myself with finding an object that casts a visible shadow. Turns out that the shadows point almost perfectly north, meaning that local time is around noon.

Summarizing the findings: image shows a cargo ship docked at a small, arctic port and is currently undergoing loading/unloading operations, judging by the cranes position. The port appears to be a part of an arctic research or military base with visible buildings, containers and fuel storage. The terrain has a few bodies of water behind the shoreline and a road on the left.

If all of the above is true, then the port should located at **latitude of at least 60-70 degrees north**.

# Port Mapping
#### There's so many!

Armed with that knowledge, I used **MarineTraffic** to try and map the port and its topological characteristics with a base of known ports from the portal.

![[Pasted image 20260118160859.png]]

 I was interested in pretty much anything above this line. Sadly, after several hours and countless port visits later, I still had nothing. Double checks done in Northern Canada, Alaska, Russia, Svalbard, Norway, Greenland... At this point I knew that I have to change strategy. It could be that the port itself got modernized, the topology might have changed or **it's not marked on the map at all**.

After additional research, I found several news articles about Russian presence in the Arctic Ocean. Main consensus was that there are significant efforts related to militarization of the arctic coming from Russia, due to global warming and subsequent ice melting.


![[Pasted image 20260118163357.png]]

![[Pasted image 20260118163446.png]]


#### Russia again!

I then searched for known Russian military bases in the Arctic theatre. I used this map - https://www.americansecurityproject.org/russian-arctic-military-bases/. Marked in red are two bases/ports that were not visible on the **MaritimeTraffic** map.

![[Pasted image 20260118164204.png]]

I quickly examited **Nagurskoye Airbase** that is located in **Franz Josef Land** archipelago, specifically **Alexander Island**.

![[Pasted image 20260118164603.png]]

Then, I started to compare the original image with up-to-date and historical data. I used **Google Earth** and **World Imagery Wayback** - https://livingatlas.arcgis.com/wayback/#mapCenter=47.69376%2C80.77568%2C13&mode=explore&active=45134 and succesfully identified that the port is in fact located on the island! Coordinates: 
**80°46'17"N 47°40'22"E**

![[Pasted image 20260118165326.png]]

#### Back to the ship!

With a port location known, I went straight to **GlobalFishingWatch** https://globalfishingwatch.org/map website to pinpoint all vessels that broadcasted their position near or in the port around Sep 1st, 2022.

Surely enough, there they are. Looks like there were two vessels heading to and out of the island between **Aug 30th - Sep 3rd.**:
`- Mekhanik Pyatlin
`- Cirrus

![[Pasted image 20260118170249.png]]


![[Pasted image 20260118170437.png]]

Details of the **Mekhanik Pyatlin** cargo ship with IMO **8904434** - it spent 41 hours in the port - in line with a theory that the vessel was performing loading or unloading operations on Sep 1st.

![[Pasted image 20260118170707.png]]

I then checked the IMO against **ShipSpotting** website. It surely matches our original vessel description!

https://www.shipspotting.com/photos/3293355?navList=gallery&imo=8904434&page=1&viewType=normal&sortBy=newest

![[Pasted image 20260118171148.png]]

And there is our answer!

![[Pasted image 20260118171226.png]]

Huh, that was something. I really feel like my OSINT skills increased dramatically after this one. I had a lot of fun, even though some parts of the investigation didn't yield any meaningful results - I still learned a ton about maritime open source intel. Thank you for reading, I hope you enjoyed the writeup and had as much fun as I did!

---
title: Bellingcat OSINT Challenge - The Frozen North - Writeup
time: 2026-01-12 15:00:00
categories: [osint]
tags: [osint,maritime,military]
image: /assets/posts/osintfrozennorth2026/shiptitle.png
---

Below you can find my writeup of one of the Bellingcat's OSINT challenges - **The Frozen North**. Grab something to eat, make yourself a coffee, relax and have fun!

### Initial image analysis
As per the description, we are tasked with identifying the ship present on satellite image by providing its **IMO (International Maritime Organization) number** - a unique ship identifier.

![challenge](/assets/posts/osintfrozennorth2026/challenge.png)

Well, not a lot to work with. The image isn't clear due to cloud cover, landscape looks complex and snowy, the port itself is shorter than the vessel, no recognizable buildings... This means that we are indeed dealing with an extremely isolated place, where ship traffic is sparse.

Quick reverse image search - nothing. No search engine was able to point me to any reasonable clue.

Let's start with investigating the terrain. We have a coast with fair amount of snow on its edges and in the interior. Take a look at how the snow is distributed - its presence emphasizes slopes, creating a layer effect throughout the landscape. This must mean that the land is not flat and has significant height differences. There are a few bodies of water immediately behind the coast with complex shorelines, and a possible road heading northbound, visible on the left side.

![analysis1](/assets/posts/osintfrozennorth2026/analysis1.png)

Having that out of the way, I started looking for any trace of settlements / buildings / installations beside the port itself. And surely, I've found **three points of interest** that could help with analysis. I've increased exposure and contrast of the image so they are much more visible:
- a **container yard** or **warehouse complex** near the port,
- an installation that looks similar to **research outpost**,
- a possible **settlement with housing buildings**.

![analysis2](/assets/posts/osintfrozennorth2026/analysis2.png)

The aforementioned "research complex" caught my attention as it appears to have two rows of symmetrical, orange objects...I couldn't think of a better explanation than these being **fuel tanks**, similar to the image below:

![fuel](/assets/posts/osintfrozennorth2026/fuel.png)

Then, I moved to the ship itself. Looks like its superstructure is on the aft and it has two yellow cranes midship. Hard to tell if there is any cargo onboard or in the port. If you look closely however, both of those cranes are rotated in different directions. Not that it means much, but in my mind it was worth noting down as it could indicate loading/unloading process.

![shipcranes](/assets/posts/osintfrozennorth2026/shipcranes.png)

Another interesting clue is **filename** of the image - `20220901_091318-C5etx_H-.png`. Frist part of it looks like a datetime (**20220901_091318**). My theory was - if I were to believe the filename, this could mean that the photo was taken on **Sep 1st, 2022 at 09:13:18**, although specific timezone remained unknown. Then, I focused on finding objects that cast visible shadow and tried to approximate bearing of those shadows. Turns out, they point almost perfectly north, meaning that local time is around noon.

Alright, time for a small summary: a cargo ship docked at a small, arctic port, possibly undergoing loading/unloading operations. The port itself is most definitely not a big hub that sees cargo ships often. It more or less serves as a **landing zone for an arctic outpost/base with visible buildings, containers and fuel storage**. The landscape has a few bodies of water behind the shoreline and a road on the left.

Based on current findings, my educated guess pointed me to a location to **latitude of at least 65-70 degrees north**.

### Port mapping attempts!

Armed with my up to date findings, I went to **MarineTraffic** to try to map the port and its geographical characteristics with a base of known ports from the portal.

![marinetraffic](/assets/posts/osintfrozennorth2026/marinetraffic.png)

I was interested in pretty much anything above this "highly educated" line. Sadly, after several hours and countless identification attempts later, I had no candidates. I commited to double check Northern Canada, Alaska, Russia, Svalbard, Norway, Greenland... Still nothing. At this point I knew that I have to change strategy. It was completely plausibe that the port itself got modernized, the geography might have changed or... **it's not present on the map at all**.

After additional research, I found several news articles mentioning Russian presence in the Arctic Ocean. Main consensus was that there are significant efforts related to militarization of the ocean coming from Russia. Due to global warming and subsequent ice melting, new routes of traffic may emerge - for civilian and military ships alike. Sounds like a whole new playground from geopolitical perspective.

![arctic](/assets/posts/osintfrozennorth2026/arctic.png)

### ...Russia at it again.

If that's the deal, then this might be a military complex. I then searched for maps with known locations of Russian military bases in the Arctic theatre. Quickly, a map from **AmericanSecurityProject** helped me tremendously. Marked in red are two ports that were not visible on the **MaritimeTraffic** map - one is located in **Franz Josef Land**, the second one near **Komsomolets Island**.

![bases](/assets/posts/osintfrozennorth2026/bases.png)

I briefly examined **Nagurskoye Airbase** that is located in **Franz Josef Land** archipelago, more precisely on **Alexander Island**.

![base2](/assets/posts/osintfrozennorth2026/base2.png)

I noticed a very peculiar harbor. I then compared the original image with up-to-date and historical data from **Google Earth** and **World Imagery Wayback** to investigate, pinpoint and... there it is! **The port belongs to the Nagurskoye Airbase**. Coordinates: 

**80°46'17"N 47°40'22"E**

![portfound](/assets/posts/osintfrozennorth2026/portfound.png)

### Back to the ship!

Now, with port location known, I went straight to **GlobalFishingWatch** to analyze all vessels that broadcasted their position near or in the port around Sep 1st, 2022.

Surely enough, I found some hits. Looks like there were two vessels heading to and out of the island between **Aug 30th - Sep 3rd.**:
- **Mekhanik Pyatlin**
- **Cirrus**

![gfw1](/assets/posts/osintfrozennorth2026/gfw1.png)

![gfw2](/assets/posts/osintfrozennorth2026/gfw2.png)

**Mekhanik Pyatlin** is a cargo ship with IMO **8904434**. Additionaly, judging by its AIS signal, it spent 41 hours in the port - in line with the theory that it was performing loading or unloading operations on **Sep 1st**.

![pyatlin1](/assets/posts/osintfrozennorth2026/pyatlin1.png)

I then checked the IMO against **ShipSpotting** website. It surely matches our original vessel description!

![pyatlin2](/assets/posts/osintfrozennorth2026/pyatlin2.png)

And there is our answer!

![answer](/assets/posts/osintfrozennorth2026/answer.png)

Huh, that was something. I had a lot of fun, even though some parts of the investigation didn't yield any meaningful results - I still learned a ton about maritime open source intel. Thank you for reading, I hope you enjoyed the writeup. Take care and until the next one!

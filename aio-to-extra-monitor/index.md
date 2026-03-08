---
title: Turning an old AIO into an extra monitor
description: Not enough monitors? Have an old all-in-one machine lying around? Why waste it? Read along to find out how I turned potential e-waste into a 'free' extra monitor.
lastmod: 2026-03-08
published: 2026-03-08
changefreq: never
priority: "0.1"
feeds:
  - blog/index.json
  - blog/atom.xml
  - blog/rss.xml
tags:
  - weekend-project
  - diy
readtime: 1 min read
template: n3rdium.dev
---
Long time no see! I decided to check back in and assure you that I'm still very much alive and making more cool stuff. My schedule has never been this packed. I've got multiple waves of exams headed my way, and it's going to stay like that till around April next year.

I've always dreamed of having more than one monitor. But I'm broke, so there's no way I'd actually buy one. Ever since I upgraded to a new machine after having lived way too long off an HP Pavilion 20 (not even kidding, it has an Intel Pentium G2020), I've been nagged by the idea countless times: "What if I used it as an extra monitor?"

One fine day, it had crossed the threshold. From the depths of my... 'stowage', I pulled out the poor old AIO. It was still alive, running EndeavourOS (amazing distro/community btw).

When I had a quick look at the ports, though, I was heartbroken. No HDMI, no DisplayPort, no VGA, nothing. If I really wanted a 'new' monitor, I would have to get creative in my approach.
# How
My method is probably really inefficient and more complicated than it needs to be. But it works. I create a virtual “headless” output on Hyprland (my go-to wayland compositor) and start a vnc server on it (using `wayvnc`).

Then, the AIO connects to the main rig using a vnc client (I tried many clients, and found `tigervnc` to work the best). Of course, everything is connected over gigabit ethernet for sanity.
# QoL Updates
I’ve also added some cool functionality, like the ability to change display brightness (via `ddcutil`) and temperature (via `hyprsunset`) automatically based on time of day, ask the vnc client to reconnect manually, and auto-reconnect the client if it was somehow disconnected.
# Conclusion
I’m going to release the nixos configuration of the second monitor on GitHub soon. Also planning to turn an old laptop I had into a THIRD monitor.

I've also been working on a “hologram” display for desk widgets that makes use of more old hardware. Will be releasing it “soon”. Stay tuned for more cool DIY stuff!
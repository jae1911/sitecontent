---
title: "Internet Peace of Mind"
---

# Internet Peace of Mind

As you may have noticed, in <span class="int">[Software used](/wiki/the-internet/software)</span>, it is said that I use NextDNS and that has been the best tool I have been given so far (a self-hosted PiHole can yield the same results tho). So recently, I fixed myself few objectives: 

 - Sleep better
 - Use less big websites like YouTube
 - Try to eat a bit more

As you may imagine, the first objective can (and is) influenced by the other two remaining. Today we will focus on the second one which is to reduce as much as possible exposure to biggest websites. My first step was to completely block all Google services by using the available blocklist called [No Google](https://github.com/nickspaargaren/no-google). And after that by fine tuning and blocking stuff like:

 - reddit.com
 - twitter.com

And basically any Meta/Facebook-owned domain with the [No Facebook](https://github.com/jmdugan/blocklists) blocklist (sadly the No Amazon one is not available yet on the service but it can be imported easily into [uBlock Origin](https://github.com/gorhill/uBlock)). Now, any service is replaced by own instances (see <span class="int">[List of instances](/)</span>) and redirected using [LibRedirect](https://github.com/libredirect/libredirect).

Some other configs are applied on the services, for instance for Piped (YouTube proxy), comments are disabled, video descriptions are minimized by default, recommendations are minimized by default and auto-play is off (unless in audio mode when listening to music). For now, this new hygiene seems to have some effect but will have to see on the long run to see if any lasting effects. For now, I have been spending less and less time in my browser and instead started writing, walking and socializing more (yup, touching grass is a real thing). I will update this post in a month or so to see if there is larger results at the end (which I am sure there will be).

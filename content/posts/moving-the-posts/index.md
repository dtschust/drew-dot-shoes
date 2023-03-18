---
title: "Moving the Posts: Adventures in Legacy Infrastructure Migrations"
date: 2023-03-17T21:50:56-07:00
cover:
    image: "images/before - street view.png"
    alt: "Photo of a utility pole with a mess of wires going in every direction"
    caption: "The utility pole in front of my previous apartment (image from Google StreetView)"
    relative: true
---

I figured I'd mix things up a little bit and write a post that has nothing to do with computers or software development.

At my previous apartment in the Richmond neighborhood of San Francisco, there was a utility pole right outside my apartment that was a real eyesore. My pole wasn't particularly special, most utility poles in the neighborhood looked like this: wires snaking out in every direction, across the street, tangling through trees, etc. On windy days, two wires that appeared to have simply been cut instead of removed would loudly bang against my windows. On a day without fog (rare), the wires obstructed my very narrow view of the Golden Gate Bridge.

I don't know enough about how any of this works to know *why* this utility pole might have been in need of some maintenance, but it certainly didn't give a ton of confidence even at a glance by a layman like myself. Regardless, the company in charge of this pole, [PG&E](https://www.pge.com/), did invest in some maintenance last year, and I'd like to imagine what might have happened.


# The Proposal
Let's pretend you are the infrastructure engineer at PG&E who is in charge of this pole. You've been watching more and more wires get added to this pole over the years, each one increasing the complexity and overall risk of the system. Finally, some change or decay in the system crossed a risk threshold where you now felt the need to advocate for maintenance and improvements. You write a proposal and share it with leadership. The proposal has all the usual things:
* **Describing the problem and its impact**: You break down what's wrong with the current implementation of this pole, and the risks to the business of not addressing them.
* **Definition of Done**: You outline what a successful migration is. In this case, a successful migration would be that the new pole is installed, the wires have been attached to it, and the system is still operating smoothly.
* **The Proposal**: You define the phases and milestones of the project. Obviously there's more detail, but these would be the basic steps:
	* Install a new utility pole next to the existing one.
	* Migrate existing wires to the new pole.
	* Refactor the system (either during the migration or afterwards, whichever makes the most sense) to clean up the technical debt that's accumulated over time.
	* Verify that the migration has been a success.
	* Remove the old utility pole.

These sorts of proposals get written at your company all the time, and most of them never get prioritized. For some reason, either due to the quality of your proposal, the potential risk of not fixing the pole, or just sheer luck and timing, your project gets funded! Your manager tells you this project is going to have really high visibility, and that if you do a good job this could lead to you getting a big promotion. You're stoked! You've been passionate about utility poles since you were a child, and an opportunity like this to dive into a real gnarly utility pole problem and build something robust that you can be proud of will be the highlight of your career so far! You finalize staffing and scheduling of the project, and dive in headfirst.

# The Project
While you want this project to go as smoothly as possible and will do your best to limit outages for customers, this process requires some downtime. So, you determine a good time for an outage based on customer patterns, and send letters to all customers who might be impacted well in advance. I received such a letter, and knew that on specific days last September I may be without power within given time windows.

The day of the project kickoff actually gets pushed back a week due to poor weather conditions, but you update the customers about that too, and the day finally comes!

{{< figure align=center src="images/at work 2.jpg" caption="Project Kickoff: [the optimistic meal](https://www.youtube.com/watch?v=rxJHBewFYos)" >}}

The milestones are flying by perfectly and smoothly. You easily get the new pole installed next to the old one, and after allowing a few days for it to settle (is that how cement works? You tell me, you're the engineer!) you begin migrating wires to the new pole in earnest. Oh man, this new pole is incredible! It's taller than the old one, it's better constructed, it hasn't been beaten down by years of weather. You wish your job always involved working with poles this nice. You tell your boss you're having the time of your life, and they're singing your praises all the way up the org chart. Life is good.

You decide that the smoothest migration path in this case is to move the wires over to the new pole as is, instead of refactoring as you move. This is the least risky approach, and has the least downtime. Besides, once you're over to the new pole and the old pole is gone, life is going to be so much easier: you're going to have more room to operate, and you won't have to deal with all the baggage of the old pole while you focus on finishing the utility pole of your dreams.

You also decide to move the highest risk wires first, because they're the ones that you absolutely need to move to mitigate the business risk. *Technically*, about 2/3 of these wires would be fine if they stayed on the old pole, so you can wait to move them while you move the higher risk ones.

After a few days, you've gotten the high risk third of the wires moved over to the new pole. You verify that the entire system is operational, and it's working perfectly! You let out a sigh of relief: you've completed the hardest parts of this migration. All that's left now is moving the lower risk wires, removing the old pole, and finally getting into that awesome refactor of the new pole that you've been excited about this whole time.

{{< figure align=center src="images/after.jpg" caption="Middle of Project: doesn't look great, but it's a work in progress and actually functions ok temporarily." >}}

You let your manager know what your team has accomplished already and how smoothly it's gone. Your project is well ahead of schedule, but it's the end of the quarter at PG&E and your manager is looking for some good news to share with their bosses. They proudly report at the big End of Quarter Leadership Roundtable that all of the high risk work on your project is complete, and that you're about to kickoff the cleanup and refactoring phases of the project.

# Deprioritized
The next day, your manager schedules a meeting with you. The mood is tense, and they inform you that unfortunately your project has been deprioritized, effective immediately. What, how? It's not done! Your manager tells you that while they understand how great the cleanup and refactor was going to be, you've reached the point of the project that technically meets the Definition of Done in your initial proposal. The highest risk wires have been moved to the new utility pole and no longer pose significant risk. Also, the company unfortunately has had to reprioritize their focus on [putting out literal fires](https://www.pbs.org/newshour/nation/pge-to-pay-55-million-for-two-massive-california-wildfires) and doesn't have the budget right now for "unnecessary refactors."

You're really bummed out at this news. This project was just starting to get really interesting! Also, you take pride in the quality of your work, and to abandon this project as is, with TWO poles in the ground and wires on both, gives you a deep sense of shame.

{{< figure align=center src="images/after.jpg" caption="Project Completion: Terrible. [Just downright dogshit of a pole](https://twitter.com/spacetwinks/status/965428890830344193)." >}}

# Post Mortem
After a few days of sulking, you begin to reflect more on the situation. Leadership *is* right. The pole no longer poses a risk, and there are much higher priority issues that need to be addressed. The refactor you had been planning had the potential to be great, but not in a way that really helped the business. You swallow your pride and start to think about your next moves. You still did a good job on this project: you proposed a change to limit business risk, and implemented a solution ahead of schedule. The fact that it looks like it was built by a [spider on benzedrine](https://www.newscientist.com/article/mg14619750-500-spiders-on-speed-get-weaving/) doesn't actually matter or show up on any sorts of graphs or metrics that the organization sees. You switch your focus to helping your manager communicate how successful the project was, although they've informed you that since you didn't get to that technically impressive refactor, your promotion is probably going to have to be pushed back a couple of quarters. At the end of it all, you don't get a promotion but you get a solid performance review, and your manager thanks you privately for being a good team player.

# What's Next?
You try to think about what your next move should be. Leadership appears to be singularly focused on an exciting prototype that they've been testing out to trim trees, a ["heli-saw"](https://www.latimes.com/california/story/2022-03-02/pge-helicopter-saw-bay-area-park-safety-violations) comprised of [eight chainsaw blades suspended from a helicopter](https://www.youtube.com/watch?v=actkcr-KGpI). They've got a working prototype, but are looking to hand off to an infrastructure engineer like you to conduct a safety audit and productionalize it. You know that jumping on this project could be good for your career, but your true passion and expertise is in utility poles, and something about dangling chainsaws from helicopters close to power lines just seems a little risky to you.


{{< figure align=center src="images/helisaw.png" caption="[Fuck everything, we're doing ~~five~~ eight blades](https://www.theonion.com/fuck-everything-were-doing-five-blades-1819584036)" >}}

Can't you just keep working on utility poles? There's still a lot of good work there, but unfortunately your project was deemed so successful and repeatable that you've started to see double utility poles all over town. You drive over to check on your pole and [reflect](https://www.youtube.com/watch?v=BONhk-hbiXk). The person who lives in the house next to your pole sees your PG&E uniform and comes out to talk to you. He tells you that you put the new pole so close to his driveway that he can barely get out of his garage anymore. You want to apologize to him and explain the situation, and tell him it wasn't supposed to be like this. The refactor was going to include alterations to the sidewalk to give him a wider driveway on the other side of the pole. Plus, he was going to be living near the greatest god-damn utility pole in the history of humankind! That pole was going to be so good you might try to figure out if you could be buried under it when you die. But you realize that none of this story changes his situation, and that in this moment you are simply a representative of PG&E to him. You apologize for the inconvenience, tell him [we're all trying to find the guy who did this](https://pbs.twimg.com/media/EoXRIS9XMAIcRsb?format=jpg&name=900x900), and promise to report the issue to your manager and put fixing his driveway right at the top of the backlog. He thanks you and goes inside. You get back in your car, knowing his driveway is going to be like this forever.

{{< figure align=center src="images/repeatable process.jpg" caption="Copycat double poles, now with new innovations like \"not on the ground, actually.\"" >}}

Distraught, you consider leaving PG&E. They're going through a lot of problems right now, and there are [rumors of a takeover](https://calmatters.org/politics/2020/02/what-happens-if-california-takes-over-pge/) by a huge bureaucracy [known for its inefficiencies and mismanagement](https://en.wikipedia.org/wiki/California). You're worried that a takeover would cause for a really disruptive couple of years. Also, [the leader](https://en.wikipedia.org/wiki/Gavin_Newsom) doesn't seem to know much about utility companies, and seems to spend most of his time with celebrities and powerful people outside of his industry when he should probably be focused on governing. Also, even though everything he says and does is ostensibly liberal, something about him *really* makes you feel like he's a Republican.

{{< figure align=center src="images/newsom with celebs.jpg" caption="Governor Gavin Newsom hanging with celebrities instead of working" >}}

Still, you mostly like your job and love your team. A bunch of new graduates just joined, and they're really excited about utility pole work, just like you used to be! Their energy is contagious. You've been mentoring them as they do their own utility pole projects, and you end up finding it even more rewarding than working on utility poles directly. You encourage them to do refactoring and cleanup work continuously throughout the project, so that even if it's cut short they'll have improved the situation rather than making it worse. They argue that that's a less efficient way to do the work, but you smile and tell them your story and assure them [they'll thank you later](https://ih1.redbubble.net/image.1922178116.0850/st,small,507x507-pad,600x600,f8f8f8.jpg).


This is all speculation, of course! I don't know anything about PG&E or utility poles or how infrastructure work like this actually happens. I write software.
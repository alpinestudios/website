---
title: Resources

description: A collection of resources/tools I’ve come across over the years to aid in building games from scratch.
---

# How to make a game from scratch without dying of old age
There are an infinite amount of problems to solve.
Yet, only a handful of them will bring you closer to releasing a game.

If you're serious about wanting to ship a game from scratch (and aren't just here to dabble), then read on.

## Getting Started
I wish there were a simple (and actually good) game development from scratch course I could point you towards. But sadly nothing exists yet (that I'm aware of).

So you've got two options:

### option #1: Self-taught
Use these resources (and others you find online) to try and create your own curriculum. Learning as you go.
The downside to this, is that it's really easy to get overwhelmed since there's *a metric shitload* of information out there, and filtering what's useful / what isn't when it comes to getting to where you want to go is very difficult.
It's not impossible though. This is the path I took. It's taken me around 8 years to get to where I am today and I'm sure you can shortcut a lot of that with these resources.
But it won't be a walk in the park.

### option #2: Coaching
I don't have all the answers and there are a lot of areas I am sorely lacking in.
But I can teach you everything I know so that you can avoid all of the mistakes I've run into already.
I'll help you fast-track your way to where you want to go.
If you're interested, send me an email - contact at randy dot gg

## Self-taught
If you're deciding to go down this route. A good starting point for learning solid C fundamentals is https://guide.handmadehero.org/intro-to-c/
There's a lot of windows-specific stuff in there which *can be* useful to know (assuming you're on windows). For the most part though, skip over it and just focus on the fundamentals of C.

As a general rule of thumb, avoid all modern C++ like the plague and figure out how to do the equivalent thing (like std::string, or std::vector) with simple fundamentals (fixed length strings, or flat arrays).
sidenote: If you're coming from C++ and are leaning heavily on the standard library (like I was), I found that forcing myself into C was a really smart move.

Save yourself a couple of wasted years by never learning OOP and skipping straight to learning the fundamentals of computing.
If you're in the unfortunate position of having already learnt OOP (like myself), you will need to try your best to *unlearn* it.

Beyond simple programming, making an actual game in C is a whole beast in itself. And there isn't really any resources I know of that cover this from start to finish.

You can try working your way through some of Casey's Handmade Hero series - https://guide.handmadehero.org/
But with that you've got to be careful of catching "engine brain" and getting ratholed for years on *interesting tech challenges* that don't really amount to anything.
Exhibit A: https://www.youtube.com/watch?v=uVvZlH5gPAU

Beyond that. I don't have a good answer aside from just trial and error, while seeking as many mentors as possible and asking a fuck load of questions.
For that, here are some good places to do so:

Ryan's discord server https://www.rfleury.com/ (which'll probably require a $5/month investment to his Substack if you want to be nice)

Searching via the [Handmade hero episode guide](https://hero.handmade.network/episode/code) can be helpful.

If all else fails, the [Handmade Network Discord](https://handmade.network/).

Good luck, have fun!

---

The rest of this page is just loosely organise concepts which you might find useful.

## Memory Management
A nice video clip to intro to the overall issue: https://hero.handmade.network/episode/code/day626/#4408  

[Untangling Lifetimes: The Arena Allocator](https://www.rfleury.com/p/untangling-lifetimes-the-arena-allocator)  
[@](https://www.rfleury.com/i/70173682/arena-parameterization) good example of how arenas can be passed as parameters  
[@](https://www.rfleury.com/i/70173682/composition-with-more-complex-allocators) great example of a growable entity allocator with a free list  
[@](https://www.rfleury.com/i/70173682/per-thread-scratch-arenas) per-thread scratch arenas  

> "Learning how to work with arenas entirely revolutionized my experience with writing code in C. I almost never think about memory management, these days—it is not particularly more cumbersome than writing in a garbage-collected scripting language. Unlike such a language, however, I know where my memory is coming from, and when it’ll be “released”, and what that even means." - rjf

Solid written overview - https://www.gingerbill.org/article/2019/02/01/memory-allocation-strategies-001/  
Solid implementation walk-thru - https://www.gingerbill.org/article/2019/02/08/memory-allocation-strategies-002/  

## misc

[How I structure my entities](https://youtu.be/UolgW-Ff4bA)

[JBlow's extremely valuable cookbook for engine programming](https://www.youtube.com/playlist?list=PLmV5I2fxaiCI9IAdFmGChKbIbenqRMi6Z)  

[Sokol](https://github.com/floooh/sokol) for an easy and solid foundation (platform, input, sound, etc)  

https://easings.net/ - easing functions cheat sheet  

https://gafferongames.com/#posts - lots of goodies in here  

[John Carmack on Functional Programming](http://sevangelatos.com/john-carmack-on/)  

## graphics programming
If I were starting out, I'd just use [Sokol](https://github.com/floooh/sokol) with [sokol-gp](https://github.com/edubart/sokol_gp) instead of worrying about learning graphics programming straight away.  

When ready though...  

https://learnopengl.com/ - especially for the coordinate systems / transformation matrix explanations  

I just use d3d11 since I'm only targeting Windows on Steam since that's around ~98% of users. It simplifies things greatly. One target.  

d3d11 specific:  
http://www.directxtutorial.com/Lesson.aspx?lessonid=11-4-1 (solid fundamentals)  
https://graphicsprogramming.github.io/learnd3d11/ (might find something useful in here?)  
[basic setup example using the C API](https://gist.github.com/mmozeiko/5e727f845db182d468a34d524508ad5f#file-win32_d3d11-c-L4)  
[Minimal D3D11](https://gist.github.com/d7samurai/261c69490cce0620d0bfc93003cd1052)  
https://github.com/Microsoft/DirectXTK/wiki/Getting-Started - good for examples on the more advanced stuff (ignore the C++ cringe)  
[Shader examples](https://github.com/Microsoft/DirectXTK/tree/main/Src/Shaders)  
[HLSL reference](https://learn.microsoft.com/en-us/windows/win32/direct3dhlsl/dx-graphics-hlsl-reference)  
  
some fun - https://alaingalvan.gitbook.io/a-trip-through-the-graphics-pipeline/  

(for correctly mapping a texture without edge bleed)  
https://learn.microsoft.com/en-us/windows/win32/direct3d9/texture-coordinates
https://learn.microsoft.com/en-us/windows/win32/direct3d9/directly-mapping-texels-to-pixels

### lighting
[A better point light attenuation function](https://lisyarus.github.io/blog/graphics/2022/07/30/point-light-attenuation.html)  

## audio programming
[Lessons Learned from a Decade of Audio Programming](https://www.youtube.com/watch?v=Vjm--AqG04Y) is a banger  

[Introduction to Sound Mixing](https://guide.handmadehero.org/code/day139/)  
[@ -](https://guide.handmadehero.org/code/day139/#1834) mixing sounds together, clipping, modulation & interpolation, pitch  
implementation is in the following days [here](https://guide.handmadehero.org/code/) (from day 139)

https://tek256.com/posts/game-audio/ - decent overview of some of the terms wrt game dev  

[low pass filter](https://dobrian.github.io/cmp/topics/filters/lowpassfilter.html)  

## Ryan Fleury
Ryan deserves his own section because he's an absolute unit of a man.  

[His Substack](https://www.rfleury.com/) is a gold-mine. If you become a member, his community discord is a great place to ask questions and get sensible answers  
[UI Series](https://www.rfleury.com/p/ui-series-table-of-contents)  
[Confronting combinatorics](https://www.rfleury.com/i/54162175/confronting-combinatorics) - flags vs switches  

## Jai Programming
If you're in the beta, first just read the `how_to`  

then...  

[The Way to Jai](https://github.com/Ivo-Balbaert/The_Way_to_Jai) - great starting point  
[Jai Community Wiki](https://github.com/Jai-Community/Jai-Community-Library/wiki) - a great reference once finished with the `how_to`'s (and for finding stuff that isn't yet doucmented in them)  

### Jon Nuggets
[why RAII is bad](https://www.youtube.com/watch?v=uZgbKrDEzAs&t=603s)

on simply parsing a custom text file, found in `"jai\modules\Text_File_Handler\examples\example.jai"`
```
Here, we parse each line of the file. Many programmers in the modern day seem to be afraid
of parsing and fall back on huge libraries that don't even really solve the problem, and
end up giving them a bunch of extra work to do anyway, and that extra work may insidiously
worm its way throughout the program, increasing complexity of the program and reducing its
reliability. (See the typical large program that loads JSON files for an example of this).

In a modern programming language with powerful semantics and reasonable strings and good
compile-time and run-time checking, parsing simple things is pretty easy. It's much nicer
(and leads to more-solid programs) to do this than to try to load some generic uber-format
everywhere. Many people wearing Computer Science University hats will tell you this is
exactly backward, but they are exactly backward.
```

## networking shit
high level overview - https://pvigier.github.io/2019/09/08/beginner-guide-game-networking.html  

Don't bang your head against a wall trying to get around [NAT](https://tailscale.com/blog/how-nat-traversal-works/) from scratch, bang your head against a wall while using the [SteamAPI](https://partner.steamgames.com/doc/sdk/api) instead.  

great resource for learning socket fundamentals from scratch - https://beej.us/guide/bgnet/  

if you ever wanna go down the route of a netchad, here's *a lot* more concepts - https://beej.us/guide/bgnet0/

## multithreading
[Introduction to Multithreading](https://guide.handmadehero.org/code/day122)  
[Interlocked Operations](https://guide.handmadehero.org/code/day123/)  
[Memory barriers and semaphores](https://guide.handmadehero.org/code/day124/)  
^ this was enough to get me going with multithreading

## dump
most of this is unread and unsorted  

todo: make a proper linked list  
linked list stuff - https://fgiesen.wordpress.com/2010/09/27/data-structures-and-invariants/  
cycle detection - https://en.wikipedia.org/wiki/Cycle_detection#Floyd's_tortoise_and_hare  

animation stuff - https://www.youtube.com/watch?v=KPoeNZZ6H4s  

https://github.com/Angelo1211/HybridRenderingEngine#references  
[Parallel Computer Architecture and Programming](http://15418.courses.cs.cmu.edu/tsinghua2017/home  )  
[doom 2016 graphics study](https://www.adriancourreges.com/blog/2016/09/09/doom-2016-graphics-study/)  
  

https://gafferongames.com/post/networked_physics_2004/  
https://gafferongames.com/post/udp_vs_tcp/  
https://gafferongames.com/post/sending_and_receiving_packets/  
https://gafferongames.com/post/virtual_connection_over_udp/  
https://gafferongames.com/post/reliability_ordering_and_congestion_avoidance_over_udp/  
https://gafferongames.com/post/what_every_programmer_needs_to_know_about_game_networking/  

https://gafferongames.com/post/introduction_to_networked_physics/  
https://gafferongames.com/post/deterministic_lockstep/  
https://gafferongames.com/post/snapshot_interpolation/  
https://gafferongames.com/post/snapshot_compression/  
https://gafferongames.com/post/state_synchronization/  
https://gafferongames.com/post/networked_physics_in_virtual_reality/  

casey GJK:  
https://www.youtube.com/watch?v=SDS5gLSiLg0&t=2685s  
https://www.youtube.com/watch?v=Qupqu1xe7Io  
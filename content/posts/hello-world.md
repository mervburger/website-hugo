+++
date = '2024-11-30T21:18:46-05:00'
draft = false
title = 'Hello World'
+++
I wanted to go back to having the possibility of occasionally doing longer form writing online - partly to hedge my bets against continuing enshittification of the Internet as a whole (and I happen to possess the talents to be able to defend myself against it!) and to be able to make points that ~280 characters is not enough for. I had been thinking about utilizing my unused cohost account for such things, but that never happened, and then cohost announced its shut down. I didn't want to go back to managing a full-ass CMS like Wordpress or Drupal (or even a flat-file one like Grav,) but wanted something easier to manage than just writing straight HTML any time I had a thought, which is what would have been necessary with any of my previous iterations of my site.

I ended up trying out [Hugo](https://gohugo.io), a static site framework. I chose it for no particular reason, I just saw it mentioned in Discord chat, did a quick look over it, and it passed the initial smell test. I'm not familiar with SSGs and have never used them before, as all of my experience is either in just using a CMS, writing custom applications using a full-stack framework for larger needs, or by just writing things entirely from scratch for smaller ones. As such, a lot of the "benefits" touted by many SSGs fall flat for me - *fast build times? it's just HTML? i18n, for a personal site? huh???* I get that these are meant to pull in for larger sites and projects, but as someone that's used to doing things "old school," I just don't entirely "get it" - at least not yet. And maybe not ever! But that's okay!

Instead of getting lost in the weeds making a custom template, I just went with one of the ones listed on the Hugo site that matched the kind of look and vibe I want to go for now. As I get used to working with it more and more, I'll eventually dabble with it deeper - the advantage with Hugo is that it's based on, and heavily utilizes, Go, which I have had some interest in working with.

So why even bother making such a change? I've used Wordpress before, but the management overhead required for it is a pain, especially for a personal site, where I would prefer to be able to forget it and be able to safely do so. I manage a bunch of Drupal sites at my job, and I would prefer not to also do that in my personal time.

My more recent versions of my home page has been custom from scratch HTML and PHP, just written in a text editor - very old school stuff. There's a bit of time and effort to going with code from scratch, and you usually do *just enough* to meet the needs at the time, and any additions have to get hacked on later. My most version of a home page was just an index HTML file, some javascript for lols and images. I would have had to effectively entirely restructure it anyway to just add the ability to add new content, for a page I wasn't particularly fully attached to, anyway.

Using an SSG is designed with that from the get-go, so to add content is just as easy as putting the content in the appropriate location, build, and you're off. As an aside - I do appreciate Hugo's preference for [Markdown](https://en.wikipedia.org/wiki/Markdown) as its content format. It is by and large the most common way to format text online these days, and I can appreciate using the same stying methods I use elsewhere on the Internet on my own site, and there are plenty of editors that work natively with Markdown.

My old page would then be pushed to Github, and I would build a docker container with nginx to just serve the HTML, which gets into another problem - maintenance of it all. None of that was automatically deployed - I had a docker file that I manually ran to update when the code changed. I could have built a proper automation pipeline to build and deploy from Github for me, but I really didn't want to do this *and* figure out a solution for being able to easily occasionally add content.

My earlier sites were worse - old school FTP uploads which would break when the host decided that my occasional connection was "bot activity" and disable the account (side point: 1&1/IONOS is *really* bad about doing that.)

I'm still utilizing Github as my code storage and version control of choice, but I'm also leveraging it with Cloudflare Pages to build and host and do all the other stuff Cloudflare does. This means I'm no longer building and hosting my own server - though I still have stuff with Digital Ocean for hosting other needs and projects. Now when I do an update, all I have to do is write a new post, place the file in the appropriate location, push to Github, and then Cloudflare rebuilds with the new content. I can also use separate branches to do development testing and also get it hosted, with access control, too.

Hell, I don't even have to be at my computer with VSCode to do the push, the Github web interface gives me all the tools I need to be able to make updates, so I can make an update from a tablet or phone, too.

Choosing Cloudflare Pages was a bit intentional - I already use them for my domain name, so I'm already a bit familiar with their service, but I'm also not well-versed in everything they offer, either. I'll probably eventually leverage other Cloudflare features in the future to avoid some concerns I have with a Github to Cloudflare Pages pipeline, such as avoiding storing any images directly within Github, which is generally a bad idea.

Additionally, all of this is *new to me.* I didn't go out initially to go about things this way, but I decided that I liked the idea of utilizing solutions that are fairly unknown to me. By using something new I'm adding to my own toolbox of solutions that I can go into in the future.
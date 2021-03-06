---
title: "setting up a blog in 2022"
date: 2022-04-15T22:39:12+02:00
draft: false
---

the state of blogging software in 2022 is quite depressing in general.
it feels like not a lot has moved in the last couple of years, yet none of the existing solutions are really satisfying.
you mainly have the choice between two paths you can take: the full-blown-wysiwyg-self-integrated-platform or the minimalist-markdown-to-html-tool.
i've tried my hand at both for some time, so here's my notes.

# wysiwyg
### hosted solutions
there are a bunch of platforms like medium, but i greatly dislike the idea of companies making money with my content, so that wasn't an option.

### wordpress
you can say about wordpress what you like, but you have to admit it has reached quite the popularity. that is probably due to it being easy to set up, the size of the community, and its ease of use.
everyone can easily set up a wordpress blog with one of the millions of hosted wordpress providers and doesn't need to know anything about software to use it.
there are tons of good themes, and the integrated editor gives you a clear idea what your posts are gonna look like.
that being said though, since i have refuse to use php in 2022, it wasn't really an option for me.

### ghost
the second-biggest competitor is probably ghost.
let me start by saying it's clearly inferior to wordpress as it is virtually impossible to self-host. i guess the idea is making as much money as possible with the hosting services provided by the company behind ghost.
after trying a couple of different ways from their docs, i basically ended up running a pre-configured ec2 image for ghost.
that worked pretty well for basic features, but would not be amused at all when i tried to get an ssl certificate running (this was the same with all the setup options, btw).
setting the certificate, custom domain, etc up was quite easy, but ghost did *not* like me putting the _https_ in front of the hostname config option.
basically all the features where ghost would render a preview (for selecting a theme, changing menus, and so on) were broken.
i feel like after googling that issue for more than 5 minutes, it's safe to say there was no good solution. (this is a so-called pro-engineer move, btw)
it was also not clear why i couldn't disable the newsletter function fully, as it would still ask visitors to enter their email addresses.
i did like some visual aspects, like the editor and the themes, but felt like the headache of self-hosting it myself was just not worth that.


# static website generators
after heaving seen an increasing number of blogs on hackernews that were basically just a bunch of txt files, i finally gave up and decided to do the same.
### hugo
some of the biggest players in this area are gatsby and jekyll, but since react is a bit overkill when essentially rendering only text and ruby should be allowed to rest in its grave already, i decided to go with hugo for generating static websites from markdown files.
first off, it was surprisingly painless to set up, and it can be deployed and hosted in an automated way with github actions/github pages *for free*.
all of that was much better documented and easier to implement than with ghost.

on the negative side though, my editor is configured to write code, not write prose.
i will probably have to copy my blogposts over to some online grammar checking tool every time before i post them.
it's also not half as easy putting an image into posts, as i, for one, do not know markdown syntax by heart, so anything other than plain text requires a little extra effort. the UX of ghost wins in this aspect for just wasting less brain cycles.

on the list of good things, at least it's fast, easy to set up, supports ssl certificates, and i don't have to run stuff manually.

# summary
most of the viable options for fully integrated platforms win when it comes to UI/UX, but lose in terms of self hostability. here the small markdown static website generators can shine, although the visual aspects suffer.
in the end i went with hugo as it was the easiest to set up and host.

in an ideal scenario, i'd like to have a visual admin page that lets me select themes, write blog posts in a nice web editor, etc, but saves the outcome into files so i can enjoy the ease of hosting that comes with static website generators. as far as i know, such a tool does not exist.

![relatable meme](https://i.imgflip.com/2uzxes.jpg)

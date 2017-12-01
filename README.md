# ircdocs 'mission'

The 'ircdocs' group grew out of my frustration with IRC. Specifically, the IRC protocol's lack of a clear, concise archive that collected a bunch of information about it. In addition, the lack of clear, useful, and functional files that help new IRC developers write projects and software from scratch that interact with the protocol.

Along the way to creating this group, and while running it, I've been involved in and created a bunch of related projects that I think contribute to the value of the protocol, help store the history of it and similar. These are projects I'd like to see continued (or at least maintained) for a fairly long while.

Since my projects tend to be scattered around 4-5 different orgs, as well as my own personal repos, I figured collecting them all together in one place would be useful. If something happens to me, these are things that people might find useful to work on, pick up the maintainership of, and etc.

---

## Projects

Below are a collection of the different projects I work on and/or contribute to, and are stuff I think are worth working on. Along with each project is a short description, and probably also some rough direction I want to take them in going forward.


### Historical

These projects primarily, or in a large way, try to collect historical context for people digging into IRC's history.


#### Rough history/files section on ircdocs.horse

This section of the ircdocs.horse website contains and centralises some stuff written both lately and way back when: https://ircdocs.horse/history/

I'm planning to extend this out a fair bit, maybe make a roughly-dated browser of maps, files, etc released, and of course link to the below lists archive when I get it online.


#### Usenet / Mailing List archives

I've been collecting a bunch of mailing list and usenet archives, which I intend to collate together. I'm hoping to throw those online as `lists.ircdocs.horse`, but we'll see how those goes.

As I collect the raw archives I'll be uploading them to the [Internet Archive](https://archive.org/).


#### irc-archive

[Over here](https://github.com/irc-archive) lives the irc-archive org on Github. It roughly helps collect old IRC code, useful to keep updating and throwing new code on there so it's available somewhere at an good, easy place to reference and access.


#### irchelp

The ole' irchelp website's a bit dodgy at the moment. Missing files, etc. I've helped fix up the Jekyll layouts and all, but I've been meaning to either make some really-big PRs that fix up a bunch of stuff at once or possibly throw up a fork of it with the links/files fixed.

Probably won't actually do this, but depends on how the current maintainers of that site respond to the incoming PRs and all.


### Functional

These projects primarily assist implementors of IRC software today in various ways.


#### Specs/Info pages

Heh. Listing this as a 'project' feels a little half-assed, but the [specs](https://ircdocs.horse/specs/) and [info](https://ircdocs.horse/info/) pages on the ircdocs site are two things I want to keep up-to-date as more relevant and useful sites, links and archives come online around IRC.


#### Modern docs

The [Modern docs](https://modern.ircdocs.horse) are, as noted on the site, a rough update to the RFCs of old. The IRC protocol, specified in a descriptive way that documents what's out there and what I think is 'best practice' for new servers and clients (totally interoperating with both old clients and servers).

Important to keep working on this so that clients and servers have a definitive, modern reference to the core IRC protocol. As possible, look at pushing stuff to the IETF to actually get released as official standards so that we also catch the general IRC consumers more effectively.

On a related note, [this](https://gist.github.com/DanielOaks/9e0993d8666a4c99786db7558ef63f01) is a rough doc I wrote up after someone asked me to relicense the Modern docs above. I can't relicense others' work, but I license my own stuff under CC0.

**Note:** If you decide to work on, or even maintain these, I have a piece of advice. Don't do it because "hey it'd be cool to get my name on an IETF spec!". Not entirely, at least. Do it because you care about the protocol being well-documented.


#### IETF Internet-Drafts

The [irc-rfcs](https://github.com/DanielOaks/irc-rfcs) repo (and coincidentally, the actual [IDs themselves](https://tools.ietf.org/html/draft-oakley-irc-ctcp-01)) are something I'm experimenting with. Seeing whether the IETF's still interested in IRC and standardising it through their process.

Keep the doc updated, and when appropriate (when everything's actually consistent, etc) push it further up the IETF chain.


#### Definition Files

[defs.ircdocs.horse](https://defs.ircdocs.horse) is a very fun place. Detailing the conflicts, and helping clients (and servers) decide which numerics, modes, and other stuff to use in their implementations. Keep it up to date, do your best to have it reflect what's actually legitimately out there.

If possible, create new files to document stuff (such as the [client caps](https://defs.ircdocs.horse/defs/clientcaps.html) and [tags](https://defs.ircdocs.horse/defs/tags.html) documents that detail things outside the IRCv3 process and all).


#### Network Stats

Of course, [stats.ircdocs.horse](https://stats.ircdocs.horse). Useful statistics, public for everyone to see.

Add weighting based on user count, add customizable filtering, make it possible to correlate different data.

I haven't released the code or the source data files for this (the data files I won't be releasing to anyone as far as I'm concerned), but I should make the code and data lists available so people can continue it if bus factor comes into effect.


#### IRCv3 (in general)

IRCv3 is a great group that helps push the IRC protocol forwards. I currently do most of their website stuff and am a bit of a spec nerd. Maintain [the repo](https://github.com/ircv3/ircv3.github.io) and [the website](http://ircv3.net), and move the site to HTTPS using Netlify's open source plan at some point.


### Testing and Breaking

Files and software that help test and fuzz new bits of IRC software. New implementations are cool, but being able to check whether they comply with other existing implementations and having fuzzers/stress-testers to bash on your software and try to break it five ways from Sunday are always a good idea.


#### Parser Tests

Having a decent, standard, and very widely redistributable set of tests for IRC parsers to be checked against is great, amazing, awesome. I have one, a collection made up from Mozilla's tests, grawity's tests, and Sadie's tests [right here](https://github.com/DanielOaks/irc-parser-tests).

Continue finding better ways to make it useful, extend it to include other useful tests, etc.


#### irctest suite

Originally forked from ProgVal, [these tests](https://github.com/DanielOaks/irctest) are a natural extension of the parser tests above and perform high-level checks on the behaviour of various IRC clients and servers.

Keep adding new tests, use it to influence where the Modern docs go and use the Modern docs to influence these tests. Try to make sure that most every major IRCd out there passes these tests with flying colours so that if something fails, it's acting really bloody odd.


#### irc-stress-test

This is a cute little Go app that tries to connect way too many clients and break servers, or at least help you see where and why your servers slow down. [Here's the repo](https://github.com/DanielOaks/irc-stress-test).


### irc_fuzz.py

Little, simple fuzzer I wrote years and years ago, but still manages to find bugs! [Here it is](https://gist.github.com/DanielOaks/63ae611039cdf591dfa4).


### Reference Implementations

Heh, 'reference implementations'. Really, just software I develop that I think has value as a rough median of other real-world implementations, and source libraries that I think are useful to use as references.


#### GoshuIRC

The [GoshuIRC org](https://github.com/goshuirc) is a lot of where this lives. For example, it has [irc-go](https://github.com/goshuirc/irc-go), which is I think a set of decent modules for Go that are the essence of reference code. Highly-tested, etc.

There's also some other stuff on there, a Py lib I consider pretty good, a bot I haven't touched in ages, etc.


#### ircdog

Less a concrete reference implementation and more a useful testing tool, [ircdog](https://github.com/goshuirc/ircdog) helps debug raw protocol lines when full-blown clients might be a bit much. I use it a fair bit in my day-to-day testing and think it's pretty important to maintain and extend.


#### Oragono

Oragono is the rough reference server that I developed with a few other cool people. The website's [over here](https://oragono.io). Given that it implements a lot of IRCv3 extensions in tandem where most other bigger servers don't, I see it as the natural extension to [mammon](https://github.com/mammon-ircd) and think it's pretty worth continuing and all.


---

**License**

Consider this document under CC0 / public domain

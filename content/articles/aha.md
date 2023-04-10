---
title: "Increasing the number of Aha moments"
date: 2023-04-10T19:34:01+01:00
draft: false
---

### tl;dr
* Finding good information is tough. Especially when the tools we use for search prioritises ads and spam over high quality, authentic content.
* Youtube has recordings of many of the conference talks that I enjoy watching, however it can be difficult to find the ones that I might be interested in, with no easy way to search through only the conferences I'm interested in.
* [Let's Talk](https://letstalk.cachefault.com/) is a site created to help me search for relevant security talks when wanting to learn about a specific topic.

### Intro
Finding good information is tough. I often find myself needing to find out what the latest trends are in my industry.  Personally, I rely on recommendations from knowledgeable friends and colleagues, attending local meetups, conference talks, and security newsletters. Search engines used to feature quite high on that list, but it's become increasingly difficult to sift through SEO-optimized marketing pages that only lightly touch on the topic of interest. I'm not sure why this has been the case, but a charitable view may be that as one becomes more adept in a field, what it takes to find something that is noteworthy becomes more difficult...but who I'm a kidding.

Recently at work, I was part of a project where we wanted to improve our SAST scanning tooling. We were pretty much set on the tool we wanted to use but were also interested in other people's experiences integrating said tool in their company, what considerations they made, how they dealt with false positives, and what are some useful metrics they collected. Searching for this online mostly returned introductory articles from product companies on what SAST is, some pros and cons, wrapping the blog up with a sales pitch. YouTube was a bit better, where it seems that the number of views a video has has more weight in the video being pushed up the recommendation list, which occasionally brought up videos that were of interest.

### Security Conferences
Conference talks have personally always been a great resource for discovering interesting content and keeping a pulse on the InfoSec Industry. There are a couple of reasons why I think this has been the case for such a long time for me:
* Talks are typically first-hand accounts by practitioners who have worked on a specific problem, trying to answer a particular question, or were just taking unguided adventures into obscure areas of the field. This makes them feel authentic and relatable.
* Talks undergo a level of quality control during the selection process, which is typically overseen by review boards that reflect the community's interests.

Of course, there are some downsides to relying on conference talks as a source of information. One of the biggest being the time commitment. It can be frustrating to sit through a 45-minute talk only to realize afterwards that it wasn't what you were looking for. Additionally, unlike written materials, you can't really skim read a conference talk to get the gist of it.

YouTube is the platform of choice for hosting conference talks, so I surprised how I hardly got any hits from them when I had done my search earlier on SAST. I could search on a specific youtube channel, but I was more interested in being to search across a wide range of channels.

### Lets Talk

[Let's Talk](https://letstalk.cachefault.com/) is a site born from this frustration. 

What I needed was simple: a way to search for specific terms in transcripts from security talks. I have a preference for which conferences that I find consistently provide high-quality talks, so I also wanted to limit my search to only those conferences. I needed the talks to be skimmable, so access to the talk transcripts was needed, allowing me to get the surrounding text for search term hits and quickly dive into the topic or skip if not relevant.

The implementations details involved:
* pull talk titles, descriptions, and transcripts into a DB.
* Index data using [OSS search engine](https://github.com/meilisearch/meilisearch).
* Make the index searchable via web frontend.

After using it for a couple of months, it's definitely made me a bit happier - or atleast quicker in finding what I am looking for. When exploring a new topic, my workflow looks something like this:

1. Search for a topic  of interest on `Let's Talk`. e.g "GraphQL Security".
2. Read through descriptions and scroll through transcripts, skimming for what I'm looking for.
3. When finding something that perks my interest, click the video to view in youtube.
4. Search transcript in youtube to jump to the exact location.
5. watch for a video for a bit and have my "Aha" moment💡!

### Future Work

"Let's Talk" is a rudimentary implementation and meets my needs. However, there are some "improvements" that would be nice to have, such as jumping to a video timestamp directly by selecting it from the transcript or better navigation between search term hits. The biggest "aha" moment yet though is that we need better ways to get high-quality content that is better aligned with the needs of practitioners in a field, rather than those who have the power to buy enterprise products.





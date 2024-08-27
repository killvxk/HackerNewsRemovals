**UPDATE** (February 4, 2024): This is the discussion about this project on HN: [here](https://news.ycombinator.com/item?id=39230513). Please specifically read @dang's comment regarding the core assumption of this project: [here](https://news.ycombinator.com/item?id=39231537). On a personal note, the number of Stories removed yesterday (Saturday, February 3, 2024) was the lowest ever recorded by the service. This includes 2 duplicate Stories. As a side note, **in the list always check whether a Story is a duplicate or not**: this is a very reasonable reason for removal and unfortunately I have no way of automatically determining it in the service!

# Introduction

The purpose of this project is to try to understand the type and scale of the moderation of the Hacker News Front Page.

**NOTE**: I love Hacker News. I try to read it every day. In the case of OnnxStream ([here](https://news.ycombinator.com/item?id=37752632) for example), 95% of the comments were helpful and intelligent. I also understand that moderating a site with huge traffic and where users are basically anonymous must be a very difficult task.

Returning to the purpose of this project, from what I have been able to see, the "public" (i.e. observable from the outside) moderation of the Front Page consists of two main tools: modification of the title of a Story (voluntarily or involuntarily influencing its growth in terms of rank) or directly its removal.

Regarding the first type of moderation, an excellent [site](https://hackernewstitles.netlify.app/) is already available that tracks changes to Story titles. Here instead I will focus on the second type.

For the reasons explained in the "Why?" section below, I have developed a small application that logs all the Stories that are removed from the Front Page, for personal use. I later discovered that there is no tool/website that provides this type of information and I decided to make it public here. It was a difficult decision but my rationale is: is it better to have more transparency or less transparency?

If you know of a tool/website similar to this, please let me know: I will archive this repo or set it to private.

A possible very positive outcome for this project could be to have a list similar to this, but available directly among the [HN lists](https://news.ycombinator.com/lists). Or even to notify a user when a Story is penalized on the Front Page, perhaps indicating the number of flags and/or the reason, for example.

# Why?

<details>
<summary>Feel free to skip this part or click to expand</summary>

A friend of mine posted two Stories on Hacker News related to OnnxStream (31 days apart), the first related to SDXL Turbo support and the second related to TinyLlama and Mistral 7B support.

In the case of the [first](https://news.ycombinator.com/item?id=38646969), the Story was among the first on the Front Page, until its title was changed from "Stable Diffusion Turbo on a Raspberry Pi Zero 2 generates an image in 29 minutes" to "OnnxStream: Stable Diffusion XL 1.0 Base on a Raspberry Pi Zero 2". This effectively "killed" the Story. One user pointed out that the new title didn't reflect the spirit of the Story (thanks @practice9).

In the case of the [second](https://news.ycombinator.com/item?id=38991145), the Story was in third place on the Front Page, less than an hour after the submission. In this case it was simply removed from the Front Page.

Having discovered this, perplexed, I sent an email to the moderator. @dang, who was very kind and quick in his response, explained to me that the Story had been flagged by users even without being explicitly [flagged], and that he could therefore only hypothesize the causes of the flag. His hypothesis was that (some?) users might be fed up with news related to LLMs.

While I have no reason to doubt Daniel's good faith, it's hard to believe that HN users would be tired of LLM-related news.

So I decided to develop a small console application to determine the frequency of this phenomenon (actually I was also motivated by the prospect of writing some C# code, after more than 2 years of complete abstinence). I subsequently discovered that there were no tools/websites that monitored this specific phenomenon and I therefore decided to make it public here.

</details>

# How it works

Using the [official HN API](https://github.com/HackerNews/API), the service fetches 90 Top Stories every minute and makes a comparison with the first 30 Top Stories (i.e. the Front Page) fetched the previous minute. It logs all missing Stories here. The assumption is that a Story cannot go from the top 30 to a position greater than 90 in a single minute, without having been explicitly removed. If a Story reappears on the Front Page, it is removed from this log. All Stories present in the [second-chance pool](https://news.ycombinator.com/pool) are excluded from the log. Title and URL are those from when the Story first appeared in the top 30. The number of points and comments and the rank are those from when the Story was removed from the Front Page. The ID points to the [news.social-protocols.org](https://news.social-protocols.org) page for that Story, which provides a graph of the Story's position on the Front Page over time.

# The list (updated in real time, max delay: 1 minute)

**NOTE**: always check whether a Story is a duplicate or not: this is a very reasonable reason for removal and unfortunately I have no way of automatically determining it in the service!

#### **Wednesday, August 21, 2024**
<!-- HN:41305166:start -->
* [41305166](https://news.social-protocols.org/stats?id=41305166) #3 9 points 4 comments -> [Uncensored AI: a fine tune of Llama 405B – no more PC nonsense](https://www.aiuncensored.info/uncensored)<!-- HN:41305166:end --><!-- HN:41305936:start -->
* [41305936](https://news.social-protocols.org/stats?id=41305936) #4 6 points 2 comments -> [High school shuts down its library because of book-banning state law](https://www.lgbtqnation.com/2024/08/high-school-shuts-down-its-library-because-of-book-banning-state-law/)<!-- HN:41305936:end --><!-- HN:41256266:start -->
* [41256266](https://news.social-protocols.org/stats?id=41256266) #4 24 points 3 comments -> [3D Cellular Automata](https://williamyang98.github.io/3D-Cellular-Automata/)<!-- HN:41256266:end --><!-- HN:41306664:start -->
* [41306664](https://news.social-protocols.org/stats?id=41306664) #26 10 points 2 comments -> [The Decay of Boeing](https://brief.bismarckanalysis.com/p/the-decay-of-boeing)<!-- HN:41306664:end --><!-- HN:41306978:start -->
* [41306978](https://news.social-protocols.org/stats?id=41306978) #21 45 points 40 comments -> [Sonos CEO says the old app can't be rereleased](https://www.theverge.com/2024/8/20/24224754/sonos-ceo-old-s2-app-re-release-cant-be)<!-- HN:41306978:end --><!-- HN:41309022:start -->
* [41309022](https://news.social-protocols.org/stats?id=41309022) #17 4 points 0 comments -> [Worse Is Better](https://en.wikipedia.org/wiki/Worse_is_better)<!-- HN:41309022:end --><!-- HN:41306332:start -->
* [41306332](https://news.social-protocols.org/stats?id=41306332) #18 35 points 10 comments -> [How I started blogging (2024)](https://roarepally.com/blog/why-I-blog)<!-- HN:41306332:end --><!-- HN:41311553:start -->
* [41311553](https://news.social-protocols.org/stats?id=41311553) #4 11 points 6 comments -> [MIT undergraduate admissions in the wake of the 2023 Supreme Court ruling](https://news.mit.edu/2024/qa-undergraduate-admissions-in-wake-of-supreme-court-ruling-0821)<!-- HN:41311553:end --><!-- HN:41308038:start -->
* [41308038](https://news.social-protocols.org/stats?id=41308038) #20 56 points 40 comments -> [ScreenPlay Is an Open Source Live-Wallpaper App for Windows and OS X](https://screen-play.app/)<!-- HN:41308038:end --><!-- HN:41311461:start -->
* [41311461](https://news.social-protocols.org/stats?id=41311461) #29 53 points 14 comments -> [Russia: Citizens must turn off home surveillance because Ukrainians are coming](https://www.theregister.com/2024/08/21/russia_memo_ukraine_invasion/)<!-- HN:41311461:end --><!-- HN:41313619:start -->
* [41313619](https://news.social-protocols.org/stats?id=41313619) #25 5 points 4 comments -> [.less: Crafting .less Docker Containers That Will Blow Your Mind](https://pointlesscode.dev/)<!-- HN:41313619:end --><!-- HN:41314453:start -->
* [41314453](https://news.social-protocols.org/stats?id=41314453) #20 22 points 41 comments -> [New anti-speeding system coming to Australia is dangerous](https://www.carexpert.com.au/opinion/new-anti-speeding-system-coming-to-australia-is-dangerous)<!-- HN:41314453:end -->
#### **Thursday, August 22, 2024**
<!-- HN:41267412:start -->
* [41267412](https://news.social-protocols.org/stats?id=41267412) #2 85 points 30 comments -> [Py5, a Python version of Processing for your creative coding projects](http://py5coding.org/index.html)<!-- HN:41267412:end --><!-- HN:41271783:start -->
* [41271783](https://news.social-protocols.org/stats?id=41271783) #3 35 points 12 comments -> [Ren'Py](https://github.com/renpy/renpy)<!-- HN:41271783:end --><!-- HN:41263876:start -->
* [41263876](https://news.social-protocols.org/stats?id=41263876) #7 154 points 28 comments -> [Better Living Through Algorithms (2023)](https://clarkesworldmagazine.com/kritzer_05_23/)<!-- HN:41263876:end --><!-- HN:41268126:start -->
* [41268126](https://news.social-protocols.org/stats?id=41268126) #15 15 points 3 comments -> [Underware, open source 3D-printed cable management](https://handsonkatie.com/underware/)<!-- HN:41268126:end --><!-- HN:41271139:start -->
* [41271139](https://news.social-protocols.org/stats?id=41271139) #28 30 points 8 comments -> [Unhygienic and referentially opaque macros with Scheme syntax-rules [pdf] (2013)](https://okmij.org/ftp/Scheme/Dirty-Macros.pdf)<!-- HN:41271139:end --><!-- HN:41316029:start -->
* [41316029](https://news.social-protocols.org/stats?id=41316029) #15 6 points 10 comments -> [Never enable 2FA for accounts that you actually care about (2023)](https://benwilber.github.io/2023/07/17/never-enable-2fa-for-accounts-you-actually-care-about.html)<!-- HN:41316029:end --><!-- HN:41318127:start -->
* [41318127](https://news.social-protocols.org/stats?id=41318127) #21 42 points 40 comments -> [Starbucks' new CEO will supercommute 1k miles from California to Seattle](https://www.cnbc.com/2024/08/20/starbucks-new-ceo-brian-niccol-will-supercommute-to-seattle-instead-of-relocating.html)<!-- HN:41318127:end --><!-- HN:41318806:start -->
* [41318806](https://news.social-protocols.org/stats?id=41318806) #16 9 points 1 comments -> [Causal effect of video gaming on mental well-being in Japan 2020–2022](https://www.nature.com/articles/s41562-024-01948-y)<!-- HN:41318806:end --><!-- HN:41318975:start -->
* [41318975](https://news.social-protocols.org/stats?id=41318975) #13 7 points 2 comments -> [USAF's Quicksink weapon tears a ship in half in seconds](https://newatlas.com/military/quicksink-modular-strap-on-kit-smart-bomb/)<!-- HN:41318975:end --><!-- HN:41319012:start -->
* [41319012](https://news.social-protocols.org/stats?id=41319012) #21 8 points 3 comments -> [Dad hacks database to fake death and avoid child support pay](https://www.bbc.co.uk/news/articles/cgrj9r5qpego)<!-- HN:41319012:end --><!-- HN:41318330:start -->
* [41318330](https://news.social-protocols.org/stats?id=41318330) #13 7 points 1 comments -> [Show HN: Sonarr – automate finding, downloading, and managing TV shows](https://github.com/Sonarr/Sonarr)<!-- HN:41318330:end --><!-- HN:41315415:start -->
* [41315415](https://news.social-protocols.org/stats?id=41315415) #26 54 points 40 comments -> [Windows 11 tweaks and usability improvements](https://kittenlabs.de/blog/2024/08/20/windows-11-tweaks-usability-improvements/)<!-- HN:41315415:end --><!-- HN:41319477:start -->
* [41319477](https://news.social-protocols.org/stats?id=41319477) #13 6 points 1 comments -> [Show HN: Track project ETAs and statuses based on due date with this Jira App](https://easyestimate.app/)<!-- HN:41319477:end --><!-- HN:41319973:start -->
* [41319973](https://news.social-protocols.org/stats?id=41319973) #19 20 points 0 comments -> [eBay just charged me a $1.02 fee on an item I sold for $0.99](https://mastodon.social/@nfriedly/113005868074504264)<!-- HN:41319973:end --><!-- HN:41320937:start -->
* [41320937](https://news.social-protocols.org/stats?id=41320937) #12 6 points 1 comments -> [How Costco Hacked the American Shopping Psyche](https://www.nytimes.com/2024/08/20/dining/costco.html)<!-- HN:41320937:end --><!-- HN:41321292:start -->
* [41321292](https://news.social-protocols.org/stats?id=41321292) #8 9 points 3 comments -> [Xkcd Game Theory Question](https://blog.plover.com/2024/08/22#xkcd-game-theory)<!-- HN:41321292:end --><!-- HN:41275395:start -->
* [41275395](https://news.social-protocols.org/stats?id=41275395) #18 60 points 24 comments -> [Code as Art](https://www.awwsmm.com/blog/code-as-art)<!-- HN:41275395:end --><!-- HN:41319996:start -->
* [41319996](https://news.social-protocols.org/stats?id=41319996) #29 12 points 0 comments -> [Texas Instruments to Get $1.6B in Federal Funding for US Chip Plants](https://uk.pcmag.com/processors/153918/texas-instruments-to-get-16-billion-in-federal-funding-for-us-chip-plants)<!-- HN:41319996:end --><!-- HN:41321960:start -->
* [41321960](https://news.social-protocols.org/stats?id=41321960) #5 3 points 1 comments -> [Why is this a research paper? HybridRAG = VectorRAG context and GraphRAG context](https://arxiv.org/abs/2408.04948)<!-- HN:41321960:end --><!-- HN:41321938:start -->
* [41321938](https://news.social-protocols.org/stats?id=41321938) #28 4 points 0 comments -> [Intel Further Speeds Up Strnlen() in the GNU C Library for Recent Intel/AMD CPUs](https://www.phoronix.com/news/Intel-EVEX-Faster-strnlen)<!-- HN:41321938:end --><!-- HN:41321881:start -->
* [41321881](https://news.social-protocols.org/stats?id=41321881) #25 15 points 15 comments -> [NASA says data will guide whether astronauts return on troubled Starliner](https://www.washingtonpost.com/technology/2024/08/22/boeing-starliner-nasa-astronauts-dragon-spacex/)<!-- HN:41321881:end --><!-- HN:41321467:start -->
* [41321467](https://news.social-protocols.org/stats?id=41321467) #30 24 points 40 comments -> [Japan's Public Didn't Buy Fumio Kishida's New Capitalism](https://foreignpolicy.com/2024/08/15/japan-fumio-kishida-departure-capitalism-liberal-democratic-party/)<!-- HN:41321467:end --><!-- HN:41322548:start -->
* [41322548](https://news.social-protocols.org/stats?id=41322548) #29 43 points 27 comments -> [Venezuela's Supreme Court certifies Maduro's claims he won presidential election](https://www.ctvnews.ca/world/venezuela-s-supreme-court-certifies-maduro-s-claims-that-he-won-presidential-election-1.7010540)<!-- HN:41322548:end --><!-- HN:41324059:start -->
* [41324059](https://news.social-protocols.org/stats?id=41324059) #21 6 points 2 comments -> [Peloton announces $95 "used equipment activation fee"](https://arstechnica.com/gadgets/2024/08/peloton-announces-95-used-equipment-activation-fee/)<!-- HN:41324059:end --><!-- HN:41323925:start -->
* [41323925](https://news.social-protocols.org/stats?id=41323925) #25 7 points 0 comments -> [Problem with Rescuing Stranded Astronauts: Spacesuits Aren't Compatible](https://futurism.com/stranded-astronauts-spacex-boeing-spacesuits-incompatible)<!-- HN:41323925:end --><!-- HN:41324271:start -->
* [41324271](https://news.social-protocols.org/stats?id=41324271) #30 3 points 0 comments -> [More than 8 in 10 recruiters say they post 'Ghost jobs'](https://fortune.com/2024/08/19/recruiters-posting-ghost-jobs-problem-job-seekers/)<!-- HN:41324271:end --><!-- HN:41325199:start -->
* [41325199](https://news.social-protocols.org/stats?id=41325199) #30 5 points 0 comments -> [Starlink Now Being Deployed on U.S. Navy Warships](https://www.twz.com/sea/starlink-now-being-deployed-on-u-s-navy-warships)<!-- HN:41325199:end -->
#### **Friday, August 23, 2024**
<!-- HN:41282181:start -->
* [41282181](https://news.social-protocols.org/stats?id=41282181) #3 280 points 60 comments -> [Notris: A Tetris clone for the PlayStation 1](https://github.com/jbreckmckye/notris)<!-- HN:41282181:end --><!-- HN:41276809:start -->
* [41276809](https://news.social-protocols.org/stats?id=41276809) #7 80 points 35 comments -> [Batteryless OP-1](https://shred.zone/cilla/page/503/batteryless-op-1.html)<!-- HN:41276809:end --><!-- HN:41282419:start -->
* [41282419](https://news.social-protocols.org/stats?id=41282419) #13 12 points 2 comments -> [Rare yet Impactful – Orthographic Projection in Films and Animations](https://www.cined.com/rare-yet-impactful-orthographic-projection-in-films-and-animations/)<!-- HN:41282419:end --><!-- HN:41326244:start -->
* [41326244](https://news.social-protocols.org/stats?id=41326244) #18 6 points 3 comments -> [ShipFast alternative, Next.js SaaS Boilerplate and Starter Kit](https://play.nextjstemplates.com/)<!-- HN:41326244:end --><!-- HN:41329283:start -->
* [41329283](https://news.social-protocols.org/stats?id=41329283) #7 7 points 2 comments -> [Men don't hug their kids](https://papanotes.com/men-dont-hug-their-kids)<!-- HN:41329283:end --><!-- HN:41329433:start -->
* [41329433](https://news.social-protocols.org/stats?id=41329433) #27 6 points 1 comments -> [Putin's Media Coverage Suffers in Aftermath of Ukrainian Counteroffensive](https://newsletters.filterlabs.ai/putins-media-coverage-suffers-in-aftermath-of-ukrainian-counteroffensive/)<!-- HN:41329433:end --><!-- HN:41331987:start -->
* [41331987](https://news.social-protocols.org/stats?id=41331987) #17 22 points 42 comments -> [As cars and trucks get bigger and taller, lawmakers look to protect pedestrians](https://www.npr.org/2024/08/23/nx-s1-5084276/pedestrian-protection-bill-bigger-cars-trucks)<!-- HN:41331987:end --><!-- HN:41332192:start -->
* [41332192](https://news.social-protocols.org/stats?id=41332192) #22 10 points 2 comments -> [Stanford Reverses Cognitive Decline in Alzheimer's with Brain Metabolism Drug](https://scitechdaily.com/stanford-reverses-cognitive-decline-in-alzheimers-with-brain-metabolism-drug/)<!-- HN:41332192:end --><!-- HN:41332576:start -->
* [41332576](https://news.social-protocols.org/stats?id=41332576) #23 7 points 0 comments -> [AI could be a game changer for people with disabilities](https://www.technologyreview.com/2024/08/23/1096607/ai-people-with-disabilities-accessibility/)<!-- HN:41332576:end --><!-- HN:41332273:start -->
* [41332273](https://news.social-protocols.org/stats?id=41332273) #22 4 points 0 comments -> [Kansas judge dismisses machine gun case after SCOTUS gun rights ruling](https://www.cjonline.com/story/news/politics/courts/2024/08/22/kansas-judge-dismisses-machine-gun-case-after-scotus-gun-rights-ruling/74903536007/)<!-- HN:41332273:end --><!-- HN:41333347:start -->
* [41333347](https://news.social-protocols.org/stats?id=41333347) #1 -> [Israeli society's dehumanization of Palestinians is now absolute](https://www.972mag.com/dehumanization-moral-abyss-israelis/)<!-- HN:41333347:end --><!-- HN:41332605:start -->
* [41332605](https://news.social-protocols.org/stats?id=41332605) #14 16 points 5 comments -> [The AI Arms Race Isn't Inevitable](https://www.palladiummag.com/2024/08/23/the-ai-arms-race-isnt-inevitable/)<!-- HN:41332605:end -->
#### **Saturday, August 24, 2024**
<!-- HN:41334954:start -->
* [41334954](https://news.social-protocols.org/stats?id=41334954) #29 8 points 2 comments -> [MIT's first freshman class since affirmative-action ban is less diverse](https://www.bbc.com/news/articles/c8rxvd2z6ldo)<!-- HN:41334954:end --><!-- HN:41332338:start -->
* [41332338](https://news.social-protocols.org/stats?id=41332338) #11 69 points 50 comments -> [Wcurl Is Here](https://daniel.haxx.se/blog/2024/07/03/wcurl-is-here/)<!-- HN:41332338:end --><!-- HN:41335176:start -->
* [41335176](https://news.social-protocols.org/stats?id=41335176) #18 2 points 0 comments -> [Kraken-Bay: media hosting server with multiple features and a Netflix-like UI](https://github.com/PetitPrinc3/Kraken-Bay)<!-- HN:41335176:end --><!-- HN:41336620:start -->
* [41336620](https://news.social-protocols.org/stats?id=41336620) #3 7 points 5 comments -> [Clarifying the structure and nature of left-wing authoritarianism](https://digest.bps.org.uk/2021/10/01/left-wing-authoritarianism-is-real-and-needs-to-be-taken-seriously-in-political-psychology-study-argues/)<!-- HN:41336620:end --><!-- HN:41336775:start -->
* [41336775](https://news.social-protocols.org/stats?id=41336775) #28 12 points 4 comments -> [I automatically applied 1000 jobs in 24h and got 50 interviews (using AI BOT)](https://old.reddit.com/r/OpenAI/comments/1ezzmew/automatically_applied_1000_jobs_in_24h_and_got_50/)<!-- HN:41336775:end --><!-- HN:41338148:start -->
* [41338148](https://news.social-protocols.org/stats?id=41338148) #19 9 points 0 comments -> [Warren Buffet's Missed Opportunity](https://www.city-journal.org/article/warren-buffetts-missed-opportunity)<!-- HN:41338148:end --><!-- HN:41338120:start -->
* [41338120](https://news.social-protocols.org/stats?id=41338120) #12 11 points 0 comments -> [SCOTUS could deal another blow to climate action](https://www.theverge.com/2024/8/23/24226042/scotus-epa-clean-power-coal-plants-pause-rule)<!-- HN:41338120:end --><!-- HN:41338040:start -->
* [41338040](https://news.social-protocols.org/stats?id=41338040) #22 7 points 1 comments -> [Lego's Concorde is the only supersonic jet you can affordably build](https://www.theregister.com/2024/08/24/lego_concorde/)<!-- HN:41338040:end --><!-- HN:41339925:start -->
* [41339925](https://news.social-protocols.org/stats?id=41339925) #29 4 points 0 comments -> [Striking Is in the Air at Boeing](https://labornotes.org/2024/08/striking-air-boeing)<!-- HN:41339925:end --><!-- HN:41339537:start -->
* [41339537](https://news.social-protocols.org/stats?id=41339537) #25 7 points 2 comments -> [Biorecap: An R package for summarizing bioRxiv preprints with a local LLM](https://blog.stephenturner.us/p/biorecap-r-package-for-summarizing-biorxiv-preprints-local-llm)<!-- HN:41339537:end --><!-- HN:41341523:start -->
* [41341523](https://news.social-protocols.org/stats?id=41341523) #29 5 points 0 comments -> [Pavel Durov Arrested](https://www.timesnownews.com/world/telegram-founder-pavel-durov-arrested-in-france-andrew-tate-reveals-article-112770168)<!-- HN:41341523:end --><!-- HN:41341508:start -->
* [41341508](https://news.social-protocols.org/stats?id=41341508) #30 5 points 0 comments -> [CEO of Telegram, Pavel Durov, Arrested](https://twitter.com/xakpc/status/1827446852121231700)<!-- HN:41341508:end --><!-- HN:41306555:start -->
* [41306555](https://news.social-protocols.org/stats?id=41306555) #27 5 points 2 comments -> [Exploring Impact of Code in Pre-Training](https://arxiv.org/abs/2408.10914)<!-- HN:41306555:end --><!-- HN:41341427:start -->
* [41341427](https://news.social-protocols.org/stats?id=41341427) #23 55 points 2 comments -> [Founder and CEO of Telegram Pavel Durov Arrested in France at the Airport](https://twitter.com/igorsushko/status/1827448480693948673)<!-- HN:41341427:end -->
#### **Sunday, August 25, 2024**
<!-- HN:41339885:start -->
* [41339885](https://news.social-protocols.org/stats?id=41339885) #21 192 points 2 comments -> [NASA Decides to Bring Starliner Spacecraft Back to Earth Without Crew](https://www.nasa.gov/news-release/nasa-decides-to-bring-starliner-spacecraft-back-to-earth-without-crew/)<!-- HN:41339885:end --><!-- HN:41343308:start -->
* [41343308](https://news.social-protocols.org/stats?id=41343308) #4 10 points 3 comments -> [Le fondateur et PDG de la messagerie Telegram interpellé en France](https://www.tf1info.fr/justice-faits-divers/info-tf1-lci-le-fondateur-et-pdg-de-la-messagerie-cryptee-telegram-interpelle-en-france-2316072.html)<!-- HN:41343308:end --><!-- HN:41345989:start -->
* [41345989](https://news.social-protocols.org/stats?id=41345989) #9 17 points 14 comments -> [Why fans of nuclear are a problem today](https://jeromeaparis.substack.com/p/why-fans-of-nuclear-are-a-problem)<!-- HN:41345989:end --><!-- HN:41346156:start -->
* [41346156](https://news.social-protocols.org/stats?id=41346156) #22 24 points 4 comments -> [Show HN: Cursor AI Rules Directory (Open Source)](https://cursor.directory)<!-- HN:41346156:end --><!-- HN:41324086:start -->
* [41324086](https://news.social-protocols.org/stats?id=41324086) #14 7 points 1 comments -> [Lessons in Mannerism at the Palazzo Del Te](https://daily.jstor.org/lessons-in-mannerism-at-the-palazzo-del-te/)<!-- HN:41324086:end --><!-- HN:41350992:start -->
* [41350992](https://news.social-protocols.org/stats?id=41350992) #12 5 points 1 comments -> [Fermi Resonance and the Quantum Mechanical Basis of Global Warming](https://iopscience.iop.org/article/10.3847/PSJ/ad226d)<!-- HN:41350992:end --><!-- HN:41351844:start -->
* [41351844](https://news.social-protocols.org/stats?id=41351844) #26 35 points 28 comments -> [San Francisco officials weigh in on departure of X headquarters: 'Good riddance'](https://nypost.com/2024/08/25/us-news/san-francisco-officials-weigh-in-on-departure-of-musks-x-good-riddance/)<!-- HN:41351844:end -->
#### **Monday, August 26, 2024**
<!-- HN:41353390:start -->
* [41353390](https://news.social-protocols.org/stats?id=41353390) #17 9 points 3 comments -> [Yes, Crypto Is All a Scam](https://www.stephendiehl.com/blog/crypto-is-a-scam.html)<!-- HN:41353390:end --><!-- HN:41354083:start -->
* [41354083](https://news.social-protocols.org/stats?id=41354083) #8 13 points 6 comments -> [Sam Altman doesn't care about you](https://disconnect.blog/sam-altman-doesnt-care-about-you/)<!-- HN:41354083:end --><!-- HN:41353155:start -->
* [41353155](https://news.social-protocols.org/stats?id=41353155) #9 133 points 56 comments -> [Senior Intel CPU architects splinter to develop RISC-V processors](https://www.tomshardware.com/tech-industry/senior-intel-cpu-architects-splinter-to-develop-risc-v-processors-veterans-establish-aheadcomputing)<!-- HN:41353155:end --><!-- HN:41354830:start -->
* [41354830](https://news.social-protocols.org/stats?id=41354830) #11 11 points 5 comments -> [Four Stages of Competence](https://en.wikipedia.org/wiki/Four_stages_of_competence)<!-- HN:41354830:end --><!-- HN:41350530:start -->
* [41350530](https://news.social-protocols.org/stats?id=41350530) #11 527 points 475 comments -> [Is Telegram really an encrypted messaging app?](https://blog.cryptographyengineering.com/2024/08/25/telegram-is-not-really-an-encrypted-messaging-app/)<!-- HN:41350530:end --><!-- HN:41313861:start -->
* [41313861](https://news.social-protocols.org/stats?id=41313861) #17 84 points 8 comments -> [A Comparison of Arenas in Rust](https://donsz.nl/blog/arenas/)<!-- HN:41313861:end --><!-- HN:41353330:start -->
* [41353330](https://news.social-protocols.org/stats?id=41353330) #19 75 points 16 comments -> [Open-Source Cola](https://en.wikipedia.org/wiki/Open-source_cola)<!-- HN:41353330:end --><!-- HN:41353284:start -->
* [41353284](https://news.social-protocols.org/stats?id=41353284) #26 150 points 53 comments -> [Server Setup Basics for Self Hosting](https://becomesovran.com/blog/server-setup-basics.html)<!-- HN:41353284:end --><!-- HN:41354021:start -->
* [41354021](https://news.social-protocols.org/stats?id=41354021) #26 5 points 2 comments -> [Association of the "Weekend Warrior" Physical Activity Patterns with Mortality](https://jamanetwork.com/journals/jamainternalmedicine/fullarticle/2794038)<!-- HN:41354021:end --><!-- HN:41355079:start -->
* [41355079](https://news.social-protocols.org/stats?id=41355079) #2 8 points 0 comments -> [Investing for Anyone: a low-stress and effective way to invest your savings](https://blog.strnisa.com/p/investing-for-anyone)<!-- HN:41355079:end --><!-- HN:41356248:start -->
* [41356248](https://news.social-protocols.org/stats?id=41356248) #2 15 points 6 comments -> [Danish government will shut down encrypted messaging (including via blocking)](https://www.version2.dk/artikel/minister-vil-lukke-krypterede-beskeder-ned-professor-kalder-det-ekstremt-vidtgaaende)<!-- HN:41356248:end --><!-- HN:41333369:start -->
* [41333369](https://news.social-protocols.org/stats?id=41333369) #20 10 points 17 comments -> [Show HN: Play this game to prove your humanity against AI](https://playandsurvive.vercel.app/)<!-- HN:41333369:end --><!-- HN:41352055:start -->
* [41352055](https://news.social-protocols.org/stats?id=41352055) #19 38 points 4 comments -> [Bootstrap a Linux system from a 512 byte binary seed with 170 steps](https://github.com/fosslinux/live-bootstrap/blob/master/parts.rst)<!-- HN:41352055:end --><!-- HN:41350151:start -->
* [41350151](https://news.social-protocols.org/stats?id=41350151) #19 86 points 7 comments -> [An AWS IAM Security Tooling Reference](https://ramimac.me/aws-iam-tools-2024)<!-- HN:41350151:end --><!-- HN:41337540:start -->
* [41337540](https://news.social-protocols.org/stats?id=41337540) #11 9 points 0 comments -> [Database in the Browser, a Spec](https://www.instantdb.com/essays/db_browser)<!-- HN:41337540:end --><!-- HN:41357817:start -->
* [41357817](https://news.social-protocols.org/stats?id=41357817) #25 3 points 1 comments -> [NASA will bring stranded astronauts back on SpaceX – not Boeing's Starliner](https://www.npr.org/2024/08/24/nx-s1-5087892/nasa-starliner-astronaut-return-iss-spacex)<!-- HN:41357817:end --><!-- HN:41357609:start -->
* [41357609](https://news.social-protocols.org/stats?id=41357609) #7 9 points 3 comments -> [The Mystics of Progress](https://isaacyoung.substack.com/p/the-mystics-of-progress)<!-- HN:41357609:end --><!-- HN:41357920:start -->
* [41357920](https://news.social-protocols.org/stats?id=41357920) #24 4 points 0 comments -> [P. boydii – Deadly fungus lacking antimycotic treatment](https://en.wikipedia.org/wiki/Pseudallescheria_boydii)<!-- HN:41357920:end --><!-- HN:41358327:start -->
* [41358327](https://news.social-protocols.org/stats?id=41358327) #20 27 points 22 comments -> [A Massachusetts town closes its parks to stop a mosquito-borne disease](https://www.npr.org/2024/08/26/nx-s1-5089737/massachusetts-mosquito-disease-parks-fatal)<!-- HN:41358327:end --><!-- HN:41335770:start -->
* [41335770](https://news.social-protocols.org/stats?id=41335770) #6 15 points 0 comments -> [Guy Davenport–The Last High Modernist](https://www.thenation.com/article/culture/guy-davenport-geography-imagination/)<!-- HN:41335770:end --><!-- HN:41359311:start -->
* [41359311](https://news.social-protocols.org/stats?id=41359311) #18 8 points 15 comments -> [Young workers face a new challenge: Older workers aren't retiring](https://www.washingtonpost.com/opinions/2024/08/26/five-generations-workforce-gen-z-challenge/)<!-- HN:41359311:end --><!-- HN:41358991:start -->
* [41358991](https://news.social-protocols.org/stats?id=41358991) #30 7 points 0 comments -> [Tree mortality may lead to carbon tipping point in the Amazon by 2050s](https://phys.org/news/2024-08-tree-mortality-carbon-amazon-2050s.html)<!-- HN:41358991:end --><!-- HN:41360466:start -->
* [41360466](https://news.social-protocols.org/stats?id=41360466) #6 4 points 3 comments -> [McKinsey Reveals: Leaders Are Wrong About Why Employees Quit](https://www.worktango.com/resources/articles/mckinsey-report-2021)<!-- HN:41360466:end --><!-- HN:41311122:start -->
* [41311122](https://news.social-protocols.org/stats?id=41311122) #14 37 points 9 comments -> [Military Motivation and Frontier Maintenance](https://acoup.blog/2024/08/16/fireside-friday-august-16-2024/)<!-- HN:41311122:end --><!-- HN:41359502:start -->
* [41359502](https://news.social-protocols.org/stats?id=41359502) #26 124 points 111 comments -> [The Arrest of Pavel Durov Is a Reminder That Telegram Is Not Encrypted](https://gizmodo.com/the-arrest-of-pavel-durov-is-a-reminder-that-telegram-is-not-encrypted-2000490960)<!-- HN:41359502:end --><!-- HN:41360979:start -->
* [41360979](https://news.social-protocols.org/stats?id=41360979) #27 5 points 2 comments -> [Finding love: Study reveals where love lives in the brain](https://medicalxpress.com/news/2024-08-reveals-brain.html)<!-- HN:41360979:end --><!-- HN:41361675:start -->
* [41361675](https://news.social-protocols.org/stats?id=41361675) #3 7 points 0 comments -> [Causes and consequences of US teacher strikes](https://www.nber.org/papers/w32862)<!-- HN:41361675:end --><!-- HN:41361993:start -->
* [41361993](https://news.social-protocols.org/stats?id=41361993) #27 7 points 2 comments -> ['Terrorgram' Chatrooms Are Fueling a Wave of Power Grid Attacks](https://www.bloomberg.com/news/articles/2024-08-26/far-right-terrorgram-chatrooms-fuel-wave-of-power-grid-attacks)<!-- HN:41361993:end --><!-- HN:41311029:start -->
* [41311029](https://news.social-protocols.org/stats?id=41311029) #30 15 points 0 comments -> [Recurring Systems Archetypes (2017)](https://medium.com/disruptive-design/tools-for-systems-thinkers-the-12-recurring-systems-archetypes-2e2c8ae8fc99)<!-- HN:41311029:end --><!-- HN:41360409:start -->
* [41360409](https://news.social-protocols.org/stats?id=41360409) #25 20 points 2 comments -> [CL-32 is a DIY pocket computer with a thumb keyboard, E-Ink and ESP32-S3 chip](https://liliputing.com/cl-32-is-a-diy-pocket-computer-with-a-thumb-keyboard-e-ink-screen-and-esp32-s3-chip/)<!-- HN:41360409:end --><!-- HN:41360035:start -->
* [41360035](https://news.social-protocols.org/stats?id=41360035) #27 20 points 5 comments -> [Show HN: I made a game to show how bad the NYC rental market is](https://leaseswap.nyc/guess)<!-- HN:41360035:end --><!-- HN:41337941:start -->
* [41337941](https://news.social-protocols.org/stats?id=41337941) #27 13 points 2 comments -> [PHP-Parser: A Native PHP Parser for Parsing and Analyzing PHP Code](https://github.com/nikic/PHP-Parser)<!-- HN:41337941:end --><!-- HN:41362854:start -->
* [41362854](https://news.social-protocols.org/stats?id=41362854) #23 3 points 0 comments -> [Surprise Hardware Bug in RP2350 Leads to Unexpected Pulldown Behavior](https://www.hackster.io/news/a-surprise-hardware-bug-in-raspberry-pi-s-rp2350-leads-to-unexpected-pull-down-behavior-76b51ec22ede)<!-- HN:41362854:end -->
#### **Tuesday, August 27, 2024**
<!-- HN:41347119:start -->
* [41347119](https://news.social-protocols.org/stats?id=41347119) #24 33 points 40 comments -> [What it's like to work on cold cases](https://www.nytimes.com/2024/08/25/us/cold-case-murder-investigation-police.html)<!-- HN:41347119:end -->
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

#### **Thursday, September 5, 2024**
<!-- HN:41452414:start -->
* [41452414](https://news.social-protocols.org/stats?id=41452414) #19 5 points 1 comments -> [The Houthis now rule the Red Sea, America has silently admitted defeat](https://unherd.com/2024/09/why-the-houthis-now-rule-the-red-sea/)<!-- HN:41452414:end --><!-- HN:41451143:start -->
* [41451143](https://news.social-protocols.org/stats?id=41451143) #17 15 points 0 comments -> [What Is an Atomic Clock? (2019)](https://www.nasa.gov/missions/tech-demonstration/deep-space-atomic-clock/what-is-an-atomic-clock/)<!-- HN:41451143:end --><!-- HN:41452720:start -->
* [41452720](https://news.social-protocols.org/stats?id=41452720) #8 3 points 1 comments -> [K-Pop Redefined](https://www.bloomberg.com/graphics/2024-kpop-redefine-global-music-industry/)<!-- HN:41452720:end --><!-- HN:41422150:start -->
* [41422150](https://news.social-protocols.org/stats?id=41422150) #9 23 points 40 comments -> [Undefined behavior in C is a reading error (2021)](https://www.yodaiken.com/2021/05/19/undefined-behavior-in-c-is-a-reading-error/)<!-- HN:41422150:end --><!-- HN:41454081:start -->
* [41454081](https://news.social-protocols.org/stats?id=41454081) #27 3 points 1 comments -> [Racism, misogyny, lies: how did X become so full of hatred?](https://www.theguardian.com/technology/article/2024/sep/05/racism-misogyny-lies-how-did-x-become-so-full-of-hatred-and-is-it-ethical-to-keep-using-it)<!-- HN:41454081:end --><!-- HN:41453894:start -->
* [41453894](https://news.social-protocols.org/stats?id=41453894) #27 -> [Amazon Drivers Complain Their Ability to Sing Along the Radio Is Being Stifled](https://jalopnik.com/amazon-bans-its-drivers-from-moving-their-own-lips-too-1851639312)<!-- HN:41453894:end --><!-- HN:41428759:start -->
* [41428759](https://news.social-protocols.org/stats?id=41428759) #30 23 points 5 comments -> [Activating a Playstation-Only Cheat on PC in Just Nine Bytes](https://falseceilings.wordpress.com/2020/03/24/activating-a-playstation-only-cheat-on-pc-in-just-nine-bytes/)<!-- HN:41428759:end --><!-- HN:41425055:start -->
* [41425055](https://news.social-protocols.org/stats?id=41425055) #27 9 points 0 comments -> [The Powerful Potential of Tiny Conservation Plots](https://www.noemamag.com/the-powerful-potential-of-tiny-conservation-plots/)<!-- HN:41425055:end --><!-- HN:41422395:start -->
* [41422395](https://news.social-protocols.org/stats?id=41422395) #19 37 points 22 comments -> [CSS-only infinite scrolling carousel animation](https://blog.logto.io/css-only-infinite-scroll)<!-- HN:41422395:end --><!-- HN:41455252:start -->
* [41455252](https://news.social-protocols.org/stats?id=41455252) #30 17 points 3 comments -> [Olympic athlete Rebecca Cheptegei dies days after being set alight by ex-BF](https://www.bbc.com/news/articles/c3vx0kq2xr2o)<!-- HN:41455252:end --><!-- HN:41455888:start -->
* [41455888](https://news.social-protocols.org/stats?id=41455888) #25 15 points 6 comments -> [North Korean Spies Are Infiltrating U.S. Companies Through Remote IT Jobs](https://www.wsj.com/tech/north-korean-spies-are-infiltrating-u-s-companies-through-it-jobs-e45a1be8)<!-- HN:41455888:end --><!-- HN:41455906:start -->
* [41455906](https://news.social-protocols.org/stats?id=41455906) #30 15 points 5 comments -> [Laravel has raised a $57M Series A in partnership with Accel](https://twitter.com/taylorotwell/status/1831668872732180697)<!-- HN:41455906:end --><!-- HN:41456270:start -->
* [41456270](https://news.social-protocols.org/stats?id=41456270) #1 29 points 13 comments -> [New study suggests nose picking could increase risk for Alzheimer's and dementia](https://news.griffith.edu.au/2022/10/28/new-research-suggests-nose-picking-could-increase-risk-for-alzheimers-and-dementia/)<!-- HN:41456270:end --><!-- HN:41456425:start -->
* [41456425](https://news.social-protocols.org/stats?id=41456425) #7 6 points 0 comments -> [The Deep Religious Roots of American Economics](https://thereader.mitpress.mit.edu/the-deep-religious-roots-of-american-economics/)<!-- HN:41456425:end --><!-- HN:41455432:start -->
* [41455432](https://news.social-protocols.org/stats?id=41455432) #29 28 points 28 comments -> [America's Space Force Is Preparing for the Risk of War](https://www.wsj.com/politics/national-security/americas-space-force-is-preparing-for-the-risk-of-war-d6b5e9c7)<!-- HN:41455432:end --><!-- HN:41457564:start -->
* [41457564](https://news.social-protocols.org/stats?id=41457564) #28 22 points 40 comments -> [Ditching EVs for Hybrids Is Already Paying Off for Automakers](https://jalopnik.com/ditching-evs-for-hybrids-is-already-paying-off-for-auto-1851640422)<!-- HN:41457564:end --><!-- HN:41457967:start -->
* [41457967](https://news.social-protocols.org/stats?id=41457967) #24 4 points 0 comments -> [Apple 'testing' foldable with secondary E Ink display, says analyst](https://www.theverge.com/2022/5/17/23086673/apple-e-ink-foldable-external-screen-tablet-electronic-paper)<!-- HN:41457967:end --><!-- HN:41457654:start -->
* [41457654](https://news.social-protocols.org/stats?id=41457654) #25 6 points 6 comments -> [BMW tries "motionless" wind tech on UK plant roof](https://renewablesnow.com/news/bmw-tries-motionless-wind-tech-on-uk-plant-roof-867956/)<!-- HN:41457654:end --><!-- HN:41458221:start -->
* [41458221](https://news.social-protocols.org/stats?id=41458221) #10 3 points 0 comments -> [Loopy: Lip-Sync AI (Audio-Driven Portrait Avatar Generation)](https://loopyavatar.github.io/)<!-- HN:41458221:end --><!-- HN:41458442:start -->
* [41458442](https://news.social-protocols.org/stats?id=41458442) #4 13 points 3 comments -> [A sensible Java key management tool for normal people](https://github.com/alastairmccormack/keyutil)<!-- HN:41458442:end --><!-- HN:41458820:start -->
* [41458820](https://news.social-protocols.org/stats?id=41458820) #20 9 points 6 comments -> [We need to check the gen AI hype and get back to reality](https://venturebeat.com/ai/why-we-need-to-check-the-gen-ai-hype-and-get-back-to-reality/)<!-- HN:41458820:end --><!-- HN:41459000:start -->
* [41459000](https://news.social-protocols.org/stats?id=41459000) #29 3 points 0 comments -> [Final orange grove in the San Fernando Valley to give way to luxury homes](https://www.latimes.com/business/story/2024-08-22/plans-to-turn-last-commercial-citrus-grove-in-san-fernando-valley-into-housing-move-forward)<!-- HN:41459000:end --><!-- HN:41456433:start -->
* [41456433](https://news.social-protocols.org/stats?id=41456433) #26 11 points 1 comments -> [Leon is your open-source personal assistant who can live on your server](https://getleon.ai/)<!-- HN:41456433:end --><!-- HN:41457896:start -->
* [41457896](https://news.social-protocols.org/stats?id=41457896) #30 15 points 2 comments -> [A Manifesto for Radical Simplicity](https://joshaustin.tech/blog/a-manifesto-for-radical-simplicity/)<!-- HN:41457896:end --><!-- HN:41460984:start -->
* [41460984](https://news.social-protocols.org/stats?id=41460984) #26 10 points 40 comments -> [First-in-Nation Bill Requiring Cars to Warn Speeding Drivers Goes to CA Governor](https://sd11.senate.ca.gov/news/senator-wieners-first-nation-bill-require-cars-warn-speeding-drivers-heads-governor)<!-- HN:41460984:end -->
#### **Friday, September 6, 2024**<!-- HN:41420783:start -->
* [41420783](https://news.social-protocols.org/stats?id=41420783) #4 449 points 91 comments -> [OAuth from First Principles](https://stack-auth.com/blog/oauth-from-first-principles)<!-- HN:41420783:end --><!-- HN:41423385:start -->
* [41423385](https://news.social-protocols.org/stats?id=41423385) #2 190 points 57 comments -> [People can read their manager's mind](https://yosefk.com/blog/people-can-read-their-managers-mind.html)<!-- HN:41423385:end --><!-- HN:41437175:start -->
* [41437175](https://news.social-protocols.org/stats?id=41437175) #14 5 points 0 comments -> [DIY Geiger Counter and Tasmota ESP8266](https://github.com/arendst/Tasmota/discussions/18449)<!-- HN:41437175:end --><!-- HN:41465044:start -->
* [41465044](https://news.social-protocols.org/stats?id=41465044) #3 5 points 1 comments -> [The "Need for Chaos" Voter](https://www.forkingpaths.co/p/the-need-for-chaos-voter-a68)<!-- HN:41465044:end --><!-- HN:41464982:start -->
* [41464982](https://news.social-protocols.org/stats?id=41464982) #25 8 points 3 comments -> [Voters' Yearning for a Dictator Is a Danger to the Country](https://reason.com/2024/09/06/voters-yearning-for-a-dictator-is-a-danger-to-the-country/)<!-- HN:41464982:end --><!-- HN:41463768:start -->
* [41463768](https://news.social-protocols.org/stats?id=41463768) #13 79 points 34 comments -> [Oxford commercializes its 20% more powerful solar panels in the US](https://electrek.co/2024/09/05/oxford-commercializes-its-20-more-powerful-solar-panels-in-the-us/)<!-- HN:41463768:end --><!-- HN:41460944:start -->
* [41460944](https://news.social-protocols.org/stats?id=41460944) #18 77 points 42 comments -> [Cron Jobs on Linux – Comprehensive Guide with Examples](https://ittavern.com/cron-jobs-on-linux-comprehensive-guide/)<!-- HN:41460944:end --><!-- HN:41465567:start -->
* [41465567](https://news.social-protocols.org/stats?id=41465567) #20 4 points 0 comments -> [Therapy Sessions Exposed by Mental Health Care Firm's Unsecured Database](https://www.wired.com/story/confidant-health-therapy-records-database-exposure/)<!-- HN:41465567:end --><!-- HN:41463330:start -->
* [41463330](https://news.social-protocols.org/stats?id=41463330) #17 176 points 132 comments -> [The expected value of the game is positive regardless of Ballmer’s strategy](https://gukov.dev/puzzles/math/2024/09/05/steve-ballmer-was-wrong.html)<!-- HN:41463330:end --><!-- HN:41465874:start -->
* [41465874](https://news.social-protocols.org/stats?id=41465874) #23 15 points 0 comments -> [Causing environmental damage should be a criminal offence](https://earth4all.life/news/causing-environmental-damage-should-be-a-criminal-offence-say-72-of-people-in-g20-countries-surveyed/)<!-- HN:41465874:end --><!-- HN:41466131:start -->
* [41466131](https://news.social-protocols.org/stats?id=41466131) #25 4 points 0 comments -> [D-Link says it is not fixing four RCE flaws in DIR-846W routers](https://www.bleepingcomputer.com/news/security/d-link-says-it-is-not-fixing-four-rce-flaws-in-dir-846w-routers/)<!-- HN:41466131:end --><!-- HN:41464566:start -->
* [41464566](https://news.social-protocols.org/stats?id=41464566) #27 61 points 49 comments -> [Streaming every NFL game this season requires 7 different services, costs $2,500](https://www.marketwatch.com/story/want-to-watch-every-nfl-game-this-season-its-going-to-cost-you-nearly-2-500-31c4d300)<!-- HN:41464566:end --><!-- HN:41465692:start -->
* [41465692](https://news.social-protocols.org/stats?id=41465692) #25 9 points 0 comments -> [Telegram CEO breaks silence after arrest](https://www.theverge.com/2024/9/5/24237174/telegram-ceo-pavel-durov-statement-following-arrest)<!-- HN:41465692:end --><!-- HN:41464808:start -->
* [41464808](https://news.social-protocols.org/stats?id=41464808) #15 26 points 6 comments -> [Advanced Programming in the Unix Environment](https://stevens.netmeister.org/631/)<!-- HN:41464808:end --><!-- HN:41464482:start -->
* [41464482](https://news.social-protocols.org/stats?id=41464482) #24 6 points 2 comments -> [CA Governor seeks to harness the power of GenAI to address homelessness](https://www.gov.ca.gov/2024/09/05/governor-newsom-seeks-to-harness-the-power-of-genai-to-address-homelessness-other-challenges/)<!-- HN:41464482:end --><!-- HN:41466621:start -->
* [41466621](https://news.social-protocols.org/stats?id=41466621) #8 15 points 5 comments -> [AI Training is Copyright Infringement (under European law)](https://urheber.info/diskurs/ai-training-is-copyright-infringement)<!-- HN:41466621:end --><!-- HN:41464994:start -->
* [41464994](https://news.social-protocols.org/stats?id=41464994) #11 26 points 21 comments -> [C2y Proposal: Essential Effects for C](https://www9.open-std.org/JTC1/SC22/WG14/www/docs/n3317.htm)<!-- HN:41464994:end --><!-- HN:41466667:start -->
* [41466667](https://news.social-protocols.org/stats?id=41466667) #4 22 points 5 comments -> [Linux man-pages project maintenance](https://lwn.net/ml/all/4d7tq6a7febsoru3wjium4ekttuw2ouocv6jstdkthnacmzr6x@f2zfbe5hs7h5/)<!-- HN:41466667:end --><!-- HN:41466702:start -->
* [41466702](https://news.social-protocols.org/stats?id=41466702) #30 9 points 3 comments -> [The fight between Prospero and Honduras](https://twitter.com/GarrisonLovely/status/1831104024612896795)<!-- HN:41466702:end --><!-- HN:41468431:start -->
* [41468431](https://news.social-protocols.org/stats?id=41468431) #29 6 points 0 comments -> [US Surgeon General warns that parenting is a health hazard [pdf]](https://www.hhs.gov/sites/default/files/parents-under-pressure.pdf)<!-- HN:41468431:end --><!-- HN:41468794:start -->
* [41468794](https://news.social-protocols.org/stats?id=41468794) #24 17 points 40 comments -> [Tesla launches first all-electric 'Giga Train' – and it's free to ride](https://www.yahoo.com/tech/tesla-launches-worlds-first-electric-111535136.html)<!-- HN:41468794:end --><!-- HN:41426828:start -->
* [41426828](https://news.social-protocols.org/stats?id=41426828) #21 126 points 85 comments -> [Advanced Python: Achieving High Performance with Code Generation](https://medium.com/@yonatanzunger/advanced-python-achieving-high-performance-with-code-generation-796b177ec79)<!-- HN:41426828:end --><!-- HN:41424533:start -->
* [41424533](https://news.social-protocols.org/stats?id=41424533) #24 43 points 9 comments -> [Hawking Archive made available to historians and researchers](https://www.cam.ac.uk/stories/hawking-archive-for-all)<!-- HN:41424533:end --><!-- HN:41469660:start -->
* [41469660](https://news.social-protocols.org/stats?id=41469660) #10 12 points 3 comments -> [Where Did the Serial Killers from the 80s Go? They're Online, and in Plain Sight](https://substack.com/@benedictslaney/p-148558589)<!-- HN:41469660:end -->
#### **Saturday, September 7, 2024**
<!-- HN:41431463:start -->
* [41431463](https://news.social-protocols.org/stats?id=41431463) #23 41 points 6 comments -> [Handling complexity without abstraction: Algebraic Bricklaying C](https://github.com/gritzko/librdx/blob/master/ABC.md)<!-- HN:41431463:end --><!-- HN:41471713:start -->
* [41471713](https://news.social-protocols.org/stats?id=41471713) #12 15 points 2 comments -> [How to evaluate performance of LLM inference frameworks](https://www.lamini.ai/blog/evaluate-performance-llm-inference-frameworks)<!-- HN:41471713:end --><!-- HN:41470491:start -->
* [41470491](https://news.social-protocols.org/stats?id=41470491) #28 43 points 26 comments -> [Boost your development environment with Ubuntu Multipass](https://letsdebug.it/post/21-ubuntu-multipass/)<!-- HN:41470491:end --><!-- HN:41473376:start -->
* [41473376](https://news.social-protocols.org/stats?id=41473376) #23 6 points 0 comments -> [An 'earthquake' at Volkswagen – and a crisis for Germany?](https://www.theguardian.com/business/article/2024/sep/07/an-earthquake-at-volkswagen-and-a-crisis-for-germany)<!-- HN:41473376:end --><!-- HN:41473309:start -->
* [41473309](https://news.social-protocols.org/stats?id=41473309) #30 4 points 0 comments -> [An Italian Bank Accepts Parmesan Cheese as Loan Collateral](https://www.forbes.com/sites/hbsworkingknowledge/2015/07/01/a-bank-that-accepts-parmesan-as-collateral-the-cheese-stands-a-loan/)<!-- HN:41473309:end --><!-- HN:41474602:start -->
* [41474602](https://news.social-protocols.org/stats?id=41474602) #10 10 points 1 comments -> [X Exec Who Defended Restoring Account with Child Abuse Content Resigns](https://gizmodo.com/x-twitter-exec-who-defended-restoring-account-that-posted-child-sexual-abuse-material-leaves-the-company-2000495687)<!-- HN:41474602:end --><!-- HN:41475018:start -->
* [41475018](https://news.social-protocols.org/stats?id=41475018) #1 14 points 2 comments -> [Saddling up on the high seas – the cyclists powering 50-MPH yachts](https://www.bbc.com/sport/articles/c4ngydm1x55o)<!-- HN:41475018:end --><!-- HN:41475697:start -->
* [41475697](https://news.social-protocols.org/stats?id=41475697) #6 16 points 4 comments -> [Amazon's $1,600 Astro robot has FOUR CPUs running Linux?](https://mastodon.social/@zhuowei@notnow.dev/113097708118539407)<!-- HN:41475697:end --><!-- HN:41432710:start -->
* [41432710](https://news.social-protocols.org/stats?id=41432710) #17 33 points 10 comments -> [Show HN: Shelly – A pure and vanilla shell-like interface for the web](https://github.com/galvao-eti/shelly)<!-- HN:41432710:end --><!-- HN:41431556:start -->
* [41431556](https://news.social-protocols.org/stats?id=41431556) #20 171 points 29 comments -> [Pulsar, micro creative coding playground](https://muffinman.io/pulsar/)<!-- HN:41431556:end --><!-- HN:41434062:start -->
* [41434062](https://news.social-protocols.org/stats?id=41434062) #30 77 points 24 comments -> [Will open science change chemistry?](https://www.chemistryworld.com/careers/will-open-science-change-chemistry/4020023.article)<!-- HN:41434062:end --><!-- HN:41476507:start -->
* [41476507](https://news.social-protocols.org/stats?id=41476507) #14 11 points 4 comments -> [Nonstandard Analysis (1972)](https://sci-hub.se/https://www.jstor.org/stable/24927363)<!-- HN:41476507:end --><!-- HN:41475872:start -->
* [41475872](https://news.social-protocols.org/stats?id=41475872) #26 23 points 15 comments -> [Alternatives to Google Products – Updated](https://peq42.com/blog/alternatives-to-google-products/)<!-- HN:41475872:end --><!-- HN:41475869:start -->
* [41475869](https://news.social-protocols.org/stats?id=41475869) #28 7 points 7 comments -> [First water car is already a reality: 1000km of autonomy and the end of gasoline](https://www.eldiario24.com/en/water-car-end-gasoline/114/)<!-- HN:41475869:end -->
#### **Sunday, September 8, 2024**
<!-- HN:41478785:start -->
* [41478785](https://news.social-protocols.org/stats?id=41478785) #3 38 points 24 comments -> [Creating a search engine for fun and because Google sucks](https://vincents.dev/blog/creating-a-search-engine/?)<!-- HN:41478785:end --><!-- HN:41479594:start -->
* [41479594](https://news.social-protocols.org/stats?id=41479594) #29 10 points 4 comments -> [Man jailed indefinitely for refusing to decrypt hard drives loses appeal (2011)](https://arstechnica.com/tech-policy/2017/03/man-jailed-indefinitely-for-refusing-to-decrypt-hard-drives-loses-appeal/)<!-- HN:41479594:end --><!-- HN:41478195:start -->
* [41478195](https://news.social-protocols.org/stats?id=41478195) #23 31 points 13 comments -> [WordPerfect for Unix Character Terminals](https://github.com/taviso/wpunix)<!-- HN:41478195:end --><!-- HN:41480267:start -->
* [41480267](https://news.social-protocols.org/stats?id=41480267) #21 5 points 2 comments -> [Twitter Runs on Hate – But Its Users Don't Reflect Real Life](https://www.theamericansaga.com/p/never-forget-twitter-isnt-real-life)<!-- HN:41480267:end --><!-- HN:41479261:start -->
* [41479261](https://news.social-protocols.org/stats?id=41479261) #23 81 points 14 comments -> [The worsening Raspberry Pi RP2350 E9 erratum situation](https://hackaday.com/2024/09/04/the-worsening-raspberry-pi-rp2350-e9-erratum-situation/)<!-- HN:41479261:end --><!-- HN:41481058:start -->
* [41481058](https://news.social-protocols.org/stats?id=41481058) #23 12 points 40 comments -> [UK electric car drivers should be charged per mile, say campaigners](https://www.theguardian.com/politics/article/2024/sep/03/uk-electric-car-drivers-per-mile-vehicle-taxes-campaign-for-better-transport)<!-- HN:41481058:end --><!-- HN:41483178:start -->
* [41483178](https://news.social-protocols.org/stats?id=41483178) #16 10 points 5 comments -> [The $12,000 Harvard Class Celebrities Are Fighting to Get Into](https://www.bloomberg.com/news/features/2024-07-22/the-12-000-harvard-business-class-celebrities-are-fighting-to-get-into)<!-- HN:41483178:end --><!-- HN:41483439:start -->
* [41483439](https://news.social-protocols.org/stats?id=41483439) #28 10 points 7 comments -> [YouTube restricts teenager access to fitness videos](https://www.euronews.com/health/2024/09/07/youtube-will-begin-limiting-access-to-fitness-videos-for-european-teens-heres-why)<!-- HN:41483439:end --><!-- HN:41455022:start -->
* [41455022](https://news.social-protocols.org/stats?id=41455022) #5 58 points 0 comments -> [Creating a Git Commit: The Hard Way](https://avestura.dev/blog/creating-a-git-commit-the-hard-way)<!-- HN:41455022:end -->
#### **Monday, September 9, 2024**
<!-- HN:41440620:start -->
* [41440620](https://news.social-protocols.org/stats?id=41440620) #14 22 points 5 comments -> [16th Century Irish Hipsters](http://irisharchaeology.ie/2013/08/16th-century-irish-hipsters/)<!-- HN:41440620:end --><!-- HN:41443012:start -->
* [41443012](https://news.social-protocols.org/stats?id=41443012) #19 121 points 32 comments -> [LibrePythonista allows running IPython code in a LibreOffice spreadsheet](https://github.com/Amourspirit/python_libre_pythonista_ext)<!-- HN:41443012:end --><!-- HN:41438744:start -->
* [41438744](https://news.social-protocols.org/stats?id=41438744) #27 38 points 28 comments -> [Deadline looms: Google Workspace mandates OAuth by September 30](https://www.theregister.com/2024/09/03/google_workspace_third_party_apps/)<!-- HN:41438744:end --><!-- HN:41484633:start -->
* [41484633](https://news.social-protocols.org/stats?id=41484633) #17 11 points 5 comments -> [⓿ dependencies!](https://0dependencies.dev/)<!-- HN:41484633:end --><!-- HN:41484743:start -->
* [41484743](https://news.social-protocols.org/stats?id=41484743) #24 13 points 40 comments -> [Do Programmers Actually Need Touch Typing?](http://blog.hakanserce.com/post/do-programmers-actually-need-touch-typing/)<!-- HN:41484743:end --><!-- HN:41485447:start -->
* [41485447](https://news.social-protocols.org/stats?id=41485447) #29 21 points 6 comments -> [The PermaTab Web Browser](https://lee-phillips.org/permatab/)<!-- HN:41485447:end --><!-- HN:41487044:start -->
* [41487044](https://news.social-protocols.org/stats?id=41487044) #3 10 points 4 comments -> [Show HN: What do your GitHub starred repos say about you?](https://starlens.aisprint.dev/)<!-- HN:41487044:end --><!-- HN:41486935:start -->
* [41486935](https://news.social-protocols.org/stats?id=41486935) #9 30 points 40 comments -> [Support for U.S. TikTok ban continues to decline](https://www.pewresearch.org/short-reads/2024/09/05/support-for-a-us-tiktok-ban-continues-to-decline-and-half-of-adults-doubt-it-will-happen/)<!-- HN:41486935:end --><!-- HN:41485967:start -->
* [41485967](https://news.social-protocols.org/stats?id=41485967) #15 118 points 118 comments -> [Please stop inventing new software licences (2020)](https://shkspr.mobi/blog/2020/09/please-stop-inventing-new-software-licences/)<!-- HN:41485967:end --><!-- HN:41484914:start -->
* [41484914](https://news.social-protocols.org/stats?id=41484914) #29 33 points 6 comments -> [JPEG XL: Industry-leading image compression and fidelity](https://jpegxl.info)<!-- HN:41484914:end --><!-- HN:41487930:start -->
* [41487930](https://news.social-protocols.org/stats?id=41487930) #17 -> [Police pressured him to confess to a murder that never happened](https://www.cnn.com/2024/09/05/us/fontana-pressured-murder-confession/index.html)<!-- HN:41487930:end --><!-- HN:41488189:start -->
* [41488189](https://news.social-protocols.org/stats?id=41488189) #8 10 points 4 comments -> [Are greedy companies to blame for grocery inflation? We looked at the data](https://www.npr.org/2024/09/09/nx-s1-5103935/grocery-prices-inflation-corporate-greedflation)<!-- HN:41488189:end --><!-- HN:41482679:start -->
* [41482679](https://news.social-protocols.org/stats?id=41482679) #27 175 points 116 comments -> [Htmx, Raku and Pico CSS](https://rakujourney.wordpress.com/2024/09/08/htmx-raku-and-pico-css/)<!-- HN:41482679:end --><!-- HN:41488116:start -->
* [41488116](https://news.social-protocols.org/stats?id=41488116) #2 72 points 40 comments -> [America's best-paid CEOs have the worst-paid employees](https://pluralistic.net/2024/09/09/low-wage-100/)<!-- HN:41488116:end --><!-- HN:41487567:start -->
* [41487567](https://news.social-protocols.org/stats?id=41487567) #22 7 points 2 comments -> [Searching 32M academic papers for obscene acronyms hidden in the titles](https://robmanuelfuckyeah.substack.com/p/searching-32-million-academic-papers)<!-- HN:41487567:end --><!-- HN:41488929:start -->
* [41488929](https://news.social-protocols.org/stats?id=41488929) #5 54 points 25 comments -> [Gitea blocks PR from community, charging $$ for open-source contributions](https://github.com/go-gitea/gitea/pull/24257)<!-- HN:41488929:end --><!-- HN:41489497:start -->
* [41489497](https://news.social-protocols.org/stats?id=41489497) #21 7 points 0 comments -> [Great Barrier Reef already been dealt its death blow](https://www.rnz.co.nz/news/national/527469/great-barrier-reef-already-been-dealt-its-death-blow-scientist)<!-- HN:41489497:end --><!-- HN:41490125:start -->
* [41490125](https://news.social-protocols.org/stats?id=41490125) #29 8 points 4 comments -> [Americans Voted Their Way into a Housing Crisis](https://www.bloomberg.com/news/articles/2024-09-08/an-american-affordable-housing-crisis-built-by-local-democracy)<!-- HN:41490125:end --><!-- HN:41493976:start -->
* [41493976](https://news.social-protocols.org/stats?id=41493976) #8 64 points 7 comments -> [James Earl Jones, voice of Darth Vader, dies aged 93](https://www.bbc.co.uk/news/articles/ce81rkg87w8o)<!-- HN:41493976:end -->
#### **Tuesday, September 10, 2024**
<!-- HN:41452780:start -->
* [41452780](https://news.social-protocols.org/stats?id=41452780) #29 118 points 27 comments -> [Paper types ranked by likelihood of paper cuts](https://phys.org/news/2024-08-paper-likelihood.html)<!-- HN:41452780:end --><!-- HN:41498640:start -->
* [41498640](https://news.social-protocols.org/stats?id=41498640) #5 10 points 3 comments -> [Huawei Unveils $2,800 Trifold Mate XT Just Hours After Apple Launches iPhone 16](https://www.bloomberg.com/news/articles/2024-09-10/huawei-trifold-phone-versus-iphone-16-specs-price-release-date)<!-- HN:41498640:end --><!-- HN:41496254:start -->
* [41496254](https://news.social-protocols.org/stats?id=41496254) #13 238 points 170 comments -> [DOJ claims Google has "trifecta of monopolies" on Day 1 of ad tech trial](https://arstechnica.com/tech-policy/2024/09/doj-claims-google-has-trifecta-of-monopolies-on-day-1-of-ad-tech-trial/)<!-- HN:41496254:end --><!-- HN:41498643:start -->
* [41498643](https://news.social-protocols.org/stats?id=41498643) #29 11 points 0 comments -> [Google's 2.4B euro fine upheld by Europe's top court in EU antitrust probe](https://www.cnbc.com/2024/09/10/googles-2point4-billion-euro-fine-upheld-by-europes-top-court.html)<!-- HN:41498643:end --><!-- HN:41499452:start -->
* [41499452](https://news.social-protocols.org/stats?id=41499452) #13 7 points 0 comments -> [The FBI spent decades tracking mathematician Paul Erdős](https://www.muckrock.com/news/archives/2015/jul/21/nothing-indicate-nothing-indicate-subject-had-any-/)<!-- HN:41499452:end --><!-- HN:41499855:start -->
* [41499855](https://news.social-protocols.org/stats?id=41499855) #1 27 points 14 comments -> [Meta's Hack (HHVM) language appears to be no longer maintained](https://github.com/facebook/hhvm/graphs/commit-activity)<!-- HN:41499855:end --><!-- HN:41495871:start -->
* [41495871](https://news.social-protocols.org/stats?id=41495871) #10 100 points 37 comments -> [Affordable DE10-Nano compatible boards for MiSTer FPGA retro platform](https://www.retrorgb.com/mister-pi-de-10-nano-clone-up-for-sale-today.html)<!-- HN:41495871:end --><!-- HN:41500419:start -->
* [41500419](https://news.social-protocols.org/stats?id=41500419) #29 5 points 0 comments -> [In Slingshot, a mission to Titan goes off course](https://spacenews.com/in-slingshot-a-mission-to-titan-goes-off-course/)<!-- HN:41500419:end --><!-- HN:41500402:start -->
* [41500402](https://news.social-protocols.org/stats?id=41500402) #30 4 points 0 comments -> [Epilepsy drug shows promise in reducing obstructive sleep apnea symptoms](https://www.ajmc.com/view/epilepsy-drug-shows-promise-in-reducing-obstructive-sleep-apnea-symptoms)<!-- HN:41500402:end --><!-- HN:41500201:start -->
* [41500201](https://news.social-protocols.org/stats?id=41500201) #20 38 points 27 comments -> [Bank of America raises minimum hourly pay to $24, as tellers flee the industry](https://www.npr.org/2024/09/10/nx-s1-5106884/bank-of-america-raises-hourly-pay-tellers-flee-banking)<!-- HN:41500201:end --><!-- HN:41495762:start -->
* [41495762](https://news.social-protocols.org/stats?id=41495762) #29 69 points 40 comments -> [Tesla FSD no longer offered for purchase](https://www.notateslaapp.com/news/2245/tesla-updates-fsd-package-can-now-only-buy-fsd-supervised)<!-- HN:41495762:end --><!-- HN:41500799:start -->
* [41500799](https://news.social-protocols.org/stats?id=41500799) #3 5 points 2 comments -> [Budget-friendly DIY video surveillance](https://felenasoft.com/xeoma/en/articles/diy-video-surveillance-system/)<!-- HN:41500799:end --><!-- HN:41500768:start -->
* [41500768](https://news.social-protocols.org/stats?id=41500768) #29 8 points 0 comments -> [BitKeeper, Linux, and licensing disputes: How Linus wrote Git in 14 days](https://lwn.net/Articles/974914/)<!-- HN:41500768:end --><!-- HN:41498529:start -->
* [41498529](https://news.social-protocols.org/stats?id=41498529) #6 47 points 7 comments -> [SQL powered operating system instrumentation, monitoring, and analytics](https://github.com/osquery/osquery)<!-- HN:41498529:end --><!-- HN:41500136:start -->
* [41500136](https://news.social-protocols.org/stats?id=41500136) #29 15 points 1 comments -> [Overweight Ford F-750 Plunges Through Historic Wooden Bridge in Maine](https://www.thedrive.com/news/overweight-ford-f-750-plunges-through-historic-wooden-bridge-in-maine)<!-- HN:41500136:end --><!-- HN:41501714:start -->
* [41501714](https://news.social-protocols.org/stats?id=41501714) #14 26 points 40 comments -> [Sony announces PS5 Pro, a $700 graphics workhorse available Nov. 7](https://arstechnica.com/gaming/2024/09/sony-announces-ps5-pro-a-700-graphics-workhorse-available-nov-7/)<!-- HN:41501714:end --><!-- HN:41500861:start -->
* [41500861](https://news.social-protocols.org/stats?id=41500861) #25 8 points 8 comments -> [Show HN: I built a cheaper ChatGPT alternative that runs on your desktop](https://www.trynyro.com)<!-- HN:41500861:end --><!-- HN:41504881:start -->
* [41504881](https://news.social-protocols.org/stats?id=41504881) #17 26 points 40 comments -> [The US finally takes aim at truck bloat](https://www.theverge.com/2024/9/10/24241047/nhtsa-rule-pedestrian-safety-fmvss-suv-truck-design)<!-- HN:41504881:end --><!-- HN:41459722:start -->
* [41459722](https://news.social-protocols.org/stats?id=41459722) #16 23 points 8 comments -> [DJI Neo review – a drone that can do everything, and land in your hand](https://www.digitalcameraworld.com/reviews/dji-neo-review)<!-- HN:41459722:end -->
#### **Wednesday, September 11, 2024**
<!-- HN:41508158:start -->
* [41508158](https://news.social-protocols.org/stats?id=41508158) #9 61 points 39 comments -> [Facebook uses Australian adults public photos/posts to train AI, without opt-out](https://www.abc.net.au/news/2024-09-11/facebook-scraping-photos-data-no-opt-out/104336170)<!-- HN:41508158:end --><!-- HN:41508244:start -->
* [41508244](https://news.social-protocols.org/stats?id=41508244) #8 29 points 40 comments -> [Common mistakes when using the metric system](https://www.nayuki.io/page/common-mistakes-when-using-the-metric-system)<!-- HN:41508244:end --><!-- HN:41510008:start -->
* [41510008](https://news.social-protocols.org/stats?id=41510008) #4 6 points 14 comments -> [UK Shops can refuse to take cash even though it's legal tender (2023)](https://fullfact.org/online/legal-tender-cash-in-shops/)<!-- HN:41510008:end --><!-- HN:41510774:start -->
* [41510774](https://news.social-protocols.org/stats?id=41510774) #3 -> [CPI for all items rises 2.5%; shelter up](https://www.bls.gov/news.release/archives/cpi_09112024.htm)<!-- HN:41510774:end --><!-- HN:41510422:start -->
* [41510422](https://news.social-protocols.org/stats?id=41510422) #3 13 points 1 comments -> [My Homelab Setup](https://arslan.io/2024/09/10/my-homelab-setup/)<!-- HN:41510422:end --><!-- HN:41508321:start -->
* [41508321](https://news.social-protocols.org/stats?id=41508321) #7 46 points 10 comments -> [Casio WQV2 Wrist Camera Photos](https://www.urban75.org/watchcam/index.html)<!-- HN:41508321:end -->
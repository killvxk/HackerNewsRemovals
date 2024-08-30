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
<!-- HN:41364114:start -->
* [41364114](https://news.social-protocols.org/stats?id=41364114) #3 9 points 8 comments -> [Show HN: I built a site that tracks short-lived flight deals](https://flight-price-alert.com/)<!-- HN:41364114:end --><!-- HN:41310822:start -->
* [41310822](https://news.social-protocols.org/stats?id=41310822) #23 62 points 11 comments -> [Compressing data with sample points and polynomial interpolation](https://www.johndcook.com/blog/2024/08/17/compression-and-interpolation/)<!-- HN:41310822:end --><!-- HN:41363637:start -->
* [41363637](https://news.social-protocols.org/stats?id=41363637) #22 25 points 17 comments -> [From 14 years old till 29, my experience with desktop Linux](https://blog.myli.page/from-14-years-old-till-29-my-experience-with-desktop-linux-b798d07bcd00)<!-- HN:41363637:end --><!-- HN:41364764:start -->
* [41364764](https://news.social-protocols.org/stats?id=41364764) #21 18 points 14 comments -> [Cellar Door: a quest to find the most beautiful word in English](https://www.cellar-door.co.uk/)<!-- HN:41364764:end --><!-- HN:41365972:start -->
* [41365972](https://news.social-protocols.org/stats?id=41365972) #22 5 points 0 comments -> [Keep Pavel Durov Locked Up](https://blog.thc.org/keep-pavel-durov-locked-up)<!-- HN:41365972:end --><!-- HN:41365598:start -->
* [41365598](https://news.social-protocols.org/stats?id=41365598) #28 53 points 25 comments -> [2023 state of the climate Entering uncharted territory](https://academic.oup.com/bioscience/article/73/12/841/7319571)<!-- HN:41365598:end --><!-- HN:41366628:start -->
* [41366628](https://news.social-protocols.org/stats?id=41366628) #28 13 points 5 comments -> [75% of founders in the Y Combinator S24 cohort are working on AI startups](https://sherwood.news/tech/three-quarters-of-founders-in-the-latest-y-combinator-cohort-are-working-on/)<!-- HN:41366628:end --><!-- HN:41366758:start -->
* [41366758](https://news.social-protocols.org/stats?id=41366758) #26 8 points 0 comments -> [Reasons not to be used by Facebook [2011-2019]](https://stallman.org/facebook.html)<!-- HN:41366758:end --><!-- HN:41366871:start -->
* [41366871](https://news.social-protocols.org/stats?id=41366871) #30 24 points 27 comments -> [Black Myth: Wukong Devs Told Streamers to Avoid Politics in Their Playthroughs](https://www.wired.com/story/black-myth-wukong-streaming-controversy/)<!-- HN:41366871:end --><!-- HN:41367126:start -->
* [41367126](https://news.social-protocols.org/stats?id=41367126) #28 3 points 1 comments -> [The Bewildering Politics of Telegram](https://www.politico.com/news/2024/08/26/telegram-app-politics-00176386)<!-- HN:41367126:end --><!-- HN:41367749:start -->
* [41367749](https://news.social-protocols.org/stats?id=41367749) #2 18 points 11 comments -> [The Real Exponential Curve for LLMs](https://fume.substack.com/p/inference-is-free-and-instant)<!-- HN:41367749:end --><!-- HN:41368677:start -->
* [41368677](https://news.social-protocols.org/stats?id=41368677) #22 10 points 6 comments -> [No smoking in your own home, California city orders residents](https://www.thetimes.com/world/us-world/article/carlsbad-california-smoking-illegal-where-houses-k9qrrvm05)<!-- HN:41368677:end --><!-- HN:41370147:start -->
* [41370147](https://news.social-protocols.org/stats?id=41370147) #24 -> [Show HN: I Built DollarAI.Store – A Collection of 350 AI Tools](https://app.dollarai.store)<!-- HN:41370147:end --><!-- HN:41374219:start -->
* [41374219](https://news.social-protocols.org/stats?id=41374219) #4 7 points 2 comments -> [Is iMessage really an encrypted messaging app? (2021)](https://warnerchad.medium.com/is-apple-imessage-end-to-end-encrypted-it-depends-8bcdcbd8c89b)<!-- HN:41374219:end -->
#### **Wednesday, August 28, 2024**
<!-- HN:41374276:start -->
* [41374276](https://news.social-protocols.org/stats?id=41374276) #27 34 points 40 comments -> [After a decade of free Alexa, Amazon now wants you to pay](https://www.washingtonpost.com/technology/2024/08/27/amazon-ai-alexa-new-subscription/)<!-- HN:41374276:end --><!-- HN:41375219:start -->
* [41375219](https://news.social-protocols.org/stats?id=41375219) #6 8 points 9 comments -> [Obsolete Command-Line Tools of Linux](https://linuxexpert.org/obsolete-command-line-tools-of-linux/)<!-- HN:41375219:end --><!-- HN:41326461:start -->
* [41326461](https://news.social-protocols.org/stats?id=41326461) #16 26 points 3 comments -> [Slime mold simulation in Rust using WASM and WebGPU](https://github.com/plul/slime-mold-simulation)<!-- HN:41326461:end --><!-- HN:41376990:start -->
* [41376990](https://news.social-protocols.org/stats?id=41376990) #21 8 points 3 comments -> [LinkedIn_AIHawk: AI job assistant. Automate applications and Resume Generation](https://github.com/feder-cr/linkedIn_auto_jobs_applier_with_AI)<!-- HN:41376990:end --><!-- HN:41377058:start -->
* [41377058](https://news.social-protocols.org/stats?id=41377058) #19 14 points 1 comments -> ['Order from Amazon': How tech giants are storing mass data for Israel's war](https://www.972mag.com/cloud-israeli-army-gaza-amazon-google-microsoft/)<!-- HN:41377058:end --><!-- HN:41374849:start -->
* [41374849](https://news.social-protocols.org/stats?id=41374849) #29 -> [Cerebras Launches the Fastest AI Inference](https://cerebras.ai/press-release/cerebras-launches-the-worlds-fastest-ai-inference)<!-- HN:41374849:end --><!-- HN:41377924:start -->
* [41377924](https://news.social-protocols.org/stats?id=41377924) #25 10 points 4 comments -> [Why Htmx is far superior to React and NextJS](https://henriqueleite42.com/why-htmx-is-far-superior-to-react-and-nextjs)<!-- HN:41377924:end --><!-- HN:41380031:start -->
* [41380031](https://news.social-protocols.org/stats?id=41380031) #23 11 points 41 comments -> [Unrealized Gain Tax–A Coming Sea Change in FY2025 Budget Proposal?](https://www.forbes.com/sites/andrewleahey/2024/04/30/unrealized-gain-tax-a-coming-sea-change-in-fy2025-budget-proposal/)<!-- HN:41380031:end --><!-- HN:41380977:start -->
* [41380977](https://news.social-protocols.org/stats?id=41380977) #2 6 points 2 comments -> [Is marriage associated with happiness for men or for women? Or both? Or neither?](https://statmodeling.stat.columbia.edu/2024/08/27/marriage-happiness/)<!-- HN:41380977:end --><!-- HN:41381816:start -->
* [41381816](https://news.social-protocols.org/stats?id=41381816) #16 8 points 5 comments -> [Man Is First to Be Charged in New York with Wearing a Mask in Public](https://www.nytimes.com/2024/08/27/nyregion/face-mask-ban-charges-nyc.html)<!-- HN:41381816:end --><!-- HN:41381487:start -->
* [41381487](https://news.social-protocols.org/stats?id=41381487) #5 5 points 1 comments -> [Fly.io (Still) Consistently Unreliable](https://community.fly.io/t/reliability-its-not-great/11253)<!-- HN:41381487:end --><!-- HN:41381994:start -->
* [41381994](https://news.social-protocols.org/stats?id=41381994) #1 32 points 9 comments -> [UAE Freezes $20B Jet Deal with France After Telegram CEO Arrest](https://thedailyguardian.com/uae-freezes-20-billion-jet-deal-with-france-after-telegram-ceo-arrest/)<!-- HN:41381994:end --><!-- HN:41383244:start -->
* [41383244](https://news.social-protocols.org/stats?id=41383244) #16 28 points 40 comments -> [I Hate the Term "Modern"](https://www.paritybit.ca/blog/why-i-hate-the-term-modern/)<!-- HN:41383244:end --><!-- HN:41385154:start -->
* [41385154](https://news.social-protocols.org/stats?id=41385154) #13 8 points 0 comments -> [Silicon Valley's Online Ideologues Are in Model Collapse](https://www.reimaginingliberty.com/silicon-valleys-very-online-ideologues-are-in-model-collapse/)<!-- HN:41385154:end -->
#### **Thursday, August 29, 2024**
<!-- HN:41385637:start -->
* [41385637](https://news.social-protocols.org/stats?id=41385637) #1 116 points 3 comments -> [Judge dismisses majority of GitHub Copilot copyright claims](https://lwn.net/Articles/987524/)<!-- HN:41385637:end --><!-- HN:41327394:start -->
* [41327394](https://news.social-protocols.org/stats?id=41327394) #9 316 points 104 comments -> [The journey of an internet packet: Exploring networks with traceroute](https://sebastianmarines.com/post/journey-of-a-packet-exploring-networks-with-traceroute/)<!-- HN:41327394:end --><!-- HN:41337268:start -->
* [41337268](https://news.social-protocols.org/stats?id=41337268) #15 161 points 92 comments -> ["Everything" is a filename search engine for Windows](https://www.voidtools.com/en-us/support/everything/)<!-- HN:41337268:end --><!-- HN:41357188:start -->
* [41357188](https://news.social-protocols.org/stats?id=41357188) #15 5 points 1 comments -> [An SSR Performance Showdown](https://blog.platformatic.dev/an-ssr-performance-showdown)<!-- HN:41357188:end --><!-- HN:41386848:start -->
* [41386848](https://news.social-protocols.org/stats?id=41386848) #6 9 points 35 comments -> [Show HN: Are You Smarter Than a 5th Grader?](https://areusmarterthanafifthgrader.com)<!-- HN:41386848:end --><!-- HN:41388557:start -->
* [41388557](https://news.social-protocols.org/stats?id=41388557) #30 14 points 6 comments -> [Show HN: A directory to find open source AI projects easier](https://www.aiexh.com/en)<!-- HN:41388557:end --><!-- HN:41389787:start -->
* [41389787](https://news.social-protocols.org/stats?id=41389787) #11 6 points 0 comments -> [OpenTofu is not so open](https://github.com/opentofu/registry/pull/824)<!-- HN:41389787:end --><!-- HN:41393462:start -->
* [41393462](https://news.social-protocols.org/stats?id=41393462) #22 22 points 6 comments -> [Rust Is Bad for Servers](https://kerkour.com/rust-is-bad-for-servers)<!-- HN:41393462:end --><!-- HN:41344245:start -->
* [41344245](https://news.social-protocols.org/stats?id=41344245) #16 132 points 50 comments -> [All Texts in Brooklyn](https://brooklyn.alltexts.nyc/)<!-- HN:41344245:end --><!-- HN:41342078:start -->
* [41342078](https://news.social-protocols.org/stats?id=41342078) #22 62 points 16 comments -> [Shufflecake: Plausible deniability for hidden filesystems on Linux (2023)](https://eprint.iacr.org/2023/1529)<!-- HN:41342078:end -->
#### **Friday, August 30, 2024**
<!-- HN:41349554:start -->
* [41349554](https://news.social-protocols.org/stats?id=41349554) #12 43 points 4 comments -> [Build an Infinite Canvas](https://infinitecanvas.cc/)<!-- HN:41349554:end --><!-- HN:41348869:start -->
* [41348869](https://news.social-protocols.org/stats?id=41348869) #19 5 points 0 comments -> [Colorful Ribbon Diagrams Became the Face of Proteins](https://www.quantamagazine.org/how-colorful-ribbon-diagrams-became-the-face-of-proteins-20240823/)<!-- HN:41348869:end --><!-- HN:41398480:start -->
* [41398480](https://news.social-protocols.org/stats?id=41398480) #6 5 points 1 comments -> [Grandma trapped in elevator for six days survived by rationing groceries](https://www.guinnessworldrecords.com/news/2024/1/grandma-trapped-in-elevator-for-six-days-survived-by-rationing-groceries-763381)<!-- HN:41398480:end --><!-- HN:41399249:start -->
* [41399249](https://news.social-protocols.org/stats?id=41399249) #13 7 points 8 comments -> [Bay Watch: Northern California is an energy catastrophe waiting to happen](https://newsletter.doomberg.com/p/bay-watch)<!-- HN:41399249:end --><!-- HN:41400570:start -->
* [41400570](https://news.social-protocols.org/stats?id=41400570) #21 5 points 0 comments -> [Web Kid Anand is a typical high schooler–except for his megahot site. (1999)](https://money.cnn.com/magazines/fsb/fsb_archive/1999/12/01/271048/index.htm)<!-- HN:41400570:end --><!-- HN:41400523:start -->
* [41400523](https://news.social-protocols.org/stats?id=41400523) #29 5 points 1 comments -> [AI cameras spot toddlers not wearing seat belts](https://www.bbc.com/news/articles/c5y3pdp099zo)<!-- HN:41400523:end -->
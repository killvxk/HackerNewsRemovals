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

#### **Thursday, August 8, 2024**<!-- HN:41186212:start -->
* [41186212](https://news.social-protocols.org/stats?id=41186212) #27 20 points 40 comments -> [Terraforming Mars may be easier than scientists thought](https://www.science.org/content/article/terraforming-mars-could-be-easier-scientists-thought)<!-- HN:41186212:end --><!-- HN:41187445:start -->
* [41187445](https://news.social-protocols.org/stats?id=41187445) #28 10 points 0 comments -> [Holodomor](https://en.wikipedia.org/wiki/Holodomor)<!-- HN:41187445:end --><!-- HN:41144685:start -->
* [41144685](https://news.social-protocols.org/stats?id=41144685) #17 97 points 9 comments -> [R5N - Obfuscated mesh routing on hostile networks.](https://lsd.gnunet.org/lsd0004/draft-schanzen-r5n.html)<!-- HN:41144685:end --><!-- HN:41145204:start -->
* [41145204](https://news.social-protocols.org/stats?id=41145204) #17 16 points 4 comments -> [Ancient Stars (and a Thought on SETI)](https://www.centauri-dreams.org/2024/08/02/on-ancient-stars-and-a-thought-on-seti/)<!-- HN:41145204:end --><!-- HN:41188292:start -->
* [41188292](https://news.social-protocols.org/stats?id=41188292) #3 44 points 8 comments -> [ISS astronauts on eight-day mission may be stuck until 2025, NASA says](https://www.theguardian.com/science/article/2024/aug/07/spacex-delay-international-space-station-boeing-nasa)<!-- HN:41188292:end --><!-- HN:41189494:start -->
* [41189494](https://news.social-protocols.org/stats?id=41189494) #27 6 points 2 comments -> [Open Source AWS SDK Code Examples: Your Go-To Resource for Cloud Development](https://github.com/awsdocs/aws-doc-sdk-examples)<!-- HN:41189494:end --><!-- HN:41189946:start -->
* [41189946](https://news.social-protocols.org/stats?id=41189946) #23 141 points 162 comments -> [The News Is Information Junk Food (2022)](https://chuck.is/news/)<!-- HN:41189946:end --><!-- HN:41189138:start -->
* [41189138](https://news.social-protocols.org/stats?id=41189138) #26 19 points 7 comments -> [Fallout 2 Remake 3D](https://jonasz-o.itch.io/fallout2remake3d)<!-- HN:41189138:end --><!-- HN:41191689:start -->
* [41191689](https://news.social-protocols.org/stats?id=41191689) #24 7 points 0 comments -> [CrowdStrike releases root cause analysis of the global Microsoft breakdown](https://www.abc.net.au/news/2024-08-07/drt-crowdstrike-root-cause-analysis/104193866)<!-- HN:41191689:end --><!-- HN:41191818:start -->
* [41191818](https://news.social-protocols.org/stats?id=41191818) #21 8 points 1 comments -> [Google and Meta ignored their own rules in secret teen-targeting ad deals](https://arstechnica.com/tech-policy/2024/08/google-and-meta-ignored-their-own-rules-in-secret-teen-targeting-ad-deals/)<!-- HN:41191818:end --><!-- HN:41192744:start -->
* [41192744](https://news.social-protocols.org/stats?id=41192744) #25 12 points 1 comments -> [Journalist Charged with a Hate Crime for Recording a Gaza Protest Action](https://theintercept.com/2024/08/08/journalist-hate-crime-gaza-protest/)<!-- HN:41192744:end --><!-- HN:41193507:start -->
* [41193507](https://news.social-protocols.org/stats?id=41193507) #7 4 points 1 comments -> [Dairy Queen's Soft Serve Isn't What You Think It Is](https://www.thetakeout.com/1630132/dairy-queen-not-ice-cream/)<!-- HN:41193507:end --><!-- HN:41193859:start -->
* [41193859](https://news.social-protocols.org/stats?id=41193859) #8 21 points 9 comments -> [GPT-4o System Card](https://openai.com/index/gpt-4o-system-card/)<!-- HN:41193859:end --><!-- HN:41195375:start -->
* [41195375](https://news.social-protocols.org/stats?id=41195375) #7 14 points 19 comments -> [New doctoral thesis proposes Buckminster Fuller was a 'charlatan'](https://research.aalto.fi/en/publications/genius-or-charlatanry-a-psychobiographical-reinterpretation-of-th)<!-- HN:41195375:end --><!-- HN:41196669:start -->
* [41196669](https://news.social-protocols.org/stats?id=41196669) #27 4 points 3 comments -> [The Outrageous Rise of Neotoddlerism](https://www.gurwinder.blog/p/the-outrageous-rise-of-neotoddlerism)<!-- HN:41196669:end -->
#### **Friday, August 9, 2024**
<!-- HN:41150451:start -->
* [41150451](https://news.social-protocols.org/stats?id=41150451) #19 36 points 42 comments -> ["Grip Car"](https://teenage.engineering/products/grip-car)<!-- HN:41150451:end --><!-- HN:41146766:start -->
* [41146766](https://news.social-protocols.org/stats?id=41146766) #5 26 points 3 comments -> [Rise of the New York Tech Scene](https://newsletter.rhizomerd.com/p/rise-of-the-new-york-tech-scene)<!-- HN:41146766:end --><!-- HN:41147452:start -->
* [41147452](https://news.social-protocols.org/stats?id=41147452) #13 34 points 13 comments -> [Harmonic Function Theory](https://www.axler.net/HFT.html)<!-- HN:41147452:end --><!-- HN:41199006:start -->
* [41199006](https://news.social-protocols.org/stats?id=41199006) #2 11 points 9 comments -> [AI Pastor: Your Guide to Spiritual Growth](https://ai-pastor.com)<!-- HN:41199006:end --><!-- HN:41199363:start -->
* [41199363](https://news.social-protocols.org/stats?id=41199363) #8 4 points 1 comments -> [A powerful tool for converting speech into text](https://app.trintai.com/)<!-- HN:41199363:end --><!-- HN:41199109:start -->
* [41199109](https://news.social-protocols.org/stats?id=41199109) #11 21 points 19 comments -> [I built a second brain tool for college students](https://ainotebook.app/)<!-- HN:41199109:end --><!-- HN:41196554:start -->
* [41196554](https://news.social-protocols.org/stats?id=41196554) #12 124 points 198 comments -> [National Park Service Will Cite AWD Drivers for Driving on 4WD-Only Trails](https://jalopnik.com/national-park-service-will-cite-drivers-of-awd-cars-for-1851617315)<!-- HN:41196554:end --><!-- HN:41195124:start -->
* [41195124](https://news.social-protocols.org/stats?id=41195124) #14 177 points 186 comments -> [Intel's Immiseration](https://thechipletter.substack.com/p/intels-immiseration)<!-- HN:41195124:end --><!-- HN:41198358:start -->
* [41198358](https://news.social-protocols.org/stats?id=41198358) #15 52 points 23 comments -> [Don't write Rust like it's Java](https://jgayfer.com/dont-write-rust-like-java/)<!-- HN:41198358:end --><!-- HN:41199515:start -->
* [41199515](https://news.social-protocols.org/stats?id=41199515) #18 54 points 16 comments -> [If you give Copilot the reins, don't be surprised when it spills your secrets](https://www.theregister.com/2024/08/08/copilot_black_hat_vulns/)<!-- HN:41199515:end --><!-- HN:41200810:start -->
* [41200810](https://news.social-protocols.org/stats?id=41200810) #21 8 points 1 comments -> [ChatGPT now lets free users generate up to two images per day made by DALL-E 3](https://www.theverge.com/2024/8/8/24216348/chatgpt-free-users-dall-e-3-images)<!-- HN:41200810:end --><!-- HN:41156638:start -->
* [41156638](https://news.social-protocols.org/stats?id=41156638) #25 63 points 11 comments -> [DIY Raspberry Pi 1000 turns a Raspberry Pi 5 into a PC-in-a-keyboard](https://liliputing.com/diy-raspberry-pi-1000-turns-a-raspberry-pi-5-into-a-pc-in-a-keyboard/)<!-- HN:41156638:end --><!-- HN:41195584:start -->
* [41195584](https://news.social-protocols.org/stats?id=41195584) #26 165 points 211 comments -> [Apple is America's semiconductor problem](https://www.semiconductor-digest.com/apple-is-americas-semiconductor-problem/)<!-- HN:41195584:end --><!-- HN:41201062:start -->
* [41201062](https://news.social-protocols.org/stats?id=41201062) #17 6 points 0 comments -> [When No Building Is Allowed: Inside the Satmar Hassidic Takeover of a Small Town](https://danfrank.ca/the-challenge-of-building-new-cities-inside-the-satmar-hassidic-takeover-of-bloomingburg/)<!-- HN:41201062:end --><!-- HN:41200391:start -->
* [41200391](https://news.social-protocols.org/stats?id=41200391) #22 19 points 10 comments -> [U.S. Athletes Are Taking Full Advantage of Free Healthcare in Olympic Village](https://www.si.com/olympics/american-athletes-taking-full-advantage-of-free-healthcare-olympic-village-france)<!-- HN:41200391:end --><!-- HN:41201294:start -->
* [41201294](https://news.social-protocols.org/stats?id=41201294) #17 3 points 1 comments -> [Do autistic people lack creativity, or are the measures of creativity lacking?](https://www.psychologytoday.com/ca/blog/mom-am-i-disabled/201612/autism-and-creativity)<!-- HN:41201294:end --><!-- HN:41200825:start -->
* [41200825](https://news.social-protocols.org/stats?id=41200825) #29 11 points 9 comments -> [What do scientists tell us about boxing's gender row?](https://www.bbc.com/news/articles/crlr8gp813ko)<!-- HN:41200825:end --><!-- HN:41201868:start -->
* [41201868](https://news.social-protocols.org/stats?id=41201868) #2 4 points 0 comments -> [Exposing the Wayland Lie (2018)](https://catfox.life/2018/07/31/exposing-the-wayland-lie/)<!-- HN:41201868:end --><!-- HN:41165409:start -->
* [41165409](https://news.social-protocols.org/stats?id=41165409) #14 -> [The Anatomy of Brainwashing](https://www.science.org/doi/10.1126/science.adp1705)<!-- HN:41165409:end --><!-- HN:41201892:start -->
* [41201892](https://news.social-protocols.org/stats?id=41201892) #20 5 points 1 comments -> [Sinkclose Flaw in AMD Chips Allows Infections](https://www.wired.com/story/amd-chip-sinkclose-flaw/)<!-- HN:41201892:end --><!-- HN:41200720:start -->
* [41200720](https://news.social-protocols.org/stats?id=41200720) #5 21 points 7 comments -> [Show HN: I created a Next.js CLI to ship code like a hacker](https://www.nextinject.pro)<!-- HN:41200720:end --><!-- HN:41201630:start -->
* [41201630](https://news.social-protocols.org/stats?id=41201630) #14 29 points 10 comments -> [The Rise of Neotoddlerism: how society encourages activists to act like infants](https://www.gurwinder.blog/p/the-outrageous-rise-of-neotoddlerism)<!-- HN:41201630:end --><!-- HN:41202059:start -->
* [41202059](https://news.social-protocols.org/stats?id=41202059) #16 4 points 0 comments -> [NYC Subway Riders See 'Exceptionally High' Air Pollution](https://www.bloomberg.com/news/articles/2024-08-07/new-york-city-subway-commuters-face-high-pm2-5-exposure)<!-- HN:41202059:end --><!-- HN:41201783:start -->
* [41201783](https://news.social-protocols.org/stats?id=41201783) #15 8 points 13 comments -> [What Happens When Ozempic Takes over Your Town](https://www.bloomberg.com/news/features/2024-08-07/ozempic-boom-inside-usa-s-weight-loss-drug-capital)<!-- HN:41201783:end --><!-- HN:41201562:start -->
* [41201562](https://news.social-protocols.org/stats?id=41201562) #18 44 points 49 comments -> [Boeing Starliner Could Brick ISS Docking Port If Crew Abandons It](https://jalopnik.com/boeing-starliner-could-brick-iss-docking-port-if-crew-a-1851615463)<!-- HN:41201562:end --><!-- HN:41202380:start -->
* [41202380](https://news.social-protocols.org/stats?id=41202380) #16 5 points 0 comments -> [ICANN reserves .internal for private use at the DNS level](https://www.theregister.com/2024/08/08/dot_internal_ratified/)<!-- HN:41202380:end --><!-- HN:41202574:start -->
* [41202574](https://news.social-protocols.org/stats?id=41202574) #4 3 points 0 comments -> [Developers hate their job, but like to code outside work](https://newsletter.techworld-with-milan.com/p/developer-hate-their-job-but-like)<!-- HN:41202574:end --><!-- HN:41202300:start -->
* [41202300](https://news.social-protocols.org/stats?id=41202300) #16 6 points 1 comments -> [Why do big digital projects in the public sector fail?](https://www.newstatesman.com/spotlight/tech-regulation/public-sector-tech/2024/07/public-sector-digital-transformation-projects-government-nhs-horizon)<!-- HN:41202300:end --><!-- HN:41202683:start -->
* [41202683](https://news.social-protocols.org/stats?id=41202683) #19 6 points 1 comments -> [Third-Party RISC-V Framework Laptop Mainboard](https://frame.work/de/de/blog/introducing-a-new-risc-v-mainboard-from-deepcomputing)<!-- HN:41202683:end --><!-- HN:41202213:start -->
* [41202213](https://news.social-protocols.org/stats?id=41202213) #21 7 points 0 comments -> [You're Not Indecisive, You're Unbiased](https://www.sciencealert.com/youre-not-indecisive-youre-unbiased-science-says-so)<!-- HN:41202213:end --><!-- HN:41203057:start -->
* [41203057](https://news.social-protocols.org/stats?id=41203057) #15 4 points 1 comments -> [Why, Are Ultraprocessed Foods So Hard to Resist?](https://www.nytimes.com/2024/07/30/well/eat/ultraprocessed-foods-diet-study.html)<!-- HN:41203057:end --><!-- HN:41202788:start -->
* [41202788](https://news.social-protocols.org/stats?id=41202788) #14 12 points 9 comments -> [Robocars improve traffic even when most cars around them are driven by people](https://theconversation.com/robocars-promise-to-improve-traffic-even-when-most-of-the-cars-around-them-are-driven-by-people-study-finds-233546)<!-- HN:41202788:end --><!-- HN:41203411:start -->
* [41203411](https://news.social-protocols.org/stats?id=41203411) #1 8 points 1 comments -> [Africa CDC to Declare First-Ever Continental Health Emergency as Mpox Surges](https://healthpolicy-watch.news/africa-cdc-to-declare-first-ever-continental-health-emergency-as-mpox-surges/)<!-- HN:41203411:end --><!-- HN:41203784:start -->
* [41203784](https://news.social-protocols.org/stats?id=41203784) #23 3 points 0 comments -> ['Like, what?': USA's Ariana Ramsey blown away by free healthcare at Olympics](https://www.theguardian.com/sport/article/2024/aug/09/ariana-ramsey-free-healthcare-usa-olympic-village-paris-rugby)<!-- HN:41203784:end --><!-- HN:41203934:start -->
* [41203934](https://news.social-protocols.org/stats?id=41203934) #26 5 points 2 comments -> [Galea: The most advanced biosensing VR headset](https://galea.co/)<!-- HN:41203934:end --><!-- HN:41205175:start -->
* [41205175](https://news.social-protocols.org/stats?id=41205175) #23 6 points 0 comments -> [A wonderful coincidence or an expected connection: why π² ≈ g](https://roitman.io/blog/91)<!-- HN:41205175:end --><!-- HN:41156534:start -->
* [41156534](https://news.social-protocols.org/stats?id=41156534) #23 28 points 40 comments -> [Photino: A lighter Electron](https://www.tryphotino.io/)<!-- HN:41156534:end --><!-- HN:41205799:start -->
* [41205799](https://news.social-protocols.org/stats?id=41205799) #30 6 points 0 comments -> [Virginia Mandates Paper Ballots, Tracking, Proof of Residency for 2024 Election](https://www.thecentersquare.com/virginia/article_d7053154-54f3-11ef-bbfd-938cffe3feff.html)<!-- HN:41205799:end --><!-- HN:41205745:start -->
* [41205745](https://news.social-protocols.org/stats?id=41205745) #26 6 points 0 comments -> [Lawyer bought HarrisWalz.com years ago. Now, he's sold it](https://www.cbc.ca/radio/asithappens/harris-walz-domaine-1.7288782)<!-- HN:41205745:end --><!-- HN:41205656:start -->
* [41205656](https://news.social-protocols.org/stats?id=41205656) #30 6 points 0 comments -> [Warner Bros. Discovery pretty much wiped the Cartoon Network website](https://www.theverge.com/2024/8/9/24216846/warner-bros-discovery-cartoon-network-website-wiped-max)<!-- HN:41205656:end -->
#### **Saturday, August 10, 2024**
<!-- HN:41206384:start -->
* [41206384](https://news.social-protocols.org/stats?id=41206384) #23 7 points 1 comments -> [Flaw in AMD Chips Allows Virtually Unfixable Infections](https://www.wired.com/story/amd-chip-sinkclose-flaw/)<!-- HN:41206384:end --><!-- HN:41154895:start -->
* [41154895](https://news.social-protocols.org/stats?id=41154895) #10 182 points 27 comments -> [Jerk](https://ivanish.ca/jerk/)<!-- HN:41154895:end --><!-- HN:41159075:start -->
* [41159075](https://news.social-protocols.org/stats?id=41159075) #24 96 points 24 comments -> [Harder Drive: Hard drives we didn't want or need (2022) [pdf]](http://tom7.org/papers/murphy2022harder.pdf)<!-- HN:41159075:end --><!-- HN:41161672:start -->
* [41161672](https://news.social-protocols.org/stats?id=41161672) #25 15 points 7 comments -> [Show HN: PlatePlanner – Design Beautiful Platemaps](https://plateplanner.nitro.bio/)<!-- HN:41161672:end --><!-- HN:41207446:start -->
* [41207446](https://news.social-protocols.org/stats?id=41207446) #10 144 points 31 comments -> [Former YouTube CEO Susan Wojcicki Has Died](https://www.threads.net/@crumbler/post/C-ecdHJxHMq)<!-- HN:41207446:end --><!-- HN:41207317:start -->
* [41207317](https://news.social-protocols.org/stats?id=41207317) #11 60 points 3 comments -> [Google Strategy Doc from Antitrust Proceedings](https://threadreaderapp.com/thread/1821554841786683554.html)<!-- HN:41207317:end --><!-- HN:41207274:start -->
* [41207274](https://news.social-protocols.org/stats?id=41207274) #13 14 points 13 comments -> [The Red Herring of Red Flags: Why Resumes Are a Relic of the Past](https://praachi.work/blog/red-flags-resumes.html)<!-- HN:41207274:end --><!-- HN:41176091:start -->
* [41176091](https://news.social-protocols.org/stats?id=41176091) #21 10 points 2 comments -> [Keynote Speech to the 1996 Oopsla Convention](https://www.patternlanguage.com/archive/ieee.html)<!-- HN:41176091:end --><!-- HN:41208252:start -->
* [41208252](https://news.social-protocols.org/stats?id=41208252) #12 7 points 4 comments -> [Does Astrology Work?](https://www.clearerthinking.org/post/does-astrology-work)<!-- HN:41208252:end --><!-- HN:41208265:start -->
* [41208265](https://news.social-protocols.org/stats?id=41208265) #14 8 points 1 comments -> [Chinese drones will fly trash out of Everest slopes](https://kathmandupost.com/money/2024/08/05/it-s-official-chinese-drones-will-fly-trash-out-of-everest-slopes)<!-- HN:41208265:end --><!-- HN:41209502:start -->
* [41209502](https://news.social-protocols.org/stats?id=41209502) #15 5 points 1 comments -> [Two men jailed for social media posts that stirred up far-right violence](https://www.theguardian.com/politics/article/2024/aug/09/two-men-jailed-for-social-media-posts-that-stirred-up-far-right-violence)<!-- HN:41209502:end --><!-- HN:41208923:start -->
* [41208923](https://news.social-protocols.org/stats?id=41208923) #20 31 points 2 comments -> [Susan Wojcicki, Former Chief of YouTube, Dies at 56](https://www.nytimes.com/2024/08/10/business/susan-wojcicki-dead.html)<!-- HN:41208923:end --><!-- HN:41209625:start -->
* [41209625](https://news.social-protocols.org/stats?id=41209625) #4 38 points 23 comments -> [Cookware company includes artificial customer prompts in website](https://thestaub.com/)<!-- HN:41209625:end --><!-- HN:41210469:start -->
* [41210469](https://news.social-protocols.org/stats?id=41210469) #12 10 points 5 comments -> [Online sports betting hurts consumers](https://www.slowboring.com/p/online-sports-betting-hurts-consumers)<!-- HN:41210469:end --><!-- HN:41210221:start -->
* [41210221](https://news.social-protocols.org/stats?id=41210221) #16 6 points 4 comments -> [Simple CLI Tool for Optimizing Your CSS Files](https://github.com/happer64bit/style-eyes)<!-- HN:41210221:end --><!-- HN:41211303:start -->
* [41211303](https://news.social-protocols.org/stats?id=41211303) #25 13 points 1 comments -> ['It's devastating': summer in Canada's Arctic region brings heatwaves](https://www.theguardian.com/world/article/2024/aug/08/canada-arctic-region-heat-wave)<!-- HN:41211303:end --><!-- HN:41211475:start -->
* [41211475](https://news.social-protocols.org/stats?id=41211475) #14 14 points 2 comments -> [Defcon Response to Badge Issues](https://twitter.com/defcon/status/1822344607063302200)<!-- HN:41211475:end --><!-- HN:41167340:start -->
* [41167340](https://news.social-protocols.org/stats?id=41167340) #9 4 points 1 comments -> [Touch Wood: The Roman Phallus as a Lucky Charm](https://www.athenaartfoundation.org/read/ancient-roman-phallus)<!-- HN:41167340:end --><!-- HN:41210994:start -->
* [41210994](https://news.social-protocols.org/stats?id=41210994) #29 -> [Millions of years for plants to recover from global warming](https://www.sciencedaily.com/releases/2024/08/240809135943.htm)<!-- HN:41210994:end --><!-- HN:41211147:start -->
* [41211147](https://news.social-protocols.org/stats?id=41211147) #14 19 points 2 comments -> [Fobos SDR: High-Quality Radio for Hobbyists, Researchers and Professionals](https://www.hackster.io/news/fobos-sdr-is-a-high-quality-radio-for-hobbyists-researchers-and-professionals-80e25e00b1e1)<!-- HN:41211147:end --><!-- HN:41211215:start -->
* [41211215](https://news.social-protocols.org/stats?id=41211215) #25 31 points 41 comments -> [Waymo got a ticket and there was confusion about who or what was being ticketed](https://twitter.com/antoniogm/status/1822141923538161776)<!-- HN:41211215:end -->
#### **Sunday, August 11, 2024**
<!-- HN:41214540:start -->
* [41214540](https://news.social-protocols.org/stats?id=41214540) #27 6 points 1 comments -> [Why I bet on DSPy](https://blog.isaacbmiller.com/posts/dspy)<!-- HN:41214540:end --><!-- HN:41208671:start -->
* [41208671](https://news.social-protocols.org/stats?id=41208671) #6 4 points 0 comments -> [Two ancient North American structures crumble as tribes see impending doom](https://nypost.com/2024/08/09/world-news/ancient-pyramids-collapse-in-mexico-in-what-tribe-calls-bad-omen/)<!-- HN:41208671:end --><!-- HN:41180356:start -->
* [41180356](https://news.social-protocols.org/stats?id=41180356) #18 100 points 17 comments -> [A/B testing mistakes I learned the hard way](https://newsletter.posthog.com/p/ab-testing-mistakes-i-learned-the)<!-- HN:41180356:end --><!-- HN:41215685:start -->
* [41215685](https://news.social-protocols.org/stats?id=41215685) #5 40 points 10 comments -> [The Authoritarian Playbook](https://protectdemocracy.org/work/the-authoritarian-playbook/)<!-- HN:41215685:end --><!-- HN:41215927:start -->
* [41215927](https://news.social-protocols.org/stats?id=41215927) #19 49 points 38 comments -> [X's likelihood of prevailing in boycott suit is higher than I thought](https://shaungallagher.pressbin.com/blog/group-boycotts.html)<!-- HN:41215927:end --><!-- HN:41216399:start -->
* [41216399](https://news.social-protocols.org/stats?id=41216399) #8 6 points 18 comments -> [The Coffee Machine Hiring Test](https://manuel.darcemont.fr/posts/coffee-machine-test/)<!-- HN:41216399:end --><!-- HN:41218675:start -->
* [41218675](https://news.social-protocols.org/stats?id=41218675) #6 15 points 0 comments -> [UK police commish threatens to extradite, jail US citizens over online posts](https://www.foxnews.com/media/uk-police-commissioner-threatens-extradite-jail-us-citizens-over-social-media-posts-we-come-afte)<!-- HN:41218675:end --><!-- HN:41186735:start -->
* [41186735](https://news.social-protocols.org/stats?id=41186735) #18 11 points 2 comments -> [Study finds organizations have a significant gap in security on macOS endpoints](https://9to5mac.com/2024/08/05/new-study-finds-organizations-have-a-significant-gap-in-security-on-macos-systems/)<!-- HN:41186735:end --><!-- HN:41218721:start -->
* [41218721](https://news.social-protocols.org/stats?id=41218721) #18 14 points 4 comments -> [Instagram Is Over](https://www.theatlantic.com/technology/archive/2022/11/instagram-tiktok-twitter-social-media-competition/672305/)<!-- HN:41218721:end --><!-- HN:41218844:start -->
* [41218844](https://news.social-protocols.org/stats?id=41218844) #24 9 points 0 comments -> [The coming religious war in Europe and how it may be averted](https://subhashkak.medium.com/the-coming-religious-war-in-europe-and-how-it-may-be-avoided-52029359b30d)<!-- HN:41218844:end --><!-- HN:41218706:start -->
* [41218706](https://news.social-protocols.org/stats?id=41218706) #27 40 points 15 comments -> [Atlas: A Windows modification to optimize performance, privacy and usability](https://atlasos.net/)<!-- HN:41218706:end --><!-- HN:41219325:start -->
* [41219325](https://news.social-protocols.org/stats?id=41219325) #17 13 points 2 comments -> [UK police commissioner threatens to extradite,jail US citizens over online posts](https://www.foxnews.com/media/uk-police-commissioner-threatens-extradite-jail-us-citizens-over-social-media-posts-we-come-afte)<!-- HN:41219325:end -->
#### **Monday, August 12, 2024**
<!-- HN:41182376:start -->
* [41182376](https://news.social-protocols.org/stats?id=41182376) #11 15 points 10 comments -> [Y'all are sleeping on HTTP/3](https://kmcd.dev/posts/yall-are-sleeping-on-http3/)<!-- HN:41182376:end --><!-- HN:41217229:start -->
* [41217229](https://news.social-protocols.org/stats?id=41217229) #30 27 points 40 comments -> [Fair Source: Sustainability with no customer risk](https://pepicrft.me/blog/2024/08/13/open-tuist)<!-- HN:41217229:end --><!-- HN:41220233:start -->
* [41220233](https://news.social-protocols.org/stats?id=41220233) #14 -> [AMD's processors have been shipping with a dangerous security bug](https://www.interest.co.nz/technology/129141/researchers-suggest-throw-away-your-computer-if-sinkclose-flaw-amd-processors)<!-- HN:41220233:end --><!-- HN:41178000:start -->
* [41178000](https://news.social-protocols.org/stats?id=41178000) #19 -> [1 vs. 1000 guitar picks (5000 picks/second) [video]](https://www.youtube.com/watch?v=H4VgGn2tPWc)<!-- HN:41178000:end --><!-- HN:41221558:start -->
* [41221558](https://news.social-protocols.org/stats?id=41221558) #18 47 points 41 comments -> [I Quit Spotify](https://www.newyorker.com/culture/infinite-scroll/why-i-finally-quit-spotify)<!-- HN:41221558:end --><!-- HN:41221814:start -->
* [41221814](https://news.social-protocols.org/stats?id=41221814) #18 36 points 12 comments -> [Box2D 3.0 Released](https://box2d.org/posts/2024/08/releasing-box2d-3.0/)<!-- HN:41221814:end --><!-- HN:41221403:start -->
* [41221403](https://news.social-protocols.org/stats?id=41221403) #21 60 points 30 comments -> [UN Cybercrime Convention to Overrule Bank Secrecy](https://www.therage.co/un-cybercrime-convention-bank-secrecy/)<!-- HN:41221403:end --><!-- HN:41223145:start -->
* [41223145](https://news.social-protocols.org/stats?id=41223145) #13 10 points 8 comments -> [The Decline of Etiquette and the Rise of 'Boundaries'](https://www.theatlantic.com/family/archive/2022/11/people-oversharing-tmi-friendship-boundaries/671970/)<!-- HN:41223145:end --><!-- HN:41223476:start -->
* [41223476](https://news.social-protocols.org/stats?id=41223476) #18 8 points 0 comments -> [American IQ Scores Have Rapidly Dropped, Proving the 'Reverse Flynn Effect'](https://www.popularmechanics.com/science/a43469569/american-iq-scores-decline-reverse-flynn-effect/)<!-- HN:41223476:end --><!-- HN:41223471:start -->
* [41223471](https://news.social-protocols.org/stats?id=41223471) #19 4 points 0 comments -> [American IQs Are Dropping. Here's Why It Might Not Be a Bad Thing](https://www.fatherly.com/news/american-iq-study-dropping-what-it-means)<!-- HN:41223471:end --><!-- HN:41221235:start -->
* [41221235](https://news.social-protocols.org/stats?id=41221235) #30 24 points 10 comments -> [Show HN: Simple Science – The Newest Science Explained Simply](https://simplescience.ai)<!-- HN:41221235:end --><!-- HN:41224009:start -->
* [41224009](https://news.social-protocols.org/stats?id=41224009) #4 11 points 2 comments -> [2024 Paris Olympics: No, breaking shouldn't be an Olympic sport](https://sports.yahoo.com/2024-paris-olympics-no-breaking-shouldnt-be-an-olympic-sport-190421401.html)<!-- HN:41224009:end --><!-- HN:41224164:start -->
* [41224164](https://news.social-protocols.org/stats?id=41224164) #15 23 points 8 comments -> [Google Down](https://downdetector.com/status/google/)<!-- HN:41224164:end --><!-- HN:41225238:start -->
* [41225238](https://news.social-protocols.org/stats?id=41225238) #11 9 points 2 comments -> [Iran Emerges as the Most Aggressive Foreign Threat to U.S. Election](https://www.wsj.com/politics/national-security/iran-emerges-as-the-most-aggressive-foreign-threat-to-u-s-election-b61161ad)<!-- HN:41225238:end --><!-- HN:41226147:start -->
* [41226147](https://news.social-protocols.org/stats?id=41226147) #7 34 points 7 comments -> [Apple to take 30% of all Patreon donations](https://twitter.com/KenneyNL/status/1822996361551184290)<!-- HN:41226147:end --><!-- HN:41225795:start -->
* [41225795](https://news.social-protocols.org/stats?id=41225795) #20 10 points 1 comments -> [Apple's requirements are about to hit creators and fans on Patreon](https://microsite-news.pages.dev/articles/understanding-apple-requirements-for-patreon)<!-- HN:41225795:end --><!-- HN:41224905:start -->
* [41224905](https://news.social-protocols.org/stats?id=41224905) #17 14 points 6 comments -> [Genie: Best AI Software Engineer](https://cosine.sh/genie)<!-- HN:41224905:end --><!-- HN:41224749:start -->
* [41224749](https://news.social-protocols.org/stats?id=41224749) #5 166 points 62 comments -> [Postgres.new](https://postgres.new/)<!-- HN:41224749:end -->
#### **Tuesday, August 13, 2024**
<!-- HN:41188496:start -->
* [41188496](https://news.social-protocols.org/stats?id=41188496) #14 5 points 1 comments -> [Just Say It, Henry](https://www.lrb.co.uk/the-paper/v46/n16/colin-burrow/just-say-it-henry)<!-- HN:41188496:end --><!-- HN:41182895:start -->
* [41182895](https://news.social-protocols.org/stats?id=41182895) #27 136 points 125 comments -> [Poetry Was an Official Olympic Event for Nearly 40 Years. What Happened?](https://www.smithsonianmag.com/history/poetry-was-an-official-olympic-event-for-nearly-40-years-what-happened-180984838/)<!-- HN:41182895:end --><!-- HN:41232054:start -->
* [41232054](https://news.social-protocols.org/stats?id=41232054) #26 8 points 0 comments -> [Auto-Generated Transcript of Musk-Trump Twitter Space](https://gist.githubusercontent.com/bubbaprog/1eb29610374ff9f458a37a648a4004e1/raw/212ad823d62f7c2948749b976f7a0fa7cda046d9/gistfile1.txt)<!-- HN:41232054:end --><!-- HN:41232133:start -->
* [41232133](https://news.social-protocols.org/stats?id=41232133) #10 11 points 4 comments -> [Texas builds clean power – but it isn't a climate champion](https://ketanjoshi.co/2024/08/12/texas-builds-clean-power-but-it-isnt-a-climate-champion/)<!-- HN:41232133:end --><!-- HN:41232317:start -->
* [41232317](https://news.social-protocols.org/stats?id=41232317) #11 6 points 2 comments -> [Show HN: I manually curated 130 modern AI Agents and platforms](https://aiagentsdirectory.com/)<!-- HN:41232317:end --><!-- HN:41234180:start -->
* [41234180](https://news.social-protocols.org/stats?id=41234180) #24 37 points 41 comments -> [Core Python developer suspended for three months](https://www.theregister.com/2024/08/09/core_python_developer_suspended_coc/)<!-- HN:41234180:end --><!-- HN:41228579:start -->
* [41228579](https://news.social-protocols.org/stats?id=41228579) #30 71 points 10 comments -> [TP-Link GPL Code Center](https://www.tp-link.com/us/support/gpl-code/)<!-- HN:41228579:end --><!-- HN:41231731:start -->
* [41231731](https://news.social-protocols.org/stats?id=41231731) #22 310 points 252 comments -> [Brands should avoid the term 'AI'. It's turning off customers](https://www.cnn.com/2024/08/10/business/brands-avoid-term-customers/index.html)<!-- HN:41231731:end --><!-- HN:41234382:start -->
* [41234382](https://news.social-protocols.org/stats?id=41234382) #19 5 points 0 comments -> [Rethinking the Nature of Light](https://chatgpt.com/share/9296f553-d36d-4c02-b73d-31b1058afe60)<!-- HN:41234382:end --><!-- HN:41231145:start -->
* [41231145](https://news.social-protocols.org/stats?id=41231145) #17 201 points 44 comments -> [Mastering Osint: How to Find Information on Anyone](https://osintteam.blog/mastering-osint-how-to-find-information-on-anyone-680e4086f17f)<!-- HN:41231145:end --><!-- HN:41236649:start -->
* [41236649](https://news.social-protocols.org/stats?id=41236649) #28 15 points 0 comments -> [WHO to scrap weak PFAS drinking water guidelines after alleged corruption](https://www.theguardian.com/us-news/article/2024/aug/13/world-health-organization-pfas-drinking-water-health-guidelines)<!-- HN:41236649:end --><!-- HN:41212380:start -->
* [41212380](https://news.social-protocols.org/stats?id=41212380) #24 17 points 3 comments -> [Go structs are copied on assignment](https://jvns.ca/blog/2024/08/06/go-structs-copied-on-assignment/)<!-- HN:41212380:end -->
#### **Wednesday, August 14, 2024**
<!-- HN:41242280:start -->
* [41242280](https://news.social-protocols.org/stats?id=41242280) #9 18 points 9 comments -> [Japan's Leader, Fumio Kishida, Will Step Down](https://www.nytimes.com/2024/08/13/world/asia/fumio-kishida-japan-prime-minister.html)<!-- HN:41242280:end --><!-- HN:41220532:start -->
* [41220532](https://news.social-protocols.org/stats?id=41220532) #21 25 points 1 comments -> [CVBasic v0.6.0: The retro Z80 BASIC compiler now targets 6502](https://github.com/nanochess/CVBasic)<!-- HN:41220532:end -->
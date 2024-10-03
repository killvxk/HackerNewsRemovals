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

#### **Friday, September 27, 2024**<!-- HN:41665045:start -->
* [41665045](https://news.social-protocols.org/stats?id=41665045) #18 35 points 54 comments -> [Sam Altman denied that there are plans for him to receive a giant equity stake](https://www.cnbc.com/2024/09/26/openais-sam-altman-tells-employees-he-didnt-get-giant-equity-stake.html)<!-- HN:41665045:end --><!-- HN:41665630:start -->
* [41665630](https://news.social-protocols.org/stats?id=41665630) #25 30 points 40 comments -> [Should Sports Betting Be Banned?](https://www.maximum-progress.com/p/should-sports-betting-be-banned)<!-- HN:41665630:end --><!-- HN:41667393:start -->
* [41667393](https://news.social-protocols.org/stats?id=41667393) #18 7 points 1 comments -> [Bugs Found in Cups](https://www.thestack.technology/critical-9-9-linux-bug-cups-your-ears-the-details-are-now-here/)<!-- HN:41667393:end --><!-- HN:41666945:start -->
* [41666945](https://news.social-protocols.org/stats?id=41666945) #25 146 points 104 comments -> [Microsoft's new Outlook client moves your email to the cloud](https://www.xda-developers.com/privacy-implications-new-microsoft-outlook/)<!-- HN:41666945:end --><!-- HN:41668451:start -->
* [41668451](https://news.social-protocols.org/stats?id=41668451) #14 21 points 40 comments -> [Leak claims RTX 5090 has 600W TGP, RTX 5080 hits 400W](https://www.tomshardware.com/pc-components/gpus/leak-claims-rtx-5090-has-600w-tgp-rtx-5080-hits-400w-up-to-21760-cores-32gb-vram-512-bit-bus)<!-- HN:41668451:end --><!-- HN:41669964:start -->
* [41669964](https://news.social-protocols.org/stats?id=41669964) #6 8 points 6 comments -> [Dev Starter Pack: The essential startup starter kit](https://devstarterpack.io/)<!-- HN:41669964:end --><!-- HN:41670543:start -->
* [41670543](https://news.social-protocols.org/stats?id=41670543) #14 26 points 42 comments -> [I've Soured on Open Source](https://greaterdanorequalto.com/ive-soured-on-open-source/)<!-- HN:41670543:end --><!-- HN:41671548:start -->
* [41671548](https://news.social-protocols.org/stats?id=41671548) #24 12 points 12 comments -> [Just stop oil protesters sentenced 2years for throwing soup on Van Gogh painting](https://juststopoil.org/2024/09/27/sent-down-for-throwing-soup-judge-hehir-turns-state-repression-into-an-art-form/)<!-- HN:41671548:end --><!-- HN:41675713:start -->
* [41675713](https://news.social-protocols.org/stats?id=41675713) #14 4 points 2 comments -> [Tell HN: AI Safety projects in need of volunteers](https://www.aisafety.com/projects)<!-- HN:41675713:end --><!-- HN:41675671:start -->
* [41675671](https://news.social-protocols.org/stats?id=41675671) #30 32 points 40 comments -> [WP Engine Reprieve](https://wordpress.org/news/2024/09/wp-engine-reprieve/)<!-- HN:41675671:end --><!-- HN:41635730:start -->
* [41635730](https://news.social-protocols.org/stats?id=41635730) #18 11 points 0 comments -> [How we threw 10 quantum bit designs in the trash](https://vidnova.com/how-we-threw-10-quantum-bits-in-the-trash/)<!-- HN:41635730:end -->
#### **Saturday, September 28, 2024**
<!-- HN:41636093:start -->
* [41636093](https://news.social-protocols.org/stats?id=41636093) #21 3 points 8 comments -> [I built an AI tool to track my hair loss, here's what I learned](https://www.myhair.ai/)<!-- HN:41636093:end --><!-- HN:41677669:start -->
* [41677669](https://news.social-protocols.org/stats?id=41677669) #2 -> [A small area of solar panels plus storage cannot power the world](https://alexepstein.substack.com/p/refuting-the-myth-that-just-a-small)<!-- HN:41677669:end --><!-- HN:41678259:start -->
* [41678259](https://news.social-protocols.org/stats?id=41678259) #29 8 points 1 comments -> [I locked myself in my apartment for 4 years to build this humanoid](https://twitter.com/lethic1/status/1839909404973642137)<!-- HN:41678259:end --><!-- HN:41678392:start -->
* [41678392](https://news.social-protocols.org/stats?id=41678392) #7 8 points 13 comments -> [C is not Turing-complete (2018)](https://memo.barrucadu.co.uk/c-is-not-turing-complete.html)<!-- HN:41678392:end --><!-- HN:41640397:start -->
* [41640397](https://news.social-protocols.org/stats?id=41640397) #15 9 points 5 comments -> [Mysterious Nazca Glyphs Have Just Been Revealed](https://www.sciencealert.com/hundreds-of-mysterious-nazca-glyphs-have-just-been-revealed)<!-- HN:41640397:end --><!-- HN:41670186:start -->
* [41670186](https://news.social-protocols.org/stats?id=41670186) #13 214 points 64 comments -> [MTA Open Data Challenge](https://new.mta.info/article/mta-open-data-challenge)<!-- HN:41670186:end --><!-- HN:41679019:start -->
* [41679019](https://news.social-protocols.org/stats?id=41679019) #29 6 points 0 comments -> [Exponential growth brews 1M AI models on Hugging Face](https://arstechnica.com/information-technology/2024/09/ai-hosting-platform-surpasses-1-million-models-for-the-first-time/)<!-- HN:41679019:end --><!-- HN:41673317:start -->
* [41673317](https://news.social-protocols.org/stats?id=41673317) #30 58 points 35 comments -> [Ceefax and the Birth of Interactive TV](https://www.bbc.com/articles/cvg360rr91zo)<!-- HN:41673317:end --><!-- HN:41679185:start -->
* [41679185](https://news.social-protocols.org/stats?id=41679185) #29 15 points 10 comments -> [Hyundai Faces New Theft Threat from "Game Boy" Hack](https://headlight.news/2024/07/08/hyundai-faces-new-theft-threat-from-game-boy-hack/)<!-- HN:41679185:end --><!-- HN:41638775:start -->
* [41638775](https://news.social-protocols.org/stats?id=41638775) #30 26 points 29 comments -> [Grocery Territories of America](https://www.washingtonpost.com/business/interactive/2024/grocery-store-owners-map-kroger-albertsons-merger/)<!-- HN:41638775:end --><!-- HN:41678784:start -->
* [41678784](https://news.social-protocols.org/stats?id=41678784) #20 7 points 2 comments -> [Show HN: Privacy DNS – free, encrypted, no-logs, DoH, DoT, DoQ, DNSProxy](https://privacy-dns.pw/)<!-- HN:41678784:end --><!-- HN:41680221:start -->
* [41680221](https://news.social-protocols.org/stats?id=41680221) #23 3 points 4 comments -> [Kamala Harris' Chances Surge in Major Election Forecast](https://www.newsweek.com/kamala-harris-polling-surge-forecast-1960686)<!-- HN:41680221:end --><!-- HN:41680313:start -->
* [41680313](https://news.social-protocols.org/stats?id=41680313) #20 -> [Entire HR Team Fired After Manager's Own Resume Gets Auto-Rejected](https://www.ibtimes.co.uk/lazy-mediocre-hr-team-fired-after-managers-own-cv-gets-auto-rejected-seconds-exposing-system-1727202)<!-- HN:41680313:end --><!-- HN:41641577:start -->
* [41641577](https://news.social-protocols.org/stats?id=41641577) #25 24 points 10 comments -> [Windows Server 2008 IA64 Guest on HP Integrity VM (HP-UX)](https://virtuallyfun.com/2024/09/23/windows-server-2008-ia64-guest-on-hp-integrity-vm-hp-ux/)<!-- HN:41641577:end --><!-- HN:41680579:start -->
* [41680579](https://news.social-protocols.org/stats?id=41680579) #8 5 points 0 comments -> [Goodbye API. Hello RSQL](https://rsql.io/index.html)<!-- HN:41680579:end --><!-- HN:41680127:start -->
* [41680127](https://news.social-protocols.org/stats?id=41680127) #24 21 points 42 comments -> [As Florida Storms Worsen, Some in Tampa Bay Wonder: Is Living There Worth It?](https://www.nytimes.com/2024/09/28/us/hurricane-helene-tampa-bay-florida-worries.html)<!-- HN:41680127:end --><!-- HN:41681393:start -->
* [41681393](https://news.social-protocols.org/stats?id=41681393) #16 4 points 0 comments -> [Iframely GDPR Considerations](https://iframely.com/docs/gdpr)<!-- HN:41681393:end --><!-- HN:41681113:start -->
* [41681113](https://news.social-protocols.org/stats?id=41681113) #27 8 points 6 comments -> [Eric Adams Staffer Left FBI Interview to Delete Encrypted Chat Apps](https://theintercept.com/2024/09/27/eric-adams-indictment-encrypted-messaging-apps/)<!-- HN:41681113:end --><!-- HN:41682034:start -->
* [41682034](https://news.social-protocols.org/stats?id=41682034) #19 4 points 0 comments -> [SpaceX launches Crew-9 with two people to bring back Boeing crew](https://www.nasaspaceflight.com/2024/09/crew-9-launch/)<!-- HN:41682034:end -->
#### **Sunday, September 29, 2024**
<!-- HN:41632681:start -->
* [41632681](https://news.social-protocols.org/stats?id=41632681) #14 119 points 70 comments -> [The human heart shows signs of ageing after just a month in space](https://www.nature.com/articles/d41586-024-03105-x)<!-- HN:41632681:end --><!-- HN:41634141:start -->
* [41634141](https://news.social-protocols.org/stats?id=41634141) #21 75 points 81 comments -> [New Laser Could Cram GPS Alternative into a Shoebox](https://spectrum.ieee.org/alternative-for-gps)<!-- HN:41634141:end --><!-- HN:41683580:start -->
* [41683580](https://news.social-protocols.org/stats?id=41683580) #30 18 points 12 comments -> [Jeremy Clarkson Says All Modern Cars 'Are Shit'](https://jalopnik.com/jeremy-clarkson-says-all-modern-cars-are-sh-t-1851659364)<!-- HN:41683580:end --><!-- HN:41683217:start -->
* [41683217](https://news.social-protocols.org/stats?id=41683217) #20 93 points 2 comments -> [Four more health care workers ill after caring for bird flu case in Missouri](https://www.statnews.com/2024/09/27/bird-flu-missouri-four-more-healthcare-workers/)<!-- HN:41683217:end --><!-- HN:41684445:start -->
* [41684445](https://news.social-protocols.org/stats?id=41684445) #13 15 points 5 comments -> [America's Young Men Are Falling Even Further Behind](https://www.wsj.com/lifestyle/careers/young-american-men-lost-c1d799f7)<!-- HN:41684445:end --><!-- HN:41683715:start -->
* [41683715](https://news.social-protocols.org/stats?id=41683715) #20 15 points 27 comments -> [What the heck is going on with WordPress?](https://paolo.blog/blog/what-the-heck-is-going-on-with-wordpress/)<!-- HN:41683715:end --><!-- HN:41646094:start -->
* [41646094](https://news.social-protocols.org/stats?id=41646094) #5 12 points 1 comments -> [Hyperscalers are carving up the ocean floor into private internet highways](https://www.theregister.com/2024/09/25/aspi_hyperscaler_cables/)<!-- HN:41646094:end --><!-- HN:41686107:start -->
* [41686107](https://news.social-protocols.org/stats?id=41686107) #8 48 points 11 comments -> [The world knows Wim Hof as "The Iceman", his family suffered domestic violence](https://www.volkskrant.nl/kijkverder/v/2024/the-outside-world-knows-wim-hof-as-the-eccentric-iceman-his-family-suffered-domestic-violence~v1176564/)<!-- HN:41686107:end --><!-- HN:41686688:start -->
* [41686688](https://news.social-protocols.org/stats?id=41686688) #17 7 points 4 comments -> [Just stop oil soups two more Van goghs hours after sentencing of earlier souping](https://twitter.com/JustStop_Oil/status/1839670072530317423)<!-- HN:41686688:end --><!-- HN:41689051:start -->
* [41689051](https://news.social-protocols.org/stats?id=41689051) #5 6 points 0 comments -> [Ro'im Rachok is an IDF unit for autistic adults](https://en.wikipedia.org/wiki/Ro%27im_Rachok)<!-- HN:41689051:end --><!-- HN:41689355:start -->
* [41689355](https://news.social-protocols.org/stats?id=41689355) #5 8 points 2 comments -> [When, why, and how to stop coding as your day job](https://kevingoldsmith.substack.com/p/when-why-and-how-to-stop-coding-as)<!-- HN:41689355:end --><!-- HN:41689394:start -->
* [41689394](https://news.social-protocols.org/stats?id=41689394) #21 5 points 0 comments -> [Cite-seeing and reviewing: A study on citation bias in peer review](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0283980)<!-- HN:41689394:end --><!-- HN:41689865:start -->
* [41689865](https://news.social-protocols.org/stats?id=41689865) #9 10 points 4 comments -> [Stop Using Generative AI for Hero Images](https://leejo.github.io/2024/09/29/holding_out_for_the_heros_to_fuck_off/)<!-- HN:41689865:end --><!-- HN:41689714:start -->
* [41689714](https://news.social-protocols.org/stats?id=41689714) #26 33 points 10 comments -> [Ted Kaczynski's Low-Tech Lifestyle](https://www.thetedkarchive.com/library/ted-kaczynski-ted-kaczynski-s-low-tech-lifestyle)<!-- HN:41689714:end -->
#### **Monday, September 30, 2024**<!-- HN:41695630:start -->
* [41695630](https://news.social-protocols.org/stats?id=41695630) #2 38 points 31 comments -> [A guide to working remote and not paying rent](https://ghuntley.com/freecamping/)<!-- HN:41695630:end --><!-- HN:41695327:start -->
* [41695327](https://news.social-protocols.org/stats?id=41695327) #12 14 points 0 comments -> [Exxon Mobil's 'Advanced' Technique for Recycling Plastic? Burning It](https://www.yahoo.com/news/exxon-mobil-says-advanced-recycling-100018708.html)<!-- HN:41695327:end --><!-- HN:41694563:start -->
* [41694563](https://news.social-protocols.org/stats?id=41694563) #19 77 points 8 comments -> [Raspberry Pi AI Camera on sale now at $70](https://www.raspberrypi.com/news/raspberry-pi-ai-camera-on-sale-now/)<!-- HN:41694563:end --><!-- HN:41687707:start -->
* [41687707](https://news.social-protocols.org/stats?id=41687707) #10 371 points 110 comments -> [Some Go web dev notes](https://jvns.ca/blog/2024/09/27/some-go-web-dev-notes/)<!-- HN:41687707:end --><!-- HN:41667287:start -->
* [41667287](https://news.social-protocols.org/stats?id=41667287) #17 5 points 0 comments -> [A Bendy RISC-V Processor](https://spectrum.ieee.org/flexible-risc-v)<!-- HN:41667287:end --><!-- HN:41695800:start -->
* [41695800](https://news.social-protocols.org/stats?id=41695800) #26 9 points 1 comments -> [Your Computer Is Not Yours](https://sneak.berlin/20201112/your-computer-isnt-yours/)<!-- HN:41695800:end --><!-- HN:41689159:start -->
* [41689159](https://news.social-protocols.org/stats?id=41689159) #26 88 points 12 comments -> [CPU Throttling for containerized Go applications explained](https://kanishk.io/posts/cpu-throttling-in-containerized-go-apps/)<!-- HN:41689159:end --><!-- HN:41696402:start -->
* [41696402](https://news.social-protocols.org/stats?id=41696402) #8 15 points 18 comments -> [Distinct movement cluster evident on Carola bridge in Dresden prior to collapse](https://www.newcivilengineer.com/latest/distinct-movement-cluster-evident-on-carola-bridge-in-dresden-prior-to-its-collapse-research-finds-17-09-2024/)<!-- HN:41696402:end --><!-- HN:41646978:start -->
* [41646978](https://news.social-protocols.org/stats?id=41646978) #21 67 points 15 comments -> [Hunting for Gems: How Ruby's package management system evolved](https://www.railsexplained.com/pages/hunting-for-gems/)<!-- HN:41646978:end --><!-- HN:41696855:start -->
* [41696855](https://news.social-protocols.org/stats?id=41696855) #20 3 points 0 comments -> [The messy WordPress drama, explained](https://www.theverge.com/2024/9/27/24256361/wordpress-wp-engine-drama-explained-matt-mullenweg)<!-- HN:41696855:end --><!-- HN:41689449:start -->
* [41689449](https://news.social-protocols.org/stats?id=41689449) #28 108 points 11 comments -> [Ruby Meetups](https://rubyconferences.org/meetups/)<!-- HN:41689449:end --><!-- HN:41698907:start -->
* [41698907](https://news.social-protocols.org/stats?id=41698907) #2 44 points 40 comments -> [A Burrito Is a Monad](http://williamcotton.com/articles/a-burrito-is-a-monad)<!-- HN:41698907:end --><!-- HN:41698988:start -->
* [41698988](https://news.social-protocols.org/stats?id=41698988) #4 13 points 4 comments -> [Convince Frodo to give you the ring](https://darkfrodo.com/check)<!-- HN:41698988:end --><!-- HN:41699584:start -->
* [41699584](https://news.social-protocols.org/stats?id=41699584) #8 10 points 2 comments -> [Hartford Public High School grad can't read](https://ctmirror.org/2024/09/29/cant-read-high-school-ct-hartford/)<!-- HN:41699584:end --><!-- HN:41646782:start -->
* [41646782](https://news.social-protocols.org/stats?id=41646782) #23 101 points 41 comments -> [Awala: The computer network on which humankind can rely](https://awala.network/)<!-- HN:41646782:end --><!-- HN:41652735:start -->
* [41652735](https://news.social-protocols.org/stats?id=41652735) #2 46 points 8 comments -> [Library of Congress Pre-1915 Japanese Woodblock Prints and Drawings](https://www.loc.gov/collections/japanese-fine-prints-pre-1915/about-this-collection/)<!-- HN:41652735:end --><!-- HN:41701868:start -->
* [41701868](https://news.social-protocols.org/stats?id=41701868) #27 6 points 1 comments -> [Systems used by courts and governments across US riddled with vulnerabilities](https://arstechnica.com/security/2024/09/systems-used-by-courts-and-govs-across-the-us-riddled-with-vulnerabilities/)<!-- HN:41701868:end --><!-- HN:41701820:start -->
* [41701820](https://news.social-protocols.org/stats?id=41701820) #24 9 points 3 comments -> ['Doomsday' glacier set to melt faster and swell seas as world heats up](https://phys.org/news/2024-09-doomsday-glacier-faster-seas-world.html)<!-- HN:41701820:end --><!-- HN:41701026:start -->
* [41701026](https://news.social-protocols.org/stats?id=41701026) #9 8 points 1 comments -> [Seven things I wish I would not hear as an autist](https://www.superdurszlak.dev/posts/seven-things-i-wish-i-would-not-hear-as-an-autist/)<!-- HN:41701026:end --><!-- HN:41653148:start -->
* [41653148](https://news.social-protocols.org/stats?id=41653148) #3 64 points 24 comments -> [Paramotorists soar across remote Peru desert to collect threatened plants](https://phys.org/news/2024-09-extreme-botany-paramotorists-soar-remote.html)<!-- HN:41653148:end --><!-- HN:41702388:start -->
* [41702388](https://news.social-protocols.org/stats?id=41702388) #30 7 points 0 comments -> [Georgia BioLab plant fire sparks evacuations after plume releases chlorine](https://www.washingtonpost.com/nation/2024/09/30/conyers-ga-chemical-plant-fire/)<!-- HN:41702388:end --><!-- HN:41702610:start -->
* [41702610](https://news.social-protocols.org/stats?id=41702610) #22 6 points 0 comments -> [Germany to Enforce DMA Regulations for All Microsoft Products and Services](https://www.thurrott.com/microsoft/310470/germany-to-enforce-dma-regulations-for-all-microsoft-products-and-services)<!-- HN:41702610:end --><!-- HN:41703109:start -->
* [41703109](https://news.social-protocols.org/stats?id=41703109) #1 8 points 0 comments -> [Minitel: The Online World France Built Before the Web](https://spectrum.ieee.org/minitel-the-online-world-france-built-before-the-web)<!-- HN:41703109:end -->
#### **Tuesday, October 1, 2024**
<!-- HN:41703304:start -->
* [41703304](https://news.social-protocols.org/stats?id=41703304) #15 5 points 1 comments -> [Apple TV+ Pivoting Movie Strategy Amid Disappointing Performance](https://www.macrumors.com/2024/09/30/report-apple-tv-pivoting-movie-strategy/)<!-- HN:41703304:end --><!-- HN:41666707:start -->
* [41666707](https://news.social-protocols.org/stats?id=41666707) #19 4 points 0 comments -> [A Guide to Destructuring in JavaScript](https://piccalil.li/blog/a-guide-to-destructuring-in-javascript/)<!-- HN:41666707:end --><!-- HN:41704201:start -->
* [41704201](https://news.social-protocols.org/stats?id=41704201) #20 4 points 0 comments -> [19,000 Starlink Terminals not active in NC because of FCC](https://innovationnation.blog/p/the-helene-communication-breakdown)<!-- HN:41704201:end --><!-- HN:41703797:start -->
* [41703797](https://news.social-protocols.org/stats?id=41703797) #10 20 points 2 comments -> [Essential Node in Global Semiconductor Supply Chain Hit by Hurricane Helene](https://hntrbrk.com/essential-node-in-global-semiconductor-supply-chain-hit-by-hurricane-helene-video-reveals-entrance-to-mine-has-flooded/)<!-- HN:41703797:end --><!-- HN:41704083:start -->
* [41704083](https://news.social-protocols.org/stats?id=41704083) #16 48 points 6 comments -> [Reddit policy changes make sitewide protests nearly impossible](https://www.engadget.com/big-tech/reddit-policy-changes-make-sitewide-protests-nearly-impossible-183754240.html)<!-- HN:41704083:end --><!-- HN:41663524:start -->
* [41663524](https://news.social-protocols.org/stats?id=41663524) #5 32 points 6 comments -> [A coffee table that walks](https://www.core77.com/posts/133657/A-Coffee-Table-that-Walks)<!-- HN:41663524:end --><!-- HN:41705002:start -->
* [41705002](https://news.social-protocols.org/stats?id=41705002) #19 5 points 0 comments -> [Thunderbird for Android Beta has been released](https://github.com/thunderbird/thunderbird-android/releases/tag/THUNDERBIRD_8_0b1)<!-- HN:41705002:end --><!-- HN:41705259:start -->
* [41705259](https://news.social-protocols.org/stats?id=41705259) #17 10 points 0 comments -> [President Jimmy Carter becomes the first US president to live to 100 years old](https://www.usatoday.com/videos/news/politics/2024/09/30/jimmy-carter-former-us-president-celebrates-100th-birthday/75450406007/)<!-- HN:41705259:end --><!-- HN:41706334:start -->
* [41706334](https://news.social-protocols.org/stats?id=41706334) #14 8 points 1 comments -> [Godot Game Engine Self Destructs [video]](https://www.youtube.com/watch?v=KTB6ofgkgn0)<!-- HN:41706334:end --><!-- HN:41706306:start -->
* [41706306](https://news.social-protocols.org/stats?id=41706306) #2 7 points 6 comments -> [I built a website starter kit for my side hustles](https://suf.io/blog/why-i-built-a-seo-website-starter-kit/)<!-- HN:41706306:end --><!-- HN:41706581:start -->
* [41706581](https://news.social-protocols.org/stats?id=41706581) #6 20 points 40 comments -> [UK workers must keep all customer tips under new law](https://www.bbc.co.uk/news/articles/czj9mxnyezdo)<!-- HN:41706581:end --><!-- HN:41706491:start -->
* [41706491](https://news.social-protocols.org/stats?id=41706491) #26 12 points 9 comments -> [New, unique fusion reactor comes together due to global research collaboration](https://phys.org/news/2024-09-unique-fusion-reactor-due-global.html)<!-- HN:41706491:end --><!-- HN:41707462:start -->
* [41707462](https://news.social-protocols.org/stats?id=41707462) #5 4 points 2 comments -> [Redot Engine – Multi-platform 2D and 3D game engine](https://github.com/Redot-Engine/redot-engine)<!-- HN:41707462:end --><!-- HN:41672014:start -->
* [41672014](https://news.social-protocols.org/stats?id=41672014) #21 4 points 4 comments -> [Make: Magazine and Maker faire open a community round](https://makethings.make.co/p/a-community-round)<!-- HN:41672014:end --><!-- HN:41707119:start -->
* [41707119](https://news.social-protocols.org/stats?id=41707119) #5 8 points 3 comments -> ["Switzerland is as deeply polarized as the USA"](https://www.news.uzh.ch/en/articles/news/2024/political-polarization.html)<!-- HN:41707119:end --><!-- HN:41710805:start -->
* [41710805](https://news.social-protocols.org/stats?id=41710805) #20 8 points 1 comments -> [Iran Launches Missiles at Israel](https://www.nbcnews.com/news/world/live-blog/israel-hezbollah-live-updates-idf-ground-operation-lebanon-rcna173389)<!-- HN:41710805:end --><!-- HN:41710971:start -->
* [41710971](https://news.social-protocols.org/stats?id=41710971) #26 -> [Iran has launched missiles toward Israel, the Israeli military says](https://www.cnn.com/world/live-news/israel-lebanon-war-hezbollah-10-1-24-intl-hnk/index.html)<!-- HN:41710971:end --><!-- HN:41708127:start -->
* [41708127](https://news.social-protocols.org/stats?id=41708127) #9 221 points 2 comments -> [Mozilla's lapse in judgement causes clash with uBlock Origin developer](https://www.ghacks.net/2024/10/01/mozillas-massive-lapse-in-judgement-causes-clash-with-ublock-origin-developer/)<!-- HN:41708127:end --><!-- HN:41711477:start -->
* [41711477](https://news.social-protocols.org/stats?id=41711477) #11 15 points 1 comments -> [Iran launches missile attack on Israel](https://www.cnbc.com/2024/10/01/iran-readying-imminent-ballistic-missile-attack-against-israel-us-official-tells-nbc-news.html)<!-- HN:41711477:end --><!-- HN:41711329:start -->
* [41711329](https://news.social-protocols.org/stats?id=41711329) #17 -> [Iranian Ballistic Missiles Rain Down on Israel](https://www.twz.com/news-features/iranian-ballistic-missiles-rain-down-on-israel)<!-- HN:41711329:end --><!-- HN:41711556:start -->
* [41711556](https://news.social-protocols.org/stats?id=41711556) #30 7 points 1 comments -> [OpenAI Announces Realtime Voice API](https://twitter.com/swyx/status/1841168635878129758)<!-- HN:41711556:end --><!-- HN:41711861:start -->
* [41711861](https://news.social-protocols.org/stats?id=41711861) #30 21 points 14 comments -> [Iran just launched over 400 ballistic missiles at Israel](https://www.wsj.com/world/middle-east/iran-ballistic-missile-attack-israel-8c418294)<!-- HN:41711861:end -->
#### **Wednesday, October 2, 2024**
<!-- HN:41714056:start -->
* [41714056](https://news.social-protocols.org/stats?id=41714056) #25 31 points 40 comments -> [What happens if someone votes by absentee/mail-in and dies before Election Day?](https://ballotpedia.org/What_happens_if_someone_votes_by_absentee/mail-in_ballot_and_dies_before_Election_Day%3F_(2024))<!-- HN:41714056:end --><!-- HN:41716102:start -->
* [41716102](https://news.social-protocols.org/stats?id=41716102) #8 18 points 14 comments -> [The Nobel Prize in Economics Is Fake](https://www.chibus.com/perspectives/2024/2/13/the-nobel-prize-in-economics-is-fake)<!-- HN:41716102:end --><!-- HN:41668372:start -->
* [41668372](https://news.social-protocols.org/stats?id=41668372) #10 69 points 10 comments -> [Nobody knows what happened within the MMC Association in 1998](https://sdomi.pl/weblog/21-nobody-knows-what-happened-at-mmca/)<!-- HN:41668372:end --><!-- HN:41717466:start -->
* [41717466](https://news.social-protocols.org/stats?id=41717466) #4 64 points 11 comments -> [Show HN: Weird Books to Read](https://bizarrebookshelf.com/)<!-- HN:41717466:end --><!-- HN:41716975:start -->
* [41716975](https://news.social-protocols.org/stats?id=41716975) #24 137 points 49 comments -> [Nvidia releases NVLM 1.0 72B open weight model](https://huggingface.co/nvidia/NVLM-D-72B)<!-- HN:41716975:end --><!-- HN:41688088:start -->
* [41688088](https://news.social-protocols.org/stats?id=41688088) #19 57 points 7 comments -> [PC Floppy Copy Protection: Vault Prolok](https://martypc.blogspot.com/2024/09/pc-floppy-copy-protection-vault-prolok.html)<!-- HN:41688088:end --><!-- HN:41719610:start -->
* [41719610](https://news.social-protocols.org/stats?id=41719610) #16 28 points 40 comments -> [GitHub's Copilot lies about its documentation. Why would I trust it with my code](https://shkspr.mobi/blog/2024/10/githubs-copilot-lies-about-its-own-documentation-so-why-would-i-trust-it-with-my-code/)<!-- HN:41719610:end --><!-- HN:41717174:start -->
* [41717174](https://news.social-protocols.org/stats?id=41717174) #28 27 points 4 comments -> [Dashi – A Streamlit Like Framework for Rubyists](https://thedayisntgray.github.io/now/2024/10/01/dashi-preview/)<!-- HN:41717174:end --><!-- HN:41719764:start -->
* [41719764](https://news.social-protocols.org/stats?id=41719764) #18 15 points 8 comments -> [Yoshua Bengio: Humanity faces a 'catastrophic' future if we don't regulate AI](https://www.livescience.com/technology/artificial-intelligence/people-always-say-these-risks-are-science-fiction-but-they-re-not-godfather-of-ai-yoshua-bengio-on-the-risks-of-machine-intelligence-to-humanity)<!-- HN:41719764:end --><!-- HN:41719680:start -->
* [41719680](https://news.social-protocols.org/stats?id=41719680) #20 11 points 3 comments -> [Former Nintendo factory in Kyoto opens as nostalgia-fuelled gaming museum](https://www.theguardian.com/games/2024/oct/02/former-nintendo-factory-in-kyoto-opens-as-nostalgia-fuelled-gaming-museum)<!-- HN:41719680:end --><!-- HN:41720685:start -->
* [41720685](https://news.social-protocols.org/stats?id=41720685) #19 35 points 37 comments -> [Famous AI Artist Says He's Losing Millions from People Stealing His Work](https://gizmodo.com/famous-ai-artist-says-hes-losing-millions-of-dollars-from-people-stealing-his-work-2000505822)<!-- HN:41720685:end --><!-- HN:41721947:start -->
* [41721947](https://news.social-protocols.org/stats?id=41721947) #24 7 points 2 comments -> [2 years after entering the graphics card game, Intel has nothing to show for it](https://www.theregister.com/2024/10/02/intel_aib_market_share/)<!-- HN:41721947:end --><!-- HN:41721885:start -->
* [41721885](https://news.social-protocols.org/stats?id=41721885) #3 4 points 3 comments -> [The Republic of Palau Becomes ITU's 194th Member State](https://www.itu.int:443/en/mediacentre/Pages/PR-2024-09-19-the-Republic-of-Palau-becomes-ITUs-194th-Member-State.aspx)<!-- HN:41721885:end --><!-- HN:41688499:start -->
* [41688499](https://news.social-protocols.org/stats?id=41688499) #15 40 points 27 comments -> [Porting OpenVMS to the Itanium Processor Family (2003)[pdf]](https://de.openvms.org/TUD2004/Itanium.PDF)<!-- HN:41688499:end --><!-- HN:41694509:start -->
* [41694509](https://news.social-protocols.org/stats?id=41694509) #26 6 points 0 comments -> [How to manage dangerous actions in user interfaces](https://www.smashingmagazine.com/2024/09/how-manage-dangerous-actions-user-interfaces/)<!-- HN:41694509:end --><!-- HN:41722532:start -->
* [41722532](https://news.social-protocols.org/stats?id=41722532) #7 5 points 0 comments -> [MM1.5: Methods, Analysis and Insights from Multimodal LLM Fine-Tuning](https://arxiv.org/abs/2409.20566)<!-- HN:41722532:end --><!-- HN:41723333:start -->
* [41723333](https://news.social-protocols.org/stats?id=41723333) #26 9 points 0 comments -> [OpenAI just raised $6.6B to build ever-larger AI models](https://www.theverge.com/2024/10/2/24260457/openai-funding-round-thrive-capital-6-billion)<!-- HN:41723333:end --><!-- HN:41695549:start -->
* [41695549](https://news.social-protocols.org/stats?id=41695549) #22 43 points 6 comments -> [Show HN: Pipet – CLI tool for scraping and extracting data online, with pipes](https://github.com/bjesus/pipet)<!-- HN:41695549:end --><!-- HN:41724957:start -->
* [41724957](https://news.social-protocols.org/stats?id=41724957) #26 3 points 0 comments -> [Meta smart glasses can be used to dox anyone in seconds, study finds](https://arstechnica.com/tech-policy/2024/10/harvard-students-make-auto-doxxing-smart-glasses-to-show-need-for-privacy-regs/)<!-- HN:41724957:end --><!-- HN:41725558:start -->
* [41725558](https://news.social-protocols.org/stats?id=41725558) #4 10 points 22 comments -> [Show HN: End-to-End Encrypted Dead Man's Switch](https://www.cipherwill.com/)<!-- HN:41725558:end -->
#### **Thursday, October 3, 2024**
<!-- HN:41726056:start -->
* [41726056](https://news.social-protocols.org/stats?id=41726056) #22 4 points 0 comments -> [Nvidia stunned the world with a ChatGPT rival that's as good as GPT-4o](https://bgr.com/tech/nvidia-stunned-the-world-with-a-chatgpt-rival-thats-as-good-as-gpt-4o/)<!-- HN:41726056:end --><!-- HN:41695158:start -->
* [41695158](https://news.social-protocols.org/stats?id=41695158) #20 4 points 0 comments -> [What Can a Coffee Machine Teach You About Python's Functions?](https://www.thepythoncodingstack.com/p/coffee-machine-python-function-analogy)<!-- HN:41695158:end --><!-- HN:41725584:start -->
* [41725584](https://news.social-protocols.org/stats?id=41725584) #7 7 points 0 comments -> [Code in Database vs. Code in Application](https://brandur.org/fragments/code-database-vs-app)<!-- HN:41725584:end --><!-- HN:41726724:start -->
* [41726724](https://news.social-protocols.org/stats?id=41726724) #8 8 points 4 comments -> [Watch as Tesla burns in flooded Florida garage days after Hurricane Helene](https://www.heraldtribune.com/story/weather/hurricane/2024/10/01/hurricane-helene-tesla-fire-breaks-out-in-flooded-florida-garage/75469839007/)<!-- HN:41726724:end --><!-- HN:41701339:start -->
* [41701339](https://news.social-protocols.org/stats?id=41701339) #26 10 points 6 comments -> [The box problem that baffled the boffins](https://www.theguardian.com/science/2024/sep/30/did-you-solve-it-the-box-problem-that-baffled-the-boffins)<!-- HN:41701339:end --><!-- HN:41727375:start -->
* [41727375](https://news.social-protocols.org/stats?id=41727375) #25 6 points 1 comments -> [A student built a fusion reactor at home in just 4 weeks using $2k and AI](https://bgr.com/science/a-student-built-a-fusion-reactor-at-home-in-just-4-weeks-using-2000-and-ai/)<!-- HN:41727375:end --><!-- HN:41686326:start -->
* [41686326](https://news.social-protocols.org/stats?id=41686326) #4 59 points 8 comments -> [Study: Cats in little crocheted hats shed light on feline chronic pain](https://arstechnica.com/science/2024/09/scientists-crocheted-tiny-hats-for-cats-to-record-eegs-of-brain-response-to-pain/)<!-- HN:41686326:end --><!-- HN:41728408:start -->
* [41728408](https://news.social-protocols.org/stats?id=41728408) #19 3 points 1 comments -> [Popular ad blocker uBlock Origin Lite pulled from Firefox store](https://www.pcworld.com/article/2474353/popular-ad-blocker-removed-from-firefox-extension-store.html)<!-- HN:41728408:end --><!-- HN:41727776:start -->
* [41727776](https://news.social-protocols.org/stats?id=41727776) #21 30 points 40 comments -> [Microsoft: 'ever present' AI assistants are coming](https://www.bbc.co.uk/news/articles/czj9vmnlv9zo)<!-- HN:41727776:end --><!-- HN:41729793:start -->
* [41729793](https://news.social-protocols.org/stats?id=41729793) #22 3 points 1 comments -> [UK will give sovereignty of Chagos Islands to Mauritius](https://www.bbc.com/news/articles/c98ynejg4l5o)<!-- HN:41729793:end --><!-- HN:41687950:start -->
* [41687950](https://news.social-protocols.org/stats?id=41687950) #16 80 points 57 comments -> [Salt Water Dimmers](https://en.wikipedia.org/wiki/Salt_water_dimmers)<!-- HN:41687950:end --><!-- HN:41728859:start -->
* [41728859](https://news.social-protocols.org/stats?id=41728859) #18 38 points 36 comments -> [We avoid effort even though it can improve our well-being](https://www.newscientist.com/article/mg26435110-700-why-we-avoid-effort-even-though-it-can-improve-our-well-being/)<!-- HN:41728859:end -->
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

#### **Tuesday, September 24, 2024**
<!-- HN:41631995:start -->
* [41631995](https://news.social-protocols.org/stats?id=41631995) #18 6 points 2 comments -> ["Traffic Violence": The Grifters Go After Cars](https://albertcory50.substack.com/p/traffic-violence-the-grifters-go)<!-- HN:41631995:end --><!-- HN:41632606:start -->
* [41632606](https://news.social-protocols.org/stats?id=41632606) #6 5 points 2 comments -> [Bootstrapped to 10K Users: Is B2B the Only Way to Monetize?](https://www.jobsolv.com/)<!-- HN:41632606:end --><!-- HN:41579268:start -->
* [41579268](https://news.social-protocols.org/stats?id=41579268) #12 347 points 36 comments -> [GPU Puzzles](https://github.com/srush/GPU-Puzzles)<!-- HN:41579268:end --><!-- HN:41587350:start -->
* [41587350](https://news.social-protocols.org/stats?id=41587350) #19 5 points 0 comments -> [Retrowin32: Redoing Syscalls](https://neugierig.org/software/blog/2024/09/retrowin32-syscalls.html)<!-- HN:41587350:end --><!-- HN:41582756:start -->
* [41582756](https://news.social-protocols.org/stats?id=41582756) #22 42 points 45 comments -> [The Death of LCDs, Means New Life for Chips](https://timculpan.substack.com/p/the-death-of-lcds-means-new-life)<!-- HN:41582756:end --><!-- HN:41585509:start -->
* [41585509](https://news.social-protocols.org/stats?id=41585509) #24 35 points 4 comments -> [The Many Lives of James Lovelock by Jonathan Watts – Man of Many Myths](https://www.theguardian.com/books/article/2024/sep/14/the-many-lives-of-james-lovelock-by-jonathan-watts-man-of-many-myths)<!-- HN:41585509:end --><!-- HN:41603270:start -->
* [41603270](https://news.social-protocols.org/stats?id=41603270) #11 8 points 2 comments -> [Compress JPG: The Image Compressor That Lets You Compress Images Securely](https://compressjpg.io/)<!-- HN:41603270:end --><!-- HN:41633628:start -->
* [41633628](https://news.social-protocols.org/stats?id=41633628) #2 7 points 5 comments -> [You'll own nothing and be happy- Jaguar Land Rover now offer a car subscription](https://www.drivepivotal.com/)<!-- HN:41633628:end --><!-- HN:41633626:start -->
* [41633626](https://news.social-protocols.org/stats?id=41633626) #27 5 points 3 comments -> [The Environmental Toll of a Single ChatGPT Query Is Absolutely Wild](https://futurism.com/the-byte/environment-openai-chatgpt)<!-- HN:41633626:end --><!-- HN:41633904:start -->
* [41633904](https://news.social-protocols.org/stats?id=41633904) #20 22 points 3 comments -> [Matrix.org Breaks Federation: Users Can't Decrypt Messages from Other Servers](https://github.com/matrix-org/matrix.org/issues/2483)<!-- HN:41633904:end --><!-- HN:41633268:start -->
* [41633268](https://news.social-protocols.org/stats?id=41633268) #30 91 points 37 comments -> [An AI Event Hired John Mulaney to Do a Comedy Set and He Brutally Roasted Them O](https://futurism.com/the-byte/salesforce-ai-john-mulaney-mocked)<!-- HN:41633268:end --><!-- HN:41634899:start -->
* [41634899](https://news.social-protocols.org/stats?id=41634899) #16 8 points 0 comments -> ['Places to heal, not to harm': brutal prison design kills off hope](https://www.theguardian.com/society/2024/sep/24/places-to-heal-not-to-harm-why-brutal-prison-design-kills-off-hope)<!-- HN:41634899:end --><!-- HN:41625456:start -->
* [41625456](https://news.social-protocols.org/stats?id=41625456) #28 43 points 1 comments -> [NeRF-Supervised Feature Point Detection and Description](https://arxiv.org/abs/2403.08156)<!-- HN:41625456:end --><!-- HN:41630081:start -->
* [41630081](https://news.social-protocols.org/stats?id=41630081) #21 37 points 16 comments -> [Where has all the productivity gone? (2021)](https://www.johndcook.com/blog/2021/07/31/where-has-productivity-gone/)<!-- HN:41630081:end --><!-- HN:41598330:start -->
* [41598330](https://news.social-protocols.org/stats?id=41598330) #22 50 points 15 comments -> [Cache Me Not, Cache Me, Cache Me Not](https://hazelweakly.me/blog/cache-me-not-cache-me-cache-me-not/)<!-- HN:41598330:end --><!-- HN:41634119:start -->
* [41634119](https://news.social-protocols.org/stats?id=41634119) #29 41 points 23 comments -> [Excel spreadsheet caused network equipment's physical failure](https://twitter.com/lauriewired/status/1838256923428438345)<!-- HN:41634119:end --><!-- HN:41636731:start -->
* [41636731](https://news.social-protocols.org/stats?id=41636731) #22 6 points 0 comments -> [Argentina Scrapped Its Rent Controls, here's what happened next](https://www.wsj.com/world/americas/argentina-milei-rent-control-free-market-5345c3d5)<!-- HN:41636731:end --><!-- HN:41635088:start -->
* [41635088](https://news.social-protocols.org/stats?id=41635088) #27 29 points 4 comments -> [Show HN: An expression parser supporting multiple types](https://github.com/torrentg/expr)<!-- HN:41635088:end --><!-- HN:41638137:start -->
* [41638137](https://news.social-protocols.org/stats?id=41638137) #10 24 points 15 comments -> [Natural Gas Company Said It Was Going Green but Still Sells as Much Fossil Fuel](https://www.propublica.org/article/nw-natural-gas-oregon-fossil-fuel)<!-- HN:41638137:end --><!-- HN:41639920:start -->
* [41639920](https://news.social-protocols.org/stats?id=41639920) #29 6 points 1 comments -> ["Calories in / calories out" is bullshit](https://twitter.com/anabology/status/1838203663375888640)<!-- HN:41639920:end --><!-- HN:41633630:start -->
* [41633630](https://news.social-protocols.org/stats?id=41633630) #23 39 points 2 comments -> [X will soon make your public posts visible to accounts you've blocked](https://techcrunch.com/2024/09/23/x-will-soon-make-your-public-posts-visible-to-accounts-youve-blocked/)<!-- HN:41633630:end --><!-- HN:41640458:start -->
* [41640458](https://news.social-protocols.org/stats?id=41640458) #9 30 points 1 comments -> [Star FTX Witness Caroline Ellison Sentenced to Two Years in Prison](https://www.wsj.com/finance/currencies/ftx-trial-caroline-ellison-sentencing-cc104a84)<!-- HN:41640458:end --><!-- HN:41640313:start -->
* [41640313](https://news.social-protocols.org/stats?id=41640313) #18 24 points 1 comments -> [Caroline Ellison sentenced to 24 months in prison for FTX fraud](https://www.bloomberg.com/news/live-blog/2024-09-24/caroline-ellison-sentencing)<!-- HN:41640313:end --><!-- HN:41641560:start -->
* [41641560](https://news.social-protocols.org/stats?id=41641560) #16 18 points 8 comments -> [The White Collar Apocalypse Is Nigh](https://scott-fryxell.github.io/blog/the-white-collar-apocalypse-is-nigh/)<!-- HN:41641560:end -->
#### **Wednesday, September 25, 2024**<!-- HN:41641495:start -->
* [41641495](https://news.social-protocols.org/stats?id=41641495) #22 11 points 2 comments -> [Ethernet in 17 lines of Spade [video]](https://www.youtube.com/watch?v=0a8P0NLYPWA)<!-- HN:41641495:end --><!-- HN:41640941:start -->
* [41640941](https://news.social-protocols.org/stats?id=41640941) #29 62 points 23 comments -> [$1B Solar and Battery Storage Project Breaks Ground in Utah](https://electrek.co/2024/09/23/a-1-billion-solar-battery-storage-project-just-broke-ground-in-utah/)<!-- HN:41640941:end --><!-- HN:41642203:start -->
* [41642203](https://news.social-protocols.org/stats?id=41642203) #17 32 points 35 comments -> [Drinking 3 cups of coffee linked to preventing multiple diseases](https://studyfinds.org/3-cups-of-coffee-diseases/)<!-- HN:41642203:end --><!-- HN:41644056:start -->
* [41644056](https://news.social-protocols.org/stats?id=41644056) #12 5 points 1 comments -> [Free AI Celebrity Voice Generator](https://arting.ai/ai-celebrity-voice-generator)<!-- HN:41644056:end --><!-- HN:41643388:start -->
* [41643388](https://news.social-protocols.org/stats?id=41643388) #28 46 points 17 comments -> [A new semantic chunking approach for RAG](https://gpt3experiments.substack.com/p/a-new-chunking-approach-to-rag)<!-- HN:41643388:end --><!-- HN:41630094:start -->
* [41630094](https://news.social-protocols.org/stats?id=41630094) #17 213 points 385 comments -> [Twitter/X will let people you've blocked see your posts](https://www.theverge.com/2024/9/23/24252438/x-blocked-users-view-public-posts)<!-- HN:41630094:end --><!-- HN:41643610:start -->
* [41643610](https://news.social-protocols.org/stats?id=41643610) #13 14 points 1 comments -> [Jupyter Kernel for Deno](https://docs.deno.com/runtime/reference/cli/jupyter/)<!-- HN:41643610:end --><!-- HN:41645820:start -->
* [41645820](https://news.social-protocols.org/stats?id=41645820) #5 13 points 6 comments -> [Why We're Having to End Our Direct Peering Relationship with Deutsche Telekom](https://about.fb.com/news/2024/09/why-were-having-to-end-our-direct-peering-relationship-with-deutsche-telekom/)<!-- HN:41645820:end --><!-- HN:41646376:start -->
* [41646376](https://news.social-protocols.org/stats?id=41646376) #27 5 points 0 comments -> [Family moved from US to Switzerland. The difference in quality of life is huge](https://www.businessinsider.com/moving-us-to-switzerland-better-quality-of-life-staying-abroad-2024-9)<!-- HN:41646376:end --><!-- HN:41646419:start -->
* [41646419](https://news.social-protocols.org/stats?id=41646419) #13 13 points 2 comments -> [Gmail's blue checkmarks are coming to iOS and Android](https://www.theverge.com/2024/9/25/24253904/gmails-blue-checkmarks-are-coming-to-ios-and-android)<!-- HN:41646419:end --><!-- HN:41645265:start -->
* [41645265](https://news.social-protocols.org/stats?id=41645265) #17 50 points 29 comments -> [How I Built My Blog](https://www.joshwcomeau.com/blog/how-i-built-my-blog-v2/)<!-- HN:41645265:end --><!-- HN:41606932:start -->
* [41606932](https://news.social-protocols.org/stats?id=41606932) #21 34 points 20 comments -> [Filtered for home robots, fast and slow](https://interconnected.org/home/2024/09/20/filtered)<!-- HN:41606932:end --><!-- HN:41645413:start -->
* [41645413](https://news.social-protocols.org/stats?id=41645413) #30 20 points 13 comments -> [Why Payments Engineers Should Avoid State Machines](https://news.alvaroduran.com/p/why-payments-engineers-should-avoid)<!-- HN:41645413:end --><!-- HN:41647129:start -->
* [41647129](https://news.social-protocols.org/stats?id=41647129) #15 7 points 0 comments -> [Scientists invent filter that can recycle PFAS into renewable batteries](https://www.abc.net.au/news/2024-09-05/scientists-invent-pfas-filter-for-battery-technology/104308214)<!-- HN:41647129:end --><!-- HN:41647286:start -->
* [41647286](https://news.social-protocols.org/stats?id=41647286) #17 4 points 0 comments -> [Google files first ever complaint with European Commission against Microsoft](https://www.theregister.com/2024/09/25/google_ms_ec_complaint/)<!-- HN:41647286:end --><!-- HN:41646135:start -->
* [41646135](https://news.social-protocols.org/stats?id=41646135) #27 21 points 4 comments -> [Google Paid $2.7B to Bring Back an AI Genius Who Quit in Frustration](https://www.wsj.com/tech/ai/noam-shazeer-google-ai-deal-d3605697)<!-- HN:41646135:end --><!-- HN:41647683:start -->
* [41647683](https://news.social-protocols.org/stats?id=41647683) #23 5 points 2 comments -> [The Social Web Foundation Is Shaping the Next Era of the Web](https://werd.io/2024/unlocking-the-fediverse-the-social-web-foundation-is-shaping-the)<!-- HN:41647683:end --><!-- HN:41605524:start -->
* [41605524](https://news.social-protocols.org/stats?id=41605524) #17 10 points 0 comments -> [Scaling up linear programming with PDLP](https://research.google/blog/scaling-up-linear-programming-with-pdlp/)<!-- HN:41605524:end --><!-- HN:41646167:start -->
* [41646167](https://news.social-protocols.org/stats?id=41646167) #28 20 points 7 comments -> [US Investigating SAP, Carahsoft for Potential Price-Fixing](https://www.msn.com/en-us/money/other/us-investigating-sap-carahsoft-for-potential-price-fixing/ar-AA1r9LW8)<!-- HN:41646167:end --><!-- HN:41648397:start -->
* [41648397](https://news.social-protocols.org/stats?id=41648397) #27 6 points 1 comments -> [A thriving underground economy is clogging the internet with AI garbage](https://nymag.com/intelligencer/article/ai-generated-content-internet-online-slop-spam.html)<!-- HN:41648397:end --><!-- HN:41603819:start -->
* [41603819](https://news.social-protocols.org/stats?id=41603819) #18 23 points 1 comments -> [Mathematicians define new class of shape seen throughout nature](https://www.nature.com/articles/d41586-024-03099-6)<!-- HN:41603819:end --><!-- HN:41648855:start -->
* [41648855](https://news.social-protocols.org/stats?id=41648855) #23 5 points 0 comments -> [Substack's Nazi problem isn't going away](https://theracket.news/p/substacks-nazi-problem-isnt-going-away)<!-- HN:41648855:end --><!-- HN:41599026:start -->
* [41599026](https://news.social-protocols.org/stats?id=41599026) #10 9 points 2 comments -> [Lessons from over 30 Years of Buy versus Rent Decision](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=90db2525a8c74fe80b5771bb8422ea252bb642d8)<!-- HN:41599026:end --><!-- HN:41645736:start -->
* [41645736](https://news.social-protocols.org/stats?id=41645736) #23 56 points 63 comments -> [OpenAI rolls out Advanced Voice Mode with more voices and a new look](https://techcrunch.com/2024/09/24/openai-rolls-out-advanced-voice-mode-with-more-voices-and-a-new-look/)<!-- HN:41645736:end --><!-- HN:41650231:start -->
* [41650231](https://news.social-protocols.org/stats?id=41650231) #29 4 points 1 comments -> [Meta Ray-Ban's updated with real-time AI video, reminders, QR scanning](https://techcrunch.com/2024/09/25/meta-updates-ray-ban-smart-glasses-with-real-time-ai-video-reminders-and-qr-code-scanning/)<!-- HN:41650231:end --><!-- HN:41648112:start -->
* [41648112](https://news.social-protocols.org/stats?id=41648112) #27 8 points 1 comments -> [VitePress: Vite and Vue powered static site generator](https://github.com/vuejs/vitepress)<!-- HN:41648112:end --><!-- HN:41651001:start -->
* [41651001](https://news.social-protocols.org/stats?id=41651001) #11 5 points 2 comments -> [Cozystack has officially been included in the CNCF Landscape](https://blog.aenix.io/cozystack-has-officially-been-included-in-the-cncf-landscape-07cc60c9e0eb)<!-- HN:41651001:end --><!-- HN:41651596:start -->
* [41651596](https://news.social-protocols.org/stats?id=41651596) #18 19 points 40 comments -> [The Daily Scrum: Does It Have to Be Daily?](https://rethinkingsoftware.substack.com/p/the-daily-scrum)<!-- HN:41651596:end -->
#### **Thursday, September 26, 2024**
<!-- HN:41653748:start -->
* [41653748](https://news.social-protocols.org/stats?id=41653748) #15 12 points 0 comments -> [NYC Mayor Eric Adams Is Indicted](https://www.cnn.com/2024/09/25/us/new-york-city-mayor-eric-adams-indicted/index.html)<!-- HN:41653748:end --><!-- HN:41653641:start -->
* [41653641](https://news.social-protocols.org/stats?id=41653641) #15 4 points 3 comments -> [Ugly Wallpapers – Early 2000s style](https://wallpapers.branding5.com/)<!-- HN:41653641:end --><!-- HN:41643651:start -->
* [41643651](https://news.social-protocols.org/stats?id=41643651) #12 286 points 142 comments -> [SQL Tips and Tricks](https://github.com/ben-n93/SQL-tips-and-tricks)<!-- HN:41643651:end --><!-- HN:41654570:start -->
* [41654570](https://news.social-protocols.org/stats?id=41654570) #5 13 points 1 comments -> [FreeBSD](https://www.freebsd.org/status/report-2024-04-2024-06/)<!-- HN:41654570:end --><!-- HN:41654550:start -->
* [41654550](https://news.social-protocols.org/stats?id=41654550) #19 23 points 40 comments -> [Teacher caught students using ChatGPT on their first assignment. Debate ensues](https://www.businessinsider.com/students-caught-using-chatgpt-ai-assignment-teachers-debate-2024-9)<!-- HN:41654550:end --><!-- HN:41655583:start -->
* [41655583](https://news.social-protocols.org/stats?id=41655583) #18 -> [A new Llama-based model for efficient large-scale voice generation](https://github.com/OpenT2S/LlamaVoice)<!-- HN:41655583:end --><!-- HN:41656260:start -->
* [41656260](https://news.social-protocols.org/stats?id=41656260) #16 6 points 3 comments -> [I Built "The Monospace Web"](https://wickstrom.tech/2024-09-26-how-i-built-the-monospace-web.html)<!-- HN:41656260:end --><!-- HN:41659213:start -->
* [41659213](https://news.social-protocols.org/stats?id=41659213) #6 5 points 2 comments -> [Raylib Project Creator](https://github.com/raysan5/raylib_project_creator)<!-- HN:41659213:end --><!-- HN:41602519:start -->
* [41602519](https://news.social-protocols.org/stats?id=41602519) #22 144 points 72 comments -> [Hoodmaps: Publicly Annotated City Maps](https://hoodmaps.com)<!-- HN:41602519:end --><!-- HN:41617207:start -->
* [41617207](https://news.social-protocols.org/stats?id=41617207) #17 13 points 1 comments -> [Blast wakes ghosts of nuclear past (1995)](https://www.newscientist.com/article/mg14619810-300-blast-wakes-ghosts-of-nuclear-past/)<!-- HN:41617207:end --><!-- HN:41614866:start -->
* [41614866](https://news.social-protocols.org/stats?id=41614866) #18 11 points 3 comments -> [Algorithms for the 21st Century (2006)](http://yaccman.com/papers/a21/Alg21.html)<!-- HN:41614866:end --><!-- HN:41608496:start -->
* [41608496](https://news.social-protocols.org/stats?id=41608496) #21 20 points 2 comments -> [The Mathematics of Dobble (2018)](https://www.petercollingridge.co.uk/blog/mathematics-toys-and-games/dobble/)<!-- HN:41608496:end --><!-- HN:41618070:start -->
* [41618070](https://news.social-protocols.org/stats?id=41618070) #22 4 points 3 comments -> [The Future of Programming Systems – four thoughts](https://blog.waleson.com/2024/09/the-future-of-programming-systems-four.html)<!-- HN:41618070:end --><!-- HN:41616023:start -->
* [41616023](https://news.social-protocols.org/stats?id=41616023) #28 73 points 26 comments -> [Shizuku: App that lets you use system APIs with higher privileges without root](https://shizuku.rikka.app/)<!-- HN:41616023:end --><!-- HN:41661511:start -->
* [41661511](https://news.social-protocols.org/stats?id=41661511) #23 60 points 25 comments -> [Ukraine Discovers Starlink on Downed Russian Shahed Drone: Report](https://www.newsweek.com/ukraine-starlink-russia-shahed-135-drone-elon-musk-spacex-1959563)<!-- HN:41661511:end --><!-- HN:41662291:start -->
* [41662291](https://news.social-protocols.org/stats?id=41662291) #22 4 points 0 comments -> [Attackers are increasingly targeting industrial systems with brute force](https://www.techradar.com/pro/security/hackers-are-increasingly-targeting-industrial-systems-with-brute-force-cisa-warns)<!-- HN:41662291:end --><!-- HN:41662355:start -->
* [41662355](https://news.social-protocols.org/stats?id=41662355) #6 43 points 5 comments -> [RCE Vulnerability Discovered in Cups](https://gist.github.com/stong/c8847ef27910ae344a7b5408d9840ee1)<!-- HN:41662355:end --><!-- HN:41663051:start -->
* [41663051](https://news.social-protocols.org/stats?id=41663051) #13 50 points 7 comments -> [Twitter banned me after publishing the JD Vance Dossier](https://www.kenklippenstein.com/p/twitter-banned-me)<!-- HN:41663051:end --><!-- HN:41662501:start -->
* [41662501](https://news.social-protocols.org/stats?id=41662501) #18 54 points 16 comments -> [Instagram deleting archived stories, turning old videos into photos](https://twitter.com/IndoPopBase/status/1838858807801155618)<!-- HN:41662501:end --><!-- HN:41664723:start -->
* [41664723](https://news.social-protocols.org/stats?id=41664723) #29 5 points 2 comments -> [I can't stand Google scanning my emails anymore](https://www.forbes.com/sites/daveywinder/2020/02/28/google-confirms-new-ai-tool-scans-300-billion-gmail-attachments-every-week/)<!-- HN:41664723:end -->
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
* [41695630](https://news.social-protocols.org/stats?id=41695630) #2 38 points 31 comments -> [A guide to working remote and not paying rent](https://ghuntley.com/freecamping/)<!-- HN:41695630:end -->
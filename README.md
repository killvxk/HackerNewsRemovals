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
* [41400523](https://news.social-protocols.org/stats?id=41400523) #29 5 points 1 comments -> [AI cameras spot toddlers not wearing seat belts](https://www.bbc.com/news/articles/c5y3pdp099zo)<!-- HN:41400523:end --><!-- HN:41395921:start -->
* [41395921](https://news.social-protocols.org/stats?id=41395921) #27 262 points 71 comments -> [Anthropic's Prompt Engineering Interactive Tutorial](https://github.com/anthropics/courses/tree/master/prompt_engineering_interactive_tutorial)<!-- HN:41395921:end --><!-- HN:41400152:start -->
* [41400152](https://news.social-protocols.org/stats?id=41400152) #17 4 points 0 comments -> [Understanding the Postgres Hackers Mailing List](https://www.crunchydata.com/blog/understanding-the-postgres-hackers-mailing-list)<!-- HN:41400152:end --><!-- HN:41396710:start -->
* [41396710](https://news.social-protocols.org/stats?id=41396710) #16 10 points 1 comments -> [Sail and Muddy: A Retrospective](https://feelmuddy.notion.site/Sail-Muddy-A-Retrospective-388a528951de4da58e66940c5fb85b8a)<!-- HN:41396710:end --><!-- HN:41403466:start -->
* [41403466](https://news.social-protocols.org/stats?id=41403466) #19 19 points 16 comments -> [Show HN: I made a site that lets everyone edit the same gradient in real-time](https://internetgradient.com)<!-- HN:41403466:end --><!-- HN:41404897:start -->
* [41404897](https://news.social-protocols.org/stats?id=41404897) #5 17 points 6 comments -> [John Rawls and the Death of Western Marxism](https://josephheath.substack.com/p/john-rawls-and-the-death-of-western)<!-- HN:41404897:end -->
#### **Saturday, August 31, 2024**
<!-- HN:41358432:start -->
* [41358432](https://news.social-protocols.org/stats?id=41358432) #2 27 points 7 comments -> [Dinosaur Footprints on Either Side of the Atlantic Are Matching Sets](https://gizmodo.com/dinosaur-footprints-on-either-side-of-the-atlantic-are-matching-sets-2000490979)<!-- HN:41358432:end --><!-- HN:41357409:start -->
* [41357409](https://news.social-protocols.org/stats?id=41357409) #8 189 points 43 comments -> [Emacs-like editor written in Common Lisp](https://lem-project.github.io/#)<!-- HN:41357409:end --><!-- HN:41353830:start -->
* [41353830](https://news.social-protocols.org/stats?id=41353830) #10 17 points 0 comments -> [Libntruprime is a microlibrary for the Streamlined NTRU Prime cryptosyst](https://libntruprime.cr.yp.to/)<!-- HN:41353830:end --><!-- HN:41358333:start -->
* [41358333](https://news.social-protocols.org/stats?id=41358333) #19 3 points 1 comments -> [Synthetic Open Schema: code-first approach to Synthetic Monitoring](https://github.com/checksdev/synthetic-open-schema)<!-- HN:41358333:end --><!-- HN:41356775:start -->
* [41356775](https://news.social-protocols.org/stats?id=41356775) #24 128 points 97 comments -> [Pie doesn't need to be original unless you claim it so](https://buttondown.com/geoffreylitt/archive/your-pie-doesnt-need-to-be-original-unless-you/)<!-- HN:41356775:end --><!-- HN:41357123:start -->
* [41357123](https://news.social-protocols.org/stats?id=41357123) #25 115 points 51 comments -> [Leader Election with S3 Conditional Writes](https://www.morling.dev/blog/leader-election-with-s3-conditional-writes/)<!-- HN:41357123:end --><!-- HN:41352008:start -->
* [41352008](https://news.social-protocols.org/stats?id=41352008) #28 23 points 2 comments -> [Real-world uplift modelling with significance-based uplift trees [pdf]](https://www.stochasticsolutions.com/pdf/sig-based-up-trees.pdf)<!-- HN:41352008:end --><!-- HN:41377097:start -->
* [41377097](https://news.social-protocols.org/stats?id=41377097) #18 46 points 28 comments -> [How to Use React Compiler](https://www.freecodecamp.org/news/react-compiler-complete-guide-react-19/)<!-- HN:41377097:end --><!-- HN:41406502:start -->
* [41406502](https://news.social-protocols.org/stats?id=41406502) #24 19 points 0 comments -> [You've only added two lines – why did that take two days](https://www.mrlacey.com/2020/07/youve-only-added-two-lines-why-did-that.html)<!-- HN:41406502:end --><!-- HN:41408173:start -->
* [41408173](https://news.social-protocols.org/stats?id=41408173) #12 14 points 40 comments -> [Why A.I. Isn't Going to Make Art](https://www.newyorker.com/culture/the-weekend-essay/why-ai-isnt-going-to-make-art)<!-- HN:41408173:end --><!-- HN:41408792:start -->
* [41408792](https://news.social-protocols.org/stats?id=41408792) #24 6 points 0 comments -> [When the Mismanagerial Class Destroys Great Companies](https://www.palladiummag.com/2024/08/30/when-the-mismanagerial-class-destroys-great-companies/)<!-- HN:41408792:end --><!-- HN:41408464:start -->
* [41408464](https://news.social-protocols.org/stats?id=41408464) #29 5 points 0 comments -> [The California Supreme Court Should Help Protect Your Stored Communications](https://www.eff.org/deeplinks/2024/08/california-supreme-court-should-help-protect-your-stored-communications)<!-- HN:41408464:end --><!-- HN:41377328:start -->
* [41377328](https://news.social-protocols.org/stats?id=41377328) #20 29 points 1 comments -> [Bundling Information Goods: Pricing, Profits, and Efficiency (1999)](https://www.jstor.org/stable/2634781)<!-- HN:41377328:end --><!-- HN:41410344:start -->
* [41410344](https://news.social-protocols.org/stats?id=41410344) #3 6 points 0 comments -> [What the f* is e/acc (2022)](https://effectiveaccelerationism.substack.com/p/what-the-f-is-eacc)<!-- HN:41410344:end --><!-- HN:41409144:start -->
* [41409144](https://news.social-protocols.org/stats?id=41409144) #16 5 points 1 comments -> [We can have democracy or we can have Facebook, but we can't have both (2020)](https://the.ink/p/we-can-have-democracy-or-we-can-have)<!-- HN:41409144:end --><!-- HN:41410450:start -->
* [41410450](https://news.social-protocols.org/stats?id=41410450) #17 206 points 198 comments -> [Nearly half of Nvidia's revenue comes from four mystery whales each buying $3B+](https://fortune.com/2024/08/29/nvidia-jensen-huang-ai-customers/)<!-- HN:41410450:end --><!-- HN:41411635:start -->
* [41411635](https://news.social-protocols.org/stats?id=41411635) #20 22 points 3 comments -> [Federal Appeals Court Once Again Rejects Blanket Gun Ban for Cannabis Consumers](https://norml.org/blog/2024/08/29/federal-appeals-court-once-again-rejects-blanket-gun-ban-for-cannabis-consumers/)<!-- HN:41411635:end --><!-- HN:41411147:start -->
* [41411147](https://news.social-protocols.org/stats?id=41411147) #26 32 points 31 comments -> [Las Vegas police could boycott working NFL games over new facial ID policy](https://www.reviewjournal.com/local/local-las-vegas/nfl-facial-recognition-policy-upsets-las-vegas-police-union-3128202/)<!-- HN:41411147:end --><!-- HN:41377073:start -->
* [41377073](https://news.social-protocols.org/stats?id=41377073) #26 -> [Karpathy on Software 2.0 (2017)](https://karpathy.medium.com/software-2-0-a64152b37c35)<!-- HN:41377073:end --><!-- HN:41411504:start -->
* [41411504](https://news.social-protocols.org/stats?id=41411504) #24 4 points 0 comments -> [Hillbilly Lament](https://andrewpwheeler.com/2024/08/26/hillbilly-lament/)<!-- HN:41411504:end --><!-- HN:41411339:start -->
* [41411339](https://news.social-protocols.org/stats?id=41411339) #9 34 points 40 comments -> [Signals for Tailwind CSS (styling based on ancestor state via style queries)](https://github.com/brandonmcconnell/tailwindcss-signals)<!-- HN:41411339:end -->
#### **Sunday, September 1, 2024**
<!-- HN:41412129:start -->
* [41412129](https://news.social-protocols.org/stats?id=41412129) #17 6 points 2 comments -> [California Is Now Hitting Farmers Up to $10K Fines per Day](https://franknez.com/california-is-now-hitting-farmers-up-to-10k-fines-per-day/)<!-- HN:41412129:end --><!-- HN:41412356:start -->
* [41412356](https://news.social-protocols.org/stats?id=41412356) #17 7 points 3 comments -> [Why So Many People Are Going "No Contact" with Their Parents](https://www.newyorker.com/culture/annals-of-inquiry/why-so-many-people-are-going-no-contact-with-their-parents)<!-- HN:41412356:end --><!-- HN:41366614:start -->
* [41366614](https://news.social-protocols.org/stats?id=41366614) #4 52 points 17 comments -> [My first experience with Gleam Language](https://pliutau.com/my-first-experience-with-gleam-lang/)<!-- HN:41366614:end --><!-- HN:41368657:start -->
* [41368657](https://news.social-protocols.org/stats?id=41368657) #8 91 points 8 comments -> [Compilation of JavaScript to WASM, Part 2: Ahead-of-Time vs. JIT](https://cfallin.org/blog/2024/08/27/aot-js/)<!-- HN:41368657:end --><!-- HN:41369065:start -->
* [41369065](https://news.social-protocols.org/stats?id=41369065) #23 139 points 37 comments -> [Building Bubbletea Programs](https://leg100.github.io/en/posts/building-bubbletea-programs/)<!-- HN:41369065:end --><!-- HN:41413687:start -->
* [41413687](https://news.social-protocols.org/stats?id=41413687) #30 39 points 23 comments -> [Oprah will screw up the AI story](https://www.anildash.com//2024/08/31/oprah-wrong-ai/)<!-- HN:41413687:end --><!-- HN:41415063:start -->
* [41415063](https://news.social-protocols.org/stats?id=41415063) #24 4 points 3 comments -> [Artificial intelligence comes to male sex toys](https://english.elpais.com/lifestyle/2024-09-01/this-is-not-your-normal-masturbation-artificial-intelligence-comes-to-male-sex-toys.html)<!-- HN:41415063:end --><!-- HN:41415441:start -->
* [41415441](https://news.social-protocols.org/stats?id=41415441) #20 3 points 0 comments -> [Shame and Narcissistic Rage in Autogynephilic Transsexualism](https://annelawrence.com/wp-content/uploads/2023/11/Lawrence-2008-shame-and-narcissistic-rage.pdf)<!-- HN:41415441:end --><!-- HN:41414455:start -->
* [41414455](https://news.social-protocols.org/stats?id=41414455) #23 28 points 40 comments -> [AI is growing faster than companies can secure it, warn industry leaders](https://venturebeat.com/ai/ai-is-growing-faster-than-companies-can-secure-it-warn-industry-leaders/)<!-- HN:41414455:end --><!-- HN:41416855:start -->
* [41416855](https://news.social-protocols.org/stats?id=41416855) #29 3 points 1 comments -> [Huck Finn – One of the Greatest Anti-Racist Books Ever Written](https://medium.com/luminasticity/huck-finn-one-of-the-greatest-anti-racist-books-ever-written-db3f922dea44)<!-- HN:41416855:end --><!-- HN:41379751:start -->
* [41379751](https://news.social-protocols.org/stats?id=41379751) #18 52 points 12 comments -> [The Atari 7800](https://www.goto10retro.com/p/inside-the-atari-7800)<!-- HN:41379751:end --><!-- HN:41415468:start -->
* [41415468](https://news.social-protocols.org/stats?id=41415468) #17 74 points 34 comments -> [Take a closer look at Starbucks CEO's contract, which covers his commute by jet](https://www.abc.net.au/news/2024-09-01/starbucks-ceo-brian-niccol-contract-explained/104270064)<!-- HN:41415468:end --><!-- HN:41415363:start -->
* [41415363](https://news.social-protocols.org/stats?id=41415363) #20 50 points 13 comments -> [The papers that most heavily cite retracted studies](https://www.nature.com/articles/d41586-024-02719-5)<!-- HN:41415363:end --><!-- HN:41417368:start -->
* [41417368](https://news.social-protocols.org/stats?id=41417368) #5 10 points 0 comments -> [What 100 Years of Research Says about Ability Grouping and Acceleration [pdf]](http://www.k12accountability.org/resources/Gifted-Education/GT_Review_of_Ed_Research_Meta_Analysis.pdf)<!-- HN:41417368:end --><!-- HN:41417657:start -->
* [41417657](https://news.social-protocols.org/stats?id=41417657) #11 12 points 4 comments -> [Amazon and Bezos fund's influence over carbon credit market raises alarm](https://www.ft.com/content/388b190d-49b0-4997-af18-1049e911f0b7)<!-- HN:41417657:end -->
#### **Monday, September 2, 2024**<!-- HN:41396279:start -->
* [41396279](https://news.social-protocols.org/stats?id=41396279) #14 19 points 6 comments -> [The Imperial Origins of Big Data](https://yalebooks.yale.edu/2024/08/28/the-imperial-origins-of-big-data/)<!-- HN:41396279:end --><!-- HN:41423518:start -->
* [41423518](https://news.social-protocols.org/stats?id=41423518) #16 26 points 40 comments -> [Starlink Defies Order to Block X in Brazil](https://www.nytimes.com/2024/09/01/world/americas/elon-musk-brazil-starlink-x.html)<!-- HN:41423518:end --><!-- HN:41424016:start -->
* [41424016](https://news.social-protocols.org/stats?id=41424016) #25 58 points 31 comments -> [In Leak, Facebook Partner Brags About Listening to Your Phone's Microphone to S](https://futurism.com/the-byte/facebook-partner-phones-listening-microphone)<!-- HN:41424016:end --><!-- HN:41424359:start -->
* [41424359](https://news.social-protocols.org/stats?id=41424359) #20 6 points 0 comments -> [Court Denies Cheat Seller AimJunkies a New Trial, Affirms Bungie's $4.3M Win](https://torrentfreak.com/court-denies-cheat-seller-aimjunkies-a-new-trial-affirms-bungies-4-3-million-win-240902/)<!-- HN:41424359:end --><!-- HN:41424608:start -->
* [41424608](https://news.social-protocols.org/stats?id=41424608) #12 16 points 1 comments -> [Rust Maintainer for Linux Kernel Resigns](https://ostechnix.com/rust-maintainer-for-linux-kernel-resigns/)<!-- HN:41424608:end --><!-- HN:41387613:start -->
* [41387613](https://news.social-protocols.org/stats?id=41387613) #19 37 points 14 comments -> [Why Medieval Women Sometimes Fought in Bloody Trials by Combat](https://www.atlasobscura.com/articles/trial-by-combat-man-woman)<!-- HN:41387613:end --><!-- HN:41425028:start -->
* [41425028](https://news.social-protocols.org/stats?id=41425028) #29 42 points 19 comments -> [Brazil to Fine Anyone Using a VPN to Access X $8,874 per Day; Elon Musk Responds](https://www.complex.com/pop-culture/a/treyalston/brazil-x-elon-musk-fine)<!-- HN:41425028:end --><!-- HN:41425093:start -->
* [41425093](https://news.social-protocols.org/stats?id=41425093) #21 25 points 21 comments -> [How CrowdStrike Stopped Everything](https://cacm.acm.org/news/how-crowdstrike-stopped-everything/)<!-- HN:41425093:end --><!-- HN:41425857:start -->
* [41425857](https://news.social-protocols.org/stats?id=41425857) #24 5 points 0 comments -> [The Largest Wetland Is Burning, and Rare Animals Are Dying](https://www.nytimes.com/2024/08/27/world/americas/pantanal-wildfires-wildlife.html)<!-- HN:41425857:end --><!-- HN:41425808:start -->
* [41425808](https://news.social-protocols.org/stats?id=41425808) #24 4 points 2 comments -> [Revolution: Google Password Manager Syncs Passkeys to Apple and Windows Devices](https://www.corbado.com/blog/google-passkeys-sync-windows-macos)<!-- HN:41425808:end --><!-- HN:41425307:start -->
* [41425307](https://news.social-protocols.org/stats?id=41425307) #21 16 points 2 comments -> [He Emptied an Entire Crypto Exchange onto a Thumb Drive. Then He Disappeared](https://www.wired.com/story/faruk-ozer-turkey-crypto-fraud/)<!-- HN:41425307:end --><!-- HN:41426904:start -->
* [41426904](https://news.social-protocols.org/stats?id=41426904) #17 10 points 0 comments -> [Congress Should Make Universities Pay for Handing Out Useless Degrees](https://thefederalist.com/2024/09/02/congress-should-make-universities-pay-for-handing-out-useless-degrees/)<!-- HN:41426904:end --><!-- HN:41427392:start -->
* [41427392](https://news.social-protocols.org/stats?id=41427392) #30 7 points 2 comments -> [When Heat Turns Deadly](https://www.abc.net.au/news/2024-09-02/deadly-heat-limits-tested-in-world-first-human-experiment/104242788)<!-- HN:41427392:end --><!-- HN:41427648:start -->
* [41427648](https://news.social-protocols.org/stats?id=41427648) #22 10 points 11 comments -> [Ketogenic Diet Shows Promise Treating Serious Mental Illness in Stanford Study](https://www.metabolicmind.org/news/ketogenic-diet-shows-promise-in-treating-serious-mental-illness-in-stanford-medicine-study)<!-- HN:41427648:end -->
#### **Tuesday, September 3, 2024**
<!-- HN:41429778:start -->
* [41429778](https://news.social-protocols.org/stats?id=41429778) #12 7 points 0 comments -> [Stelo Glucose Biosensor – No Prescription, Buy Now](https://www.stelo.com/en-us/buy-stelo-monthly-subscription)<!-- HN:41429778:end --><!-- HN:41430325:start -->
* [41430325](https://news.social-protocols.org/stats?id=41430325) #8 49 points 20 comments -> [FB partner admits phone microphones listen to people talk to serve better ads](https://inshort.geartape.com/facebook-partner-admits-smartphone-microphones-listen-to-people-talk-to-serve-better-ads/)<!-- HN:41430325:end --><!-- HN:41431758:start -->
* [41431758](https://news.social-protocols.org/stats?id=41431758) #11 19 points 3 comments -> [Extremist settlers rapidly seizing West Bank land](https://www.bbc.com/news/articles/c207j6wy332o)<!-- HN:41431758:end --><!-- HN:41398008:start -->
* [41398008](https://news.social-protocols.org/stats?id=41398008) #22 5 points 3 comments -> [The Asteroid-in-Spring Hypothesis](https://nymag.com/intelligencer/article/tanis-site-controversy-paleontology-fossils-during-depalma.html)<!-- HN:41398008:end --><!-- HN:41431941:start -->
* [41431941](https://news.social-protocols.org/stats?id=41431941) #28 36 points 40 comments -> [Why Britain Drives on the Left](https://www.theguardian.com/notesandqueries/query/0,5753,-19385,00.html)<!-- HN:41431941:end --><!-- HN:41399807:start -->
* [41399807](https://news.social-protocols.org/stats?id=41399807) #7 21 points 10 comments -> [Seafaring for Women in Software Engineering – Part I – Performance and Promotion](https://beabytes.com/seafaring-part-i/)<!-- HN:41399807:end --><!-- HN:41433316:start -->
* [41433316](https://news.social-protocols.org/stats?id=41433316) #12 15 points 3 comments -> [AI worse than humans in every way at summarising information, trial finds](https://www.crikey.com.au/2024/09/03/ai-worse-summarising-information-humans-government-trial/)<!-- HN:41433316:end --><!-- HN:41433673:start -->
* [41433673](https://news.social-protocols.org/stats?id=41433673) #25 12 points 6 comments -> [Europeans fail to understand how much they were fucked by the 2008 crisis](https://twitter.com/RnaudBertrand/status/1830816765611590043)<!-- HN:41433673:end --><!-- HN:41430525:start -->
* [41430525](https://news.social-protocols.org/stats?id=41430525) #16 31 points 37 comments -> [The Yubikey Is the Digital Seatbelt We Need](https://www.zagaja.com/2024/09/yubikey-digital-seatbelt/)<!-- HN:41430525:end --><!-- HN:41432432:start -->
* [41432432](https://news.social-protocols.org/stats?id=41432432) #18 5 points 0 comments -> [Elasticsearch and Kibana become free software (again)](https://lwn.net/Articles/987850/)<!-- HN:41432432:end --><!-- HN:41433721:start -->
* [41433721](https://news.social-protocols.org/stats?id=41433721) #21 6 points 3 comments -> [Gimp Is No Longer a Viable Photoshop Alternative](https://medium.com/@kevdoy/gimp-is-no-longer-a-viable-photoshop-alternative-16ba9f5e9eb5)<!-- HN:41433721:end --><!-- HN:41430310:start -->
* [41430310](https://news.social-protocols.org/stats?id=41430310) #22 111 points 66 comments -> [Feds Kill Plan to Curb Medicare Advantage Overbilling After Industry Opposition](https://kffhealthnews.org/news/article/medicare-advantage-overbilling-diagnostic-codes-cms-killed-rule/)<!-- HN:41430310:end --><!-- HN:41433708:start -->
* [41433708](https://news.social-protocols.org/stats?id=41433708) #16 5 points 0 comments -> [Any idea what HW/MCU is inside Amazon Monitron?](https://www.amazon.com/dp/B0851JTCC1)<!-- HN:41433708:end --><!-- HN:41434098:start -->
* [41434098](https://news.social-protocols.org/stats?id=41434098) #19 3 points 0 comments -> [Geolocation of a helicopter from reflection in sensor ball](https://twitter.com/ejshahid/status/1830662843190198471)<!-- HN:41434098:end --><!-- HN:41434146:start -->
* [41434146](https://news.social-protocols.org/stats?id=41434146) #24 3 points 0 comments -> [Founders Create Managers](https://skamille.medium.com/founders-create-managers-aba3c88981ba)<!-- HN:41434146:end --><!-- HN:41432525:start -->
* [41432525](https://news.social-protocols.org/stats?id=41432525) #11 23 points 2 comments -> [Hugging Face tackles speech-to-speech](https://github.com/huggingface/speech-to-speech)<!-- HN:41432525:end --><!-- HN:41434636:start -->
* [41434636](https://news.social-protocols.org/stats?id=41434636) #26 3 points 1 comments -> [Cash alone proves inadequate to solve the problems of the poor](https://www.washingtonpost.com/opinions/2024/09/03/poverty-debt-relief-cash-research/)<!-- HN:41434636:end --><!-- HN:41435103:start -->
* [41435103](https://news.social-protocols.org/stats?id=41435103) #23 7 points 0 comments -> [Concern over housing costs hits record high across rich nations](https://www.ft.com/content/f206f6f1-1536-4b29-ad8d-2421fadfc64b)<!-- HN:41435103:end --><!-- HN:41435267:start -->
* [41435267](https://news.social-protocols.org/stats?id=41435267) #24 4 points 0 comments -> [Bugs, performance issues hinder Huawei's AI chips](https://arstechnica.com/ai/2024/09/bugs-performance-issues-hinder-huaweis-ai-chips/)<!-- HN:41435267:end --><!-- HN:41435521:start -->
* [41435521](https://news.social-protocols.org/stats?id=41435521) #28 15 points 6 comments -> [How to Take Home "Garbage Bags Full of $20s"](https://www.hollywoodreporter.com/tv/tv-news/stars-getting-rich-fan-conventions-933062/)<!-- HN:41435521:end --><!-- HN:41434918:start -->
* [41434918](https://news.social-protocols.org/stats?id=41434918) #27 12 points 0 comments -> [Congress asks more questions about TSA blacklists](https://papersplease.org/wp/2024/09/03/congress-asks-more-questions-about-tsa-blacklists/)<!-- HN:41434918:end --><!-- HN:41436214:start -->
* [41436214](https://news.social-protocols.org/stats?id=41436214) #7 3 points 0 comments -> [Is one or two engines better in a fighter?](https://hushkit.net/2024/09/03/is-one-or-two-engines-better-in-a-fighter/)<!-- HN:41436214:end --><!-- HN:41436524:start -->
* [41436524](https://news.social-protocols.org/stats?id=41436524) #26 3 points 0 comments -> [NAFTA Broke American Politics](https://www.nytimes.com/2024/09/03/magazine/nafta-tarriffs-economy-trump-kamala-harris.html)<!-- HN:41436524:end --><!-- HN:41436630:start -->
* [41436630](https://news.social-protocols.org/stats?id=41436630) #30 7 points 2 comments -> [Why did Windows 95 use blue screen error messages instead of hard error messages](https://devblogs.microsoft.com/oldnewthing/20240903-00/?p=110205)<!-- HN:41436630:end --><!-- HN:41437029:start -->
* [41437029](https://news.social-protocols.org/stats?id=41437029) #26 3 points 0 comments -> [Mayo researchers develop tool that measures health of a person's gut microbiome](https://newsnetwork.mayoclinic.org/discussion/mayo-researchers-develop-tool-that-measures-health-of-a-persons-gut-microbiome/)<!-- HN:41437029:end --><!-- HN:41437214:start -->
* [41437214](https://news.social-protocols.org/stats?id=41437214) #27 5 points 0 comments -> [Google–California Deal Falls Short Where a Data Tax Would Succeed](https://news.bloombergtax.com/tax-insights-and-commentary/google-california-deal-falls-short-where-a-data-tax-would-succeed)<!-- HN:41437214:end --><!-- HN:41398833:start -->
* [41398833](https://news.social-protocols.org/stats?id=41398833) #5 101 points 57 comments -> [Things my girlfriend and I have argued about](http://www.thingsmygirlfriendandihavearguedabout.com/)<!-- HN:41398833:end --><!-- HN:41437958:start -->
* [41437958](https://news.social-protocols.org/stats?id=41437958) #30 15 points 8 comments -> ['Most People I Know Who Went Vegan Have Gone Back to Eating Meat'](https://www.menshealth.com/uk/nutrition/a62006382/are-we-losing-our-appetites-for-veganism/)<!-- HN:41437958:end --><!-- HN:41416644:start -->
* [41416644](https://news.social-protocols.org/stats?id=41416644) #18 27 points 6 comments -> [Show HN: Ten AI demo apps to build your next AI project faster](https://nextjsaitemplates.com)<!-- HN:41416644:end --><!-- HN:41438672:start -->
* [41438672](https://news.social-protocols.org/stats?id=41438672) #27 52 points 9 comments -> [Anthropic Quickstarts](https://github.com/anthropics/anthropic-quickstarts)<!-- HN:41438672:end --><!-- HN:41440340:start -->
* [41440340](https://news.social-protocols.org/stats?id=41440340) #29 8 points 0 comments -> [Starlink Backtracks and Will Comply with Judge's Order to Block X in Brazil](https://www.usnews.com/news/business/articles/2024-09-03/musks-starlink-backtracks-and-will-comply-with-judges-order-to-block-x-in-brazil)<!-- HN:41440340:end -->
#### **Wednesday, September 4, 2024**
<!-- HN:41439993:start -->
* [41439993](https://news.social-protocols.org/stats?id=41439993) #11 10 points 1 comments -> [Hacking sales as an introvert](https://shwin.co/blog/hacking-sales-as-an-introvert)<!-- HN:41439993:end -->
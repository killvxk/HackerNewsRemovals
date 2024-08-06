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

#### **Wednesday, July 31, 2024**
<!-- HN:41114468:start -->
* [41114468](https://news.social-protocols.org/stats?id=41114468) #28 6 points 0 comments -> [Check Maybe Div by Zero for Gleam](https://hexdocs.pm/check_maybe_div_by_zero/)<!-- HN:41114468:end --><!-- HN:41115776:start -->
* [41115776](https://news.social-protocols.org/stats?id=41115776) #17 -> [X suspends 'White Dudes for Harris' account after fundraiser](https://www.washingtonpost.com/technology/2024/07/30/white-dudes-harris-suspended-x-twitter/)<!-- HN:41115776:end --><!-- HN:41068016:start -->
* [41068016](https://news.social-protocols.org/stats?id=41068016) #27 26 points 6 comments -> [Zuo: A Tiny Racket for Scripting](https://github.com/racket/zuo)<!-- HN:41068016:end --><!-- HN:41116617:start -->
* [41116617](https://news.social-protocols.org/stats?id=41116617) #5 9 points 5 comments -> [Jio Cloud](https://www.jio.com/business/services/jio-cloud)<!-- HN:41116617:end --><!-- HN:41115911:start -->
* [41115911](https://news.social-protocols.org/stats?id=41115911) #27 36 points 20 comments -> [Nobody Cares](https://a16z.com/nobody-cares/)<!-- HN:41115911:end --><!-- HN:41116885:start -->
* [41116885](https://news.social-protocols.org/stats?id=41116885) #23 12 points 7 comments -> [Fedora Asahi Remix](https://bentsukun.ch/posts/fedora-asahi/)<!-- HN:41116885:end --><!-- HN:41118281:start -->
* [41118281](https://news.social-protocols.org/stats?id=41118281) #20 12 points 6 comments -> [Australia starts world-first peanut allergy treatment for babies](https://www.bbc.co.uk/news/articles/c0xj3xq5l1vo)<!-- HN:41118281:end --><!-- HN:41118349:start -->
* [41118349](https://news.social-protocols.org/stats?id=41118349) #15 13 points 27 comments -> [Which country consumes the most coffee?](https://cafely.com/blogs/research/which-country-consumes-the-most-coffee)<!-- HN:41118349:end --><!-- HN:41118659:start -->
* [41118659](https://news.social-protocols.org/stats?id=41118659) #22 16 points 8 comments -> [New study finds people alter their appearance to suit their names](https://phys.org/news/2024-07-reveals-people-evolve.html)<!-- HN:41118659:end --><!-- HN:41118300:start -->
* [41118300](https://news.social-protocols.org/stats?id=41118300) #20 4 points 0 comments -> [So You're Thinking About Monetizing Your Blog – Loren's Blog](https://lorenblog.me/posts/so-you-re-thinking-about-monetizing-your-blog)<!-- HN:41118300:end --><!-- HN:41118962:start -->
* [41118962](https://news.social-protocols.org/stats?id=41118962) #24 18 points 2 comments -> [A Mathematician's Lament [pdf]](https://worrydream.com/refs/Lockhart_2002_-_A_Mathematician%27s_Lament.pdf)<!-- HN:41118962:end --><!-- HN:41119486:start -->
* [41119486](https://news.social-protocols.org/stats?id=41119486) #29 4 points 0 comments -> [Ukrainian Weaponized Yamaha Jet Ski with Starlink Antenna](http://www.hisutton.com/Ukraine-USV-Jetski.html)<!-- HN:41119486:end --><!-- HN:41119218:start -->
* [41119218](https://news.social-protocols.org/stats?id=41119218) #27 15 points 5 comments -> [Tesla recalls 1.8M cars because their hoods can open while driving](https://arstechnica.com/cars/2024/07/tesla-recalls-1-8-million-cars-because-their-hoods-can-open-while-driving/)<!-- HN:41119218:end --><!-- HN:41076399:start -->
* [41076399](https://news.social-protocols.org/stats?id=41076399) #6 6 points 1 comments -> [Two Threads One Core : How Simultaneous Multithreading Works Under the Hood ?](https://blog.codingconfessions.com/p/simultaneous-multithreading)<!-- HN:41076399:end --><!-- HN:41121083:start -->
* [41121083](https://news.social-protocols.org/stats?id=41121083) #24 39 points 18 comments -> [Oil companies sold the public on a fake climate solution](https://www.vox.com/climate/363076/climate-change-solution-shell-exxon-mobil-carbon-capture)<!-- HN:41121083:end --><!-- HN:41120961:start -->
* [41120961](https://news.social-protocols.org/stats?id=41120961) #30 10 points 11 comments -> [Xbox console sales continue to crater with 42% revenue drop](https://arstechnica.com/gaming/2024/07/xbox-console-sales-continue-to-crater-with-massive-42-revenue-drop/)<!-- HN:41120961:end --><!-- HN:41121721:start -->
* [41121721](https://news.social-protocols.org/stats?id=41121721) #14 11 points 0 comments -> [Kamala Harris gets support of more than 100 VCs and tech execs in online pledge](https://www.cnbc.com/2024/07/31/more-than-100-techies-sign-vcs-for-kamala-pledge-backing-vp-harris.html)<!-- HN:41121721:end --><!-- HN:41122792:start -->
* [41122792](https://news.social-protocols.org/stats?id=41122792) #4 33 points 11 comments -> [Heavy metal analysis of dark chocolate and cocoa products in the USA](https://www.frontiersin.org/journals/nutrition/articles/10.3389/fnut.2024.1366231/full)<!-- HN:41122792:end --><!-- HN:41123449:start -->
* [41123449](https://news.social-protocols.org/stats?id=41123449) #14 29 points 10 comments -> [This Month in Ladybird: July 2024](https://mailchi.mp/ladybird/july-2024)<!-- HN:41123449:end --><!-- HN:41122986:start -->
* [41122986](https://news.social-protocols.org/stats?id=41122986) #7 81 points 24 comments -> [An affordable, portable and focused device for music, writing and coding](https://tulip.computer/)<!-- HN:41122986:end -->
#### **Thursday, August 1, 2024**
<!-- HN:41123989:start -->
* [41123989](https://news.social-protocols.org/stats?id=41123989) #28 20 points 11 comments -> [Two new dementia risks identified by major report](https://www.bbc.com/news/articles/c84jdxd4x1ro)<!-- HN:41123989:end --><!-- HN:41124007:start -->
* [41124007](https://news.social-protocols.org/stats?id=41124007) #7 12 points 1 comments -> [Files](https://www.files.gallery/)<!-- HN:41124007:end --><!-- HN:41073907:start -->
* [41073907](https://news.social-protocols.org/stats?id=41073907) #21 39 points 18 comments -> [Is the nervous system a democracy? (2016)](https://www.scientificamerican.com/article/is-your-nervous-system-a-democracy-or-a-dictatorship/)<!-- HN:41073907:end --><!-- HN:41076021:start -->
* [41076021](https://news.social-protocols.org/stats?id=41076021) #28 129 points 59 comments -> [Where does the name "algebraic data type" come from?](https://blog.poisson.chat/posts/2024-07-26-adt-history.html)<!-- HN:41076021:end --><!-- HN:41126365:start -->
* [41126365](https://news.social-protocols.org/stats?id=41126365) #20 5 points 2 comments -> [Predicting Harris' VP nominee based on who's scrubbing their Wikipedia page most](https://old.reddit.com/r/dataisbeautiful/s/Ryxq8HaA0a)<!-- HN:41126365:end --><!-- HN:41127269:start -->
* [41127269](https://news.social-protocols.org/stats?id=41127269) #21 49 points 42 comments -> [Google listed my restaurant's number as its British HQ](https://www.theguardian.com/money/article/2024/aug/01/google-listed-my-restaurants-number-as-its-british-hq)<!-- HN:41127269:end --><!-- HN:41126130:start -->
* [41126130](https://news.social-protocols.org/stats?id=41126130) #14 126 points 15 comments -> [This month in Servo: console logging, parallel tables, OpenXR, and more](https://servo.org/blog/2024/07/31/this-month-in-servo/)<!-- HN:41126130:end --><!-- HN:41124112:start -->
* [41124112](https://news.social-protocols.org/stats?id=41124112) #17 67 points 41 comments -> [Show HN: Non SaaS – Directory of Non SaaS Apps](https://nonsaas.com)<!-- HN:41124112:end --><!-- HN:41127496:start -->
* [41127496](https://news.social-protocols.org/stats?id=41127496) #16 26 points 2 comments -> [Amazon is responsible for recalling unsafe products sold on its site,agency says](https://www.npr.org/2024/08/01/g-s1-14633/amazon-must-recall-unsafe-products-independent-sellers)<!-- HN:41127496:end --><!-- HN:41128528:start -->
* [41128528](https://news.social-protocols.org/stats?id=41128528) #30 10 points 6 comments -> [The VS Code Flatpak is useless](https://bentsukun.ch/posts/vscode-flatpak/)<!-- HN:41128528:end --><!-- HN:41128413:start -->
* [41128413](https://news.social-protocols.org/stats?id=41128413) #15 15 points 41 comments -> [Scientist Wants to Block the Sun to Cool the Earth](https://www.nytimes.com/2024/08/01/climate/david-keith-solar-geoengineering.html)<!-- HN:41128413:end --><!-- HN:41128541:start -->
* [41128541](https://news.social-protocols.org/stats?id=41128541) #20 9 points 3 comments -> [Unusual Whales Subversive Democratic Trading ETF](https://finance.yahoo.com/quote/NANC/)<!-- HN:41128541:end --><!-- HN:41129328:start -->
* [41129328](https://news.social-protocols.org/stats?id=41129328) #16 14 points 5 comments -> [Anger mounts over environmental cost of Google datacentre in Uruguay](https://www.theguardian.com/global-development/article/2024/aug/01/uruguay-anger-environmental-cost-google-datacentre-carbon-emissions-toxic-waste-water)<!-- HN:41129328:end --><!-- HN:41128990:start -->
* [41128990](https://news.social-protocols.org/stats?id=41128990) #24 55 points 99 comments -> [Proposed rule would ban airlines from charging parents to sit with children](https://www.cnbc.com/2024/08/01/proposed-rule-would-ban-airlines-from-charging-parents-to-sit-with-their-children.html)<!-- HN:41128990:end --><!-- HN:41130035:start -->
* [41130035](https://news.social-protocols.org/stats?id=41130035) #6 10 points 1 comments -> [Single precision matrix multiplication up to 43% faster than the one from cuBLAS](https://github.com/arekpaterek/Faster_SGEMM_CUDA)<!-- HN:41130035:end --><!-- HN:41091245:start -->
* [41091245](https://news.social-protocols.org/stats?id=41091245) #13 30 points 10 comments -> [Discovering a New Neolithic World](https://archaeology.org/issues/march-april-2024/features/discovering-a-new-neolithic-world/)<!-- HN:41091245:end --><!-- HN:41129752:start -->
* [41129752](https://news.social-protocols.org/stats?id=41129752) #24 39 points 40 comments -> [Say less in your emails, get more replies](https://www.gkogan.co/increase-reply-rates/)<!-- HN:41129752:end --><!-- HN:41131238:start -->
* [41131238](https://news.social-protocols.org/stats?id=41131238) #17 8 points 0 comments -> [Planted bomb, remote control and AI: How the Mossad killed Hamas' leader in Iran](https://www.axios.com/2024/08/01/haniyeh-assassination-mossad)<!-- HN:41131238:end --><!-- HN:41130342:start -->
* [41130342](https://news.social-protocols.org/stats?id=41130342) #28 35 points 18 comments -> [Intel Faces Potential Class-Action Lawsuit over Chip Bug Controversy](https://uk.pcmag.com/processors/153676/intel-faces-potential-class-action-lawsuit-over-chip-bug-controversy)<!-- HN:41130342:end --><!-- HN:41132822:start -->
* [41132822](https://news.social-protocols.org/stats?id=41132822) #22 56 points 32 comments -> [Pharma CIO cancels AI enhanced Office 365 deal as "it doesn't add value"](https://hardforum.com/threads/pharma-cio-cancels-ai-enhanced-office-365-deal-as-it-doesnt-add-value.2036205/)<!-- HN:41132822:end -->
#### **Friday, August 2, 2024**
<!-- HN:41093197:start -->
* [41093197](https://news.social-protocols.org/stats?id=41093197) #18 158 points 81 comments -> [A skeptic's first contact with Kubernetes](https://blog.davidv.dev/posts/first-contact-with-k8s/)<!-- HN:41093197:end --><!-- HN:41136099:start -->
* [41136099](https://news.social-protocols.org/stats?id=41136099) #29 3 points 1 comments -> [US progressives push for Nvidia antitrust investigation](https://www.reuters.com/technology/us-progressives-push-nvidia-antitrust-investigation-2024-08-01/)<!-- HN:41136099:end --><!-- HN:41136905:start -->
* [41136905](https://news.social-protocols.org/stats?id=41136905) #26 8 points 0 comments -> [List of vintage Japanese pixel/dot art software](https://blog.gingerbeardman.com/2023/10/21/list-of-vintage-japanese-pixel-dot-art-software/)<!-- HN:41136905:end --><!-- HN:41137773:start -->
* [41137773](https://news.social-protocols.org/stats?id=41137773) #29 7 points 3 comments -> [Ask iFixit: Does Blowing Into Gaming Cartridges Actually Fix Them?](https://www.ifixit.com/News/97647/ask-ifixit-does-blowing-into-gaming-cartridges-actually-fix-them)<!-- HN:41137773:end --><!-- HN:41138119:start -->
* [41138119](https://news.social-protocols.org/stats?id=41138119) #17 5 points 2 comments -> [Eating Processed Red Meat Linked to Increased Dementia Risk](https://www.nytimes.com/2024/07/31/well/eat/ultraprocessed-foods-brain-health.html)<!-- HN:41138119:end --><!-- HN:41138840:start -->
* [41138840](https://news.social-protocols.org/stats?id=41138840) #4 5 points 1 comments -> [Pregnancy in Patient with XY Chromosomes](https://www.fertstert.org/article/S0015-0282(10)02954-7/fulltext)<!-- HN:41138840:end --><!-- HN:41139419:start -->
* [41139419](https://news.social-protocols.org/stats?id=41139419) #5 6 points 0 comments -> [Predicting political beliefs with scores for cognitive performance](https://mfr.osf.io/render?url=https%3A%2F%2Fosf.io%2Fdownload%2Fbdr6s%2F%3Fdirect%3D%26mode%3Drender)<!-- HN:41139419:end --><!-- HN:41139696:start -->
* [41139696](https://news.social-protocols.org/stats?id=41139696) #23 7 points 2 comments -> [Show HN: I built an interactive demo builder for your sales team](https://demoshake.com)<!-- HN:41139696:end --><!-- HN:41100737:start -->
* [41100737](https://news.social-protocols.org/stats?id=41100737) #27 279 points 134 comments -> [The protein Reelin keeps popping up in brains that resist aging and Alzheimer’s](https://www.npr.org/sections/shots-health-news/2024/07/29/g-s1-13519/alzheimers-protein-reelin-brain-aging-amyloid-tau-memory)<!-- HN:41100737:end --><!-- HN:41140263:start -->
* [41140263](https://news.social-protocols.org/stats?id=41140263) #5 29 points 7 comments -> [Does the success of LLM support Wittgenstein's position that "meaning is use"?](https://philosophy.stackexchange.com/questions/112021/does-the-success-of-ai-large-language-models-support-wittgensteins-position-t)<!-- HN:41140263:end --><!-- HN:41142365:start -->
* [41142365](https://news.social-protocols.org/stats?id=41142365) #29 7 points 3 comments -> [Why are religious teens happier than their secular peers?](https://www.bostonglobe.com/2024/06/06/opinion/religious-teens-mental-health/)<!-- HN:41142365:end -->
#### **Saturday, August 3, 2024**<!-- HN:41144106:start -->
* [41144106](https://news.social-protocols.org/stats?id=41144106) #6 10 points 2 comments -> [What are the odds, II: the Venezuelan presidential election](https://terrytao.wordpress.com/2024/08/02/what-are-the-odds-ii-the-venezuelan-presidential-election/)<!-- HN:41144106:end --><!-- HN:41144434:start -->
* [41144434](https://news.social-protocols.org/stats?id=41144434) #3 11 points 4 comments -> [Games Managers Play: Unmasking Psychological Tactics in Tech Leadership](https://praachi.work/blog/games-managers-play.html)<!-- HN:41144434:end --><!-- HN:41144108:start -->
* [41144108](https://news.social-protocols.org/stats?id=41144108) #29 26 points 2 comments -> [Stop Destroying Videogames – European Citizens' Initiative](https://eci.ec.europa.eu/045/public/#/screen/home)<!-- HN:41144108:end --><!-- HN:41144521:start -->
* [41144521](https://news.social-protocols.org/stats?id=41144521) #15 26 points 9 comments -> [US Library of Congress Digital Archive Formats](https://www.loc.gov/preservation/resources/rfs/TOC.html)<!-- HN:41144521:end --><!-- HN:41144571:start -->
* [41144571](https://news.social-protocols.org/stats?id=41144571) #29 33 points 6 comments -> [SpaceX Raptor 3, SN1](https://twitter.com/elonmusk/status/1819551225504768286/photo/1)<!-- HN:41144571:end --><!-- HN:41143452:start -->
* [41143452](https://news.social-protocols.org/stats?id=41143452) #24 77 points 40 comments -> [EWritable – e-ink tablet news and reviews](https://ewritable.com/)<!-- HN:41143452:end --><!-- HN:41145314:start -->
* [41145314](https://news.social-protocols.org/stats?id=41145314) #21 8 points 2 comments -> [Why America fell behind in drones, and how to catch up agaon](https://www.noahpinion.blog/p/why-america-fell-behind-in-drones)<!-- HN:41145314:end --><!-- HN:41145732:start -->
* [41145732](https://news.social-protocols.org/stats?id=41145732) #16 37 points 42 comments -> [Delivery worker minimum wage is bringing order to a wild industry](https://nyc.streetsblog.org/2024/07/15/delivery-worker-minimum-wage-brings-order-to-industry-data-shows)<!-- HN:41145732:end --><!-- HN:41146167:start -->
* [41146167](https://news.social-protocols.org/stats?id=41146167) #29 7 points 4 comments -> [Wi-Fi is an important threat to human health (2018)](https://www.sciencedirect.com/science/article/pii/S0013935118300355)<!-- HN:41146167:end --><!-- HN:41142921:start -->
* [41142921](https://news.social-protocols.org/stats?id=41142921) #9 8 points 6 comments -> [Reverse Captcha](https://www.selabs.tech/reverse-captcha)<!-- HN:41142921:end --><!-- HN:41147109:start -->
* [41147109](https://news.social-protocols.org/stats?id=41147109) #13 15 points 1 comments -> [Intel took billions from the CHIPS Act, and gave nothing back](https://nypost.com/2024/08/02/opinion/biden-harris-wasted-8-5-billion-in-taxpayer-money-to-lose-15000-jobs-at-intel/)<!-- HN:41147109:end --><!-- HN:41146320:start -->
* [41146320](https://news.social-protocols.org/stats?id=41146320) #23 7 points 0 comments -> [An epic environment manager to fix local environment variable management](https://github.com/danthegoodman1/EpicEnv)<!-- HN:41146320:end --><!-- HN:41147464:start -->
* [41147464](https://news.social-protocols.org/stats?id=41147464) #16 4 points 1 comments -> [Show HN: InstaCured – Instant telehealth at $19 per visit](https://instacured.com/)<!-- HN:41147464:end --><!-- HN:41146132:start -->
* [41146132](https://news.social-protocols.org/stats?id=41146132) #21 36 points 40 comments -> [The Danger of Superhuman AI Is Not What You Think](https://www.noemamag.com/the-danger-of-superhuman-ai-is-not-what-you-think/)<!-- HN:41146132:end --><!-- HN:41148961:start -->
* [41148961](https://news.social-protocols.org/stats?id=41148961) #27 5 points 1 comments -> [Why America fell behind in drones, and how to catch up again](https://www.noahpinion.blog/p/why-america-fell-behind-in-drones)<!-- HN:41148961:end --><!-- HN:41144072:start -->
* [41144072](https://news.social-protocols.org/stats?id=41144072) #19 61 points 26 comments -> [Back dating Git commits based on file modification dates](https://til.simonwillison.net/git/backdate-git-commits)<!-- HN:41144072:end --><!-- HN:41149220:start -->
* [41149220](https://news.social-protocols.org/stats?id=41149220) #19 15 points 5 comments -> [Intel is a Victim of its Own Arrogance](https://innovationnation.blog/p/intel-is-a-victim-of-its-own-arrogance)<!-- HN:41149220:end -->
#### **Sunday, August 4, 2024**
<!-- HN:41149906:start -->
* [41149906](https://news.social-protocols.org/stats?id=41149906) #11 27 points 13 comments -> [What are the odds, II: the Venezuelan presidential election](https://terrytao.wordpress.com/2024/08/02/what-are-the-odds-ii-the-venezuelan-presidential-election/)<!-- HN:41149906:end --><!-- HN:41147830:start -->
* [41147830](https://news.social-protocols.org/stats?id=41147830) #21 51 points 6 comments -> [Show HN: Plain Vanilla – a tutorial website for vanilla web development](https://plainvanillaweb.com/)<!-- HN:41147830:end --><!-- HN:41150372:start -->
* [41150372](https://news.social-protocols.org/stats?id=41150372) #28 14 points 1 comments -> [Automating away the boring parts of my job with Gemini 1.5 Pro and long context](https://medium.com/@webpaige/automating-away-the-boring-parts-of-my-job-with-gemini-1-5-pro-long-context-windows-6d5a1d9a6f38)<!-- HN:41150372:end --><!-- HN:41151687:start -->
* [41151687](https://news.social-protocols.org/stats?id=41151687) #4 4 points 0 comments -> [I made my personal website](https://www.mandar.fun/)<!-- HN:41151687:end --><!-- HN:41152040:start -->
* [41152040](https://news.social-protocols.org/stats?id=41152040) #12 27 points 20 comments -> [The Academic Culture of Fraud](https://www.palladiummag.com/2024/08/02/the-academic-culture-of-fraud/)<!-- HN:41152040:end --><!-- HN:41150278:start -->
* [41150278](https://news.social-protocols.org/stats?id=41150278) #17 133 points 83 comments -> [Nvidia reportedly delays its next AI chip due to a design flaw](https://www.theverge.com/2024/8/3/24212518/nvidia-ai-chip-delay-blackwell-b200-microsoft-amazon-google-openai-meta-artificial-intelligence)<!-- HN:41150278:end --><!-- HN:41150483:start -->
* [41150483](https://news.social-protocols.org/stats?id=41150483) #20 25 points 17 comments -> [Perfect NAS Solution](https://vermaden.wordpress.com/2024/08/04/perfect-nas-solution/)<!-- HN:41150483:end --><!-- HN:41149882:start -->
* [41149882](https://news.social-protocols.org/stats?id=41149882) #15 70 points 12 comments -> [Reverse engineering XC2064, the first FPGA  (2020)](https://www.righto.com/2020/09/reverse-engineering-first-fpga-chip.html)<!-- HN:41149882:end --><!-- HN:41149948:start -->
* [41149948](https://news.social-protocols.org/stats?id=41149948) #14 64 points 3 comments -> [Upgrading my Chumby 8 kernel part 13: the end](https://www.downtowndougbrown.com/2024/08/upgrading-my-chumby-8-kernel-part-13-the-end/)<!-- HN:41149948:end --><!-- HN:41153147:start -->
* [41153147](https://news.social-protocols.org/stats?id=41153147) #4 4 points 1 comments -> [AI Personal Assistant with RAG and LLM](https://github.com/mytechnotalent/pa)<!-- HN:41153147:end --><!-- HN:41154033:start -->
* [41154033](https://news.social-protocols.org/stats?id=41154033) #15 9 points 1 comments -> [A WA Tax Break for Data Centers Became One of Their Biggest Corporate Giveaways](https://www.propublica.org/article/washington-data-centers-tech-jobs-tax-break)<!-- HN:41154033:end --><!-- HN:41154219:start -->
* [41154219](https://news.social-protocols.org/stats?id=41154219) #7 6 points 1 comments -> [People High on Dark Triad Personality Traits Employ Distinct Defense Mechanisms](https://www.robkhenderson.com/p/people-with-dark-triad-personality)<!-- HN:41154219:end --><!-- HN:41153980:start -->
* [41153980](https://news.social-protocols.org/stats?id=41153980) #28 9 points 12 comments -> [Wasted Education: How We Fail Our Graduates in STEM [video]](https://www.youtube.com/watch?v=ZTWaSPzAgBA)<!-- HN:41153980:end --><!-- HN:41155587:start -->
* [41155587](https://news.social-protocols.org/stats?id=41155587) #22 8 points 7 comments -> [Rich, western countries face a stark choice: 6-day workweeks or more immigration](https://fortune.com/2024/08/04/rich-western-countries-face-a-stark-choice-6-day-workweeks-or-more-immigration-top-economist-warns/)<!-- HN:41155587:end -->
#### **Monday, August 5, 2024**
<!-- HN:41157140:start -->
* [41157140](https://news.social-protocols.org/stats?id=41157140) #11 5 points 0 comments -> [How would you explain a tensor to a computer scientist?](https://math.stackexchange.com/questions/4861085/how-would-you-explain-a-tensor-to-a-computer-scientist)<!-- HN:41157140:end --><!-- HN:41154560:start -->
* [41154560](https://news.social-protocols.org/stats?id=41154560) #17 194 points 66 comments -> [Praise My GitHub Profile](https://praise-me.fly.dev/)<!-- HN:41154560:end --><!-- HN:41160815:start -->
* [41160815](https://news.social-protocols.org/stats?id=41160815) #18 8 points 3 comments -> [CrowdStrike unhappy with Delta litigation threat, says airline refused free help](https://www.theregister.com/2024/08/05/crowdstrike_is_not_at_all/)<!-- HN:41160815:end --><!-- HN:41161437:start -->
* [41161437](https://news.social-protocols.org/stats?id=41161437) #8 34 points 42 comments -> [CrowdStrike to Delta: Stop pointing at us](https://www.wsj.com/business/airlines/crowdstrike-to-delta-stop-pointing-the-finger-at-us-5b2eea6c)<!-- HN:41161437:end --><!-- HN:41161736:start -->
* [41161736](https://news.social-protocols.org/stats?id=41161736) #20 15 points 2 comments -> [Build a Digital Human](https://build.nvidia.com/nvidia/digital-humans-virtual-assistant)<!-- HN:41161736:end --><!-- HN:41163304:start -->
* [41163304](https://news.social-protocols.org/stats?id=41163304) #6 7 points 1 comments -> [Why Polars destroys Pandas in all possible ways for Data Scientists](https://differ.blog/inplainenglish/why-polars-destroys-pandas-in-all-possible-ways-for-data-scientists-b9c662)<!-- HN:41163304:end --><!-- HN:41163583:start -->
* [41163583](https://news.social-protocols.org/stats?id=41163583) #29 3 points 0 comments -> [Safari can block distracting ads and other website clutter with latest beta](https://www.engadget.com/safari-can-block-distracting-ads-and-other-website-clutter-with-the-latest-ios-18-and-macos-betas-172041678.html)<!-- HN:41163583:end --><!-- HN:41161466:start -->
* [41161466](https://news.social-protocols.org/stats?id=41161466) #30 3 points 0 comments -> [Does PostgreSQL respond to the challenge of analytical queries?](https://danolivo.substack.com/p/does-postgresql-respond-to-the-challenge)<!-- HN:41161466:end --><!-- HN:41161085:start -->
* [41161085](https://news.social-protocols.org/stats?id=41161085) #28 6 points 0 comments -> [Rust-Python interoperability [hands-on course]](https://rust-exercises.com/rust-python-interop/)<!-- HN:41161085:end --><!-- HN:41163536:start -->
* [41163536](https://news.social-protocols.org/stats?id=41163536) #27 13 points 6 comments -> [Apple's new Safari feature removes distracting items from websites](https://techcrunch.com/2024/08/05/apples-new-safari-feature-removes-distracting-items-from-websites/)<!-- HN:41163536:end --><!-- HN:41163983:start -->
* [41163983](https://news.social-protocols.org/stats?id=41163983) #26 5 points 2 comments -> [Every Microsoft employee is now being judged on their security work](https://www.theverge.com/2024/8/5/24213774/microsoft-security-performance-reviews-employees-top-priority)<!-- HN:41163983:end --><!-- HN:41164234:start -->
* [41164234](https://news.social-protocols.org/stats?id=41164234) #25 9 points 1 comments -> [Google Loses DOJ Antitrust Case over Search](https://www.nytimes.com/2024/08/05/technology/google-antitrust-ruling.html)<!-- HN:41164234:end --><!-- HN:41163203:start -->
* [41163203](https://news.social-protocols.org/stats?id=41163203) #18 11 points 3 comments -> [GPU Restaking – Beyond digital currencies to physical computing resources](https://blog.bagel.net/p/gpu-restaking)<!-- HN:41163203:end --><!-- HN:41163569:start -->
* [41163569](https://news.social-protocols.org/stats?id=41163569) #28 11 points 2 comments -> [Markets tremble over risks to US economy – AP News](https://apnews.com/article/stocks-markets-nikkei-economy-c6240977e9482bf7207abc53b2a11e58)<!-- HN:41163569:end --><!-- HN:41163847:start -->
* [41163847](https://news.social-protocols.org/stats?id=41163847) #30 16 points 16 comments -> [Gen Z became so nihilistic about money](https://www.bbc.com/worklife/article/20240731-how-gen-z-became-so-nihilistic-about-money)<!-- HN:41163847:end --><!-- HN:41164747:start -->
* [41164747](https://news.social-protocols.org/stats?id=41164747) #25 5 points 0 comments -> [Google is an illegal monopoly, federal court rules](https://www.washingtonpost.com/technology/2024/08/05/doj-google-monopoly-trial-judgment/)<!-- HN:41164747:end --><!-- HN:41162789:start -->
* [41162789](https://news.social-protocols.org/stats?id=41162789) #30 18 points 0 comments -> [Smartphone use decreases trustworthiness of strangers](https://www.sciencedirect.com/science/article/pii/S0167487024000229)<!-- HN:41162789:end --><!-- HN:41164876:start -->
* [41164876](https://news.social-protocols.org/stats?id=41164876) #28 3 points 1 comments -> [Google loses antitrust case over its search dominance](https://apnews.com/article/google-antitrust-search-engine-verdict-apple-319a61f20fb11510097845a30abaefd8)<!-- HN:41164876:end --><!-- HN:41164878:start -->
* [41164878](https://news.social-protocols.org/stats?id=41164878) #29 9 points 0 comments -> [A Republican State A.G. Fights to Keep Exonerated Prisoners Behind Bars](https://www.nytimes.com/2024/08/05/us/missouri-andrew-bailey-exonerated.html)<!-- HN:41164878:end --><!-- HN:41165409:start -->
* [41165409](https://news.social-protocols.org/stats?id=41165409) #5 11 points 2 comments -> [The Anatomy of Brainwashing](https://www.science.org/doi/10.1126/science.adp1705)<!-- HN:41165409:end --><!-- HN:41165536:start -->
* [41165536](https://news.social-protocols.org/stats?id=41165536) #23 3 points 0 comments -> [Moral Implications of Being a Moderately Successful Computer Scientist and Woman](https://www.sigops.org/2024/the-moral-implications-of-being-a-moderately-successful-computer-scientist-and-a-woman/)<!-- HN:41165536:end -->
#### **Tuesday, August 6, 2024**<!-- HN:41167891:start -->
* [41167891](https://news.social-protocols.org/stats?id=41167891) #11 6 points 0 comments -> [How the Regime Captured Wikipedia](https://www.piratewires.com/p/how-the-regime-captured-wikipedia)<!-- HN:41167891:end --><!-- HN:41166844:start -->
* [41166844](https://news.social-protocols.org/stats?id=41166844) #27 39 points 55 comments -> [Why is it so hard for the U.S. to build quality transit?](https://www.fastcompany.com/91166562/us-transit-exceptionalism)<!-- HN:41166844:end --><!-- HN:41167645:start -->
* [41167645](https://news.social-protocols.org/stats?id=41167645) #10 24 points 40 comments -> [Don't use Vim for the wrong reasons](https://gist.github.com/romainl/6b952db7a6138b48657ba0fbb9d65370)<!-- HN:41167645:end --><!-- HN:41167624:start -->
* [41167624](https://news.social-protocols.org/stats?id=41167624) #17 9 points 5 comments -> [A simply utility script which allows you to analyze your Python file](https://github.com/mraza007/python-file-analyzer)<!-- HN:41167624:end --><!-- HN:41169454:start -->
* [41169454](https://news.social-protocols.org/stats?id=41169454) #3 3 points 1 comments -> [Politicisation and Vandalism in the UK's Education](https://dominiccummings.substack.com/p/how-to-help-parents-and-teachers)<!-- HN:41169454:end --><!-- HN:41169470:start -->
* [41169470](https://news.social-protocols.org/stats?id=41169470) #1 11 points 0 comments -> [Reverse Diversity](https://www.drmindle.com/reverse-diversity/)<!-- HN:41169470:end --><!-- HN:41169538:start -->
* [41169538](https://news.social-protocols.org/stats?id=41169538) #14 39 points 41 comments -> [Big Macs and the Cost of Living Crisis](https://www.abc.net.au/news/2024-08-05/cost-of-living-interest-rates-burgers/104156654)<!-- HN:41169538:end --><!-- HN:41169407:start -->
* [41169407](https://news.social-protocols.org/stats?id=41169407) #18 18 points 5 comments -> [Minds are 'not currency for social media,' says EU as TikTok kills Lite Rewards](https://thenextweb.com/news/tiktok-kills-lite-rewards-eu)<!-- HN:41169407:end --><!-- HN:41168836:start -->
* [41168836](https://news.social-protocols.org/stats?id=41168836) #25 31 points 6 comments -> [Hetzner Cloud now also in Singapore](https://www.hetzner.com/news/new-location-singapore/)<!-- HN:41168836:end --><!-- HN:41170830:start -->
* [41170830](https://news.social-protocols.org/stats?id=41170830) #1 -> [Men report more pressure and threats to share location and accounts](https://malware.news/t/men-report-more-pressure-and-threats-to-share-location-and-accounts-with-partners-research-shows/84907)<!-- HN:41170830:end --><!-- HN:41171045:start -->
* [41171045](https://news.social-protocols.org/stats?id=41171045) #24 3 points 0 comments -> [Applied Materials Denied US CHIPS Act Funding](https://www.datacenterdynamics.com/en/news/applied-materials-denied-us-chips-act-funding-report/)<!-- HN:41171045:end --><!-- HN:41170713:start -->
* [41170713](https://news.social-protocols.org/stats?id=41170713) #23 8 points 9 comments -> [Ziff Davis is buying CNET for just $100M](https://www.theverge.com/2024/8/6/24214374/cnet-zeff-davis-acquisition-digital-media-100-million)<!-- HN:41170713:end --><!-- HN:41172118:start -->
* [41172118](https://news.social-protocols.org/stats?id=41172118) #21 8 points 0 comments -> [Whistleblowers Report Tulsi Gabbard Actively Under TSA Surveillance](https://uncoverdc.com/2024/08/04/fams-whistleblowers-report-tulsi-gabbard-on-quiet-skies-list)<!-- HN:41172118:end --><!-- HN:41173564:start -->
* [41173564](https://news.social-protocols.org/stats?id=41173564) #12 26 points 9 comments -> [Former geography teacher Tim Walz is really into maps](https://minnesotareformer.com/2024/08/06/former-geography-teacher-tim-walz-is-really-into-maps/)<!-- HN:41173564:end -->
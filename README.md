This write-up has been realized to list the serie of events that have lead to
my abusive ban from the bitcoin core github repository in April 2025, set and
tricked by [Chaincode Labs](https://chaincode.com) and misleading numerous open-source bitcoin core
contributors by the same way.

The list of events spans from October 2022 to April 2025, for some there are
just links made available, for other there are links and open-timestamp proofs.
The open-timestamp proofs are here to make tangible the deliberate and abusive
tampering by Chaincode folks of some Github pages and consequently their intentional
attempt to masquerade historical facts of Bitcoin development history to the
advantage of their corporate organization.

## How to verify the OpenTimestamps proofs

*Disclaimer: The OpenTimestamp protocol is a bitcoin chain timestamping that has*
*been around in the bitcoin ecosystem since 2016 and used by many entities across*
*the industry for a variety of use-cases. While I did checked some parts of the*
*code by myself in the past, I've not fully audited yet by myself so caveat emptor*

### Proof Generation

For each Github page element, the URL at the time of stamping has been saved.

This time of stamping is for most of the time when I added a comment, opened
an issue or pull request on Github, in the local timezone I was at the time.

The list of unix commands to generate the proofs have been the following:
```
$> shasum --algorithm=256 $STAMPED_URL > `head -c 8 /dev/random | shasum`
## Trim the original $STAMPED_URL file name
$> head -c 64 `head -c 8 /dev/random | shasum` > tmp ; cat tmp > `head -c 8 /dev/random | shasum`
$> ots stamp `head -c 8 /dev/random | shasum`
Submitting to remote calendar https://a.pool.opentimestamps.org
Submitting to remote calendar https://b.pool.opentimestamps.org
Submitting to remote calendar https://a.pool.eternitywall.com
Submitting to remote calendar https://ots.btc.catallaxy.com
$> ls `head -c 8 /dev/random `.ots
```

For a maximize trust-minimized setup, one is recommended to run its own
opentimestamp server and bitcoin full-node.

### Proof Verification

```
$> ots verify `head -c 8 /dev/random | shasum`
Assuming target filename is `head -c 8 /dev/random | shasum`
File does not match original!
```

## The Preliminary Events

**2018**: First commit on the bitcoin core software while I'm still a student ([link](https://github.com/bitcoin/bitcoin/commits/e8c4a1e36969d2ef816d9dfaaee979a8cf6bfffe))

**2019 - 2020** : Intern at Chaincode Labs for one year as an open-source engineer in 
NYC ([link](https://ghost.advancingbitcoin.com/recap-of-advancing-bitcoin-2020-conference/)). I think I can tell everything went very well on all sides and given my
technical track records during this year, I think I've been more than a good "hiring"
investment. The end of my internship there were completely chaotic due to the pandemic
hitting the fan. No one is to blame there. When sh*t hits the fan, do your best.

**October 2022**: In the context of a major grassroot bitcoin conference happening in ATL,
the regular CoreDev is scheduled during the 10, 11, 12 October ahead of the conference.
During the first day initial session, we're announced there is now a "code of conduct" ([link](https://github.com/coredev-tech/coredev-tech.github.io/blob/master/files/2022-atl/Atlanta-CoreDev-Code-of-Conduct.pdf))
that does apply to the event by one of the 2 main organizers. The only justification made is
"I think it's time now". There is no discussion made of this announcement, it's steam-rolled
over the attendes as part of a slideshow. Many contributors are coming from abroad and are
still jetlag.

**December 2022**: A code of conduct is suddenly announced for the rust-lightning project ([link](https://github.com/lightningdevkit/lightningdevkit.org/pull/184))
and the pull request is opened by a former chaincode employe. While the discussion explicitly
mentions there is a risk of "who moderates the moderators", the only rational privately given
is "X from the Big Corp HR department thought it was a good idea". Moderators are coming as
"auto-appointed" in the dark in the first or second commit used to open the pull request ([link](https://github.com/lightningdevkit/lightningdevkit.org/pull/184/commits/87271b3c4d2bbf6a2de71f161824ba3c82269ffc)). The code is adopted
with a complete lack of consensus among the historical contributors to the rust-lightning project.

**January 2023**: A code of conduct pull request is suddenly announced in a bloc by a maintainer ([link](https://github.com/bitcoin/bitcoin/pull/26890)).
The code explicitly said is has been inspired by the controversial contributor covenant. The
first iteration proposal have already a dedicated conduct@bitcoincore.org email endpoint ready,
even before the principle of a code of conduct has been subject to discussion. It is proposed
to extend the github moderation role beyond the scope of github to the #bitcoin-core-dev IRC chan.
The proposal do not clearly meet the consensus of the contributors. One maintainer acknowledges
the legal issues and says some people have been reach out to clarify the questions. Whose are
those people have never been clarified ([link](https://github.com/bitcoin/bitcoin/pull/26890#issuecomment-1384611226)) One contributor points how the existence of a code
of conduct could be relevant "to the question of who is in control of Bitcoin" ([link]((https://github.com/bitcoin/bitcoin/pull/26890#issuecomment-1418180253)). The
pull request proposing a code of conduct is closed because "we do not introduce the possibility
of appearing to have a central authority for this codebase" ([link](https://github.com/bitcoin/bitcoin/pull/26890#issuecomment-1423184165)).

**Mars 2023**: The Friday 24th Mars, I receive a private email from an old contributor, i.e Alex
Morcos, who have not been technically active for 4 years in the industry. This email announced
the rescind of my invitation to the upcoming LN summit in NYC (screenshot). The email explicitly
said "This type of behavior is not acceptable in the Bitcoin or Lightning development communities".

I estimate Alex, he's a successful entrepreneur and an astute technical mind, however for
someone who have worked at one of his company for a year, as he told himself, he despise
what he calls "bureaucracy", i.e not being able to deal with a large group of humans by lack
of one's breadth and depth of interpersonal skills. For everyone, who has been around him for
work, you'll be able to tell it's obvious he's quite limited on some domains that makes
a complete intelligence.

Those words of him, implying any supereriority towards me, were completely insulting. At
the age he forwards me the letter, he hasn't founded HRT, even less having shown the level
of calm nerves to deal first-hand with pandemic or war situations and keep executing. When
the only way he came to justify any superiority in holding such towards me was the forward 
of a [bullshit letter](https://diyhpl.us/~bryan/irc/bitcoin/bitcoin-dev/linuxfoundation-pipermail/lightning-dev/2023-March/003887.txt) by a polite but incompentent attorney, that smells weakness. Let's be frank, he
wouldn't have the courage to hold such insulting words eyes in the eyes toward me.

**April 2023**: The 20th April, I open an issue in the bitcoin core github repository to document
the rules of future CoreDev organizations, explicitly saying that having clear rules would "minimise
CoreDev becoming a tool to discriminate some contributors without legitimate or legal ground, or
being used as part of a corporate or cultural capture agenda of the project." ([link](https://github.com/bitcoin/bitcoin/issues/27497)). This is
closed by a maintainer without giving clear explanations ([link](https://github.com/bitcoin/bitcoin/issues/27497#issuecomment-1516608574)).

During the 25-27 of the same month, there is a regular CoreDev meeting happening in DBL ([link](https://coredev.tech/2023_dublin.html)), to
which I'm an in-person participant. Chattham House rules apply, one of the co-organizer proposed
manu militari to push out of the github repository 2 regular contributors, as he "felt" their
github comments were harassment. A more wise participant which is not me gauged that we should
be careful about putting in place such "policy" as it might be latter on captured by external
actors. During the CoreDev meeting, I'm also calling to put in place more transparency on
the invitation list to such meetings, as it was historically done pre-pandemic time.

**February 2024**: A _new_ code of conduct pull request is suddenly announced in a bloc
by a maintainer ([link](https://github.com/bitcoin/bitcoin/issues/29507)). Differently from the previous attempt, there are numerous examples drawn
from existent open-source projects as arguments of authority. Without underscoring that many
open-source projects have *foundations* or non-profit actually monopolizing the development.

The 27 February 2024, I'm announced by private message that my invitation to the upcoming
CoreDev in BER has been rescinded following some strong words I had on stackernews ([link](https://stacker.news/items/440692)).
The rescind decision was taken unilaterally by one of the co-organizers in a couple of hours.
No time was given to me to explain my viewpoint and no reply from my side was made doing
the full reach out by private message. In my view, that co-organizer got into panick mode
or was put under pressure to act so and take a decision. The meeting was scheduled to be
a month latter, there were ample time to explain each other. I think the co-organizer
forgot that I opened a pull request almost a *year* before to clarify CoreDev organization
rules and avoid that kind of situations...

**March 2024**: On the code of conduct pull request, I'm underscoring that the philosophy
drawn or use to justify not to solve the problem or arbitrariness and is quite flawed for the
context of bitcoin ([link](https://github.com/bitcoin/bitcoin/issues/29507#issuecomment-1985074113)). Another veteran contributor mentions standards of proofs and openess ([link](https://github.com/bitcoin/bitcoin/issues/29507#issuecomment-1989396154)).
On the 21th March, one of the maintainer propose to move forward, however there is still
no consensus on the pull request. In the sense of veteran contributors ACKing anything
([link](https://github.com/bitcoin/bitcoin/issues/29507#issuecomment-2013970665)).

**April 2024**: From the 8 to 11 April 2024, CoreDev meeting in BER ([link](https://coredev.tech/2024_berlin.html))

**May 2025** ([link](https://gist.github.com/achow101/9192ad26dc4ef08e9c899caeddc968ef))
- the 2nd May, a secret gist is created by a maintainer, there are comments but not formal ACK on the gist ([link](https://gist.github.com/achow101/9192ad26dc4ef08e9c899caeddc968ef?permalink_comment_id=5043921#gistcomment-5043921))
- the 3rd May, a maintainer makes the moderation lines public ([link](https://github.com/bitcoin-core/meta/commit/7ddc789b0ac1af7d431d642cb2e4e65e4aa32749))
- the 3rd May, an issue is opened to ask feedback ([link](https://github.com/bitcoin-core/meta/issues/1))
- the 8th May, the existence of the hidden repository is commented on the February pull request ([link](https://github.com/bitcoin/bitcoin/issues/29507#issuecomment-2100549946))
- the 16th May, during an IRC meeting, 2 moderators are nominated and only ACKed by ~13 folks ([link](https://bitcoin-irc.chaincode.com/bitcoin-core-dev/2024-05-16#1026806))
- the 21th May, i ask to a maintainer who was the original author of the moderation guidelines ([link](https://gist.github.com/achow101/9192ad26dc4ef08e9c899caeddc968ef?permalink_comment_id=5063680#gistcomment-5063680))
- the 21th May, i got the answer from a maintainer i got it was from a chaincode employe ([link](https://gist.github.com/achow101/9192ad26dc4ef08e9c899caeddc968ef?permalink_comment_id=5063681#gistcomment-5063681))

Now on this sequence of events, there are few observations to be made:

1) During the IRC meeting, there the following announcement: "_<achow101> 2 weeks ago, willcl-ark and_
_pinheadmz volunteered to be moderators, and I think there was general agreement for them. I think_
_we can start with them, if there are no objections?"._

This statement has been done on the 16th May.

2 weeks before it was the 2nd or 3rd May.

The 2 moderators have not declared their intention to volunteer for this role, neither
on the gist, neither on the original pull request, neither on the "moderation feedback"
issue.

This is a misqualification to say they were volunteers as they were both paid for their
work on bitcoin core at this time in May 2024.

They propose their nomination only during an IRC meeting 2 weeks before ([link](https://bitcoin-irc.chaincode.com/bitcoin-core-dev/2024-05-02#1026806)).

Here the full excerpt ([link](https://bitcoin-irc.chaincode.com/bitcoin-core-dev/2024-05-02#1023935;))

```
14:12 <achow101> #topic moderation guidelines (achow101)
14:13 <achow101> ajonas wrote some moderation guidelines as a place for us to start thinking about this topic. I've put them into a gist, if anyone has feedback: https://gist.github.com/achow101/9192ad26dc4ef08e9c899caeddc968ef
14:14 <pinheadmz> for a test, i uploaded these guidelines to GPT and instructed it to evaluate some comments with either "OK" or "needs moderation" then fed it some comments from the datacarrier PR. The results were amazing, only one false positive
14:15 <darosior> pinheadmz: hah, neat
14:15 <glozow> pinheadmz: woah cool
14:15 <pinheadmz> i already have webhooks from the repo for telegram and IRC bots, i could send all comments to the bot to at least help flag incidents
14:15 <achow101> pinheadmz: you mean you agreed with all of it's decisions except for one?
14:15 <pinheadmz> https://chat.openai.com/share/3595a095-5918-4200-91e5-97d536899e51
14:16 <pinheadmz> achow101 correct, it flagged a long comment by Murch[m] as "needs moderation" which i disagreed with
14:16 <sipa> pinheadmz: does that mean that "you" are volunteering for the role of moderator?
14:16 <pinheadmz> sipa yes
```

Surprinsingly, it's announced the guidelines have been done by a chaincode employe.
(ajonas - 14:13). Another chaincode employe ask to another contributor if we wish to be
a moderator (sipa - 14:16). This other contributor, another employe of chaincode,
immediately and non-equivocally answer yes. Few after, the second contributor

2) Second observation among the ~13 folks who have ACKed the guidelines in
date of the IRC meeting, at least there were 5 contributors who were employes
or have benefited from financial advantage from chaincode folks.

**2024**: During the year 2024, I open few issues and pull requests to point out
all the flaws and limitations of the moderation guidelines. While I've never been
formally opposed to uphold civility and courtesy on the Internet, I've never formally
agreed to the moderation guidelines in their original status, neither to who is
occupying the role of the moderators.

**October 2024**: On the lightning side, after I'm asking some clarifications
about the Lightnint BOLTs, a former chaincode employe comes with a code of conduct
in dATe of the 21th October 2024 ([link](https://github.com/lightning/bolts/pull/1207)). The Lightning BOLT process is almost 10 years
old, however it was ACKed only by 6 folks, among them one is not working on LN anymore
as of today. There were a clear refusal to have any rational discussions on the rules,
and it was arbitrarily steamrolled by abusing github permissions. We never granted
the github permsisions for that, as the lightning repository was explicitly moved
on a stakeholder-neutral repository circa 2021.

### The Direct Events leading to the Ban

**March 2025**: 

- March 4th: a pull request is open to add CheckTemplateVerify to bitcoin core ([link](https://github.com/bitcoin/bitcoin/pull/31989#issue-2895182499))
- March 5th: i comment about some technical risks due to what vulgarly is called MEV ([link](https://github.com/bitcoin/bitcoin/pull/31989#issuecomment-2702260349))
- March 5th: a chaincode employe arbitrarly flags my comment for moderation, it was a pure technical comment ([link](https://github.com/bitcoin/bitcoin/pull/31989#issuecomment-2702330203))
- March 7th: a chaincode employe open a discussion thread on the github repository ([link](https://github.com/bitcoin-core/meta/discussions/12))
- March 14th: i told a 1st time to the chaincode employe there are falsifying the dev process about consensus change ([link](https://github.com/bitcoin-core/meta/discussions/12#discussioncomment-12504759))
- March 14th: i told a 2nd time to the chaincode employe that mod rules are abusive w.r.t 1241 historical contributors to bitcoin core ([link](https://github.com/bitcoin-core/meta/discussions/12#discussioncomment-12506478))
- March 22th: i told a 3rd time to chaincode employe that mod rules are (a) illegal and (b) there are not Satoshi ([link](https://github.com/bitcoin-core/meta/discussions/12#discussioncomment-12583887))
- March 24th: i open a 1st PR to remove the mod guidelines saying it violates the rights of the 1241 contributors to bc ([link](https://github.com/bitcoin-core/meta/pull/13))
- March 25th: i open a 2nd PR, after the 1st got closed without discussion, saying it violates the rights of the 1241 contributors to bc ([link](https://github.com/bitcoin-core/meta/pull/14))
- March 26th: i open a 3rd PR to remove the mod guidelines, after the 2nd got closed, saying it violates the 1241 contributors to bc ([link](https://github.com/bitcoin-core/meta/pull/15))

This last PR stays open, because indeed the mod guidelines were steamrolled in May 2024,
with zero care for the ~1241 historical contributors to bitcoin core minus ~13 people and
the chaincode folks clearly do not have a very high level of legal sophistication.

- March 31th: i open a 1st PR to remove lightning coc ([link](https://github.com/lightning/bolts/pull/1241))
- April 5th: i open a 2nd PR to remove lightning coc ([link](https://github.com/lightning/bolts/pull/1247))
- April 6th: i open a 3rd PR to remove lightning coc ([link](https://github.com/lightning/bolts/pull/1248))

One should note the usage of LLM tooling on the last pull request on the lightning CoC. If it's for "jamming"
the discussion or whatever. There is complete absurdity yielded like "and the repository is free to adopt
governance policies as needed.".

Around April 18th: i explicitly said on the consensus cleanup draft championed by a chaincode employe, 
that a friend won't share sensitive sec info with chaincode folks that might be of technical interest (screenshot).
At the same time, a former chaincode employe make inappropriate comment ([link](https://github.com/bitcoin/bips/pull/1800#issuecomment-2797915905)),
I do ask him politely go to shut up and pointed out to the attorney letter of 2023. I made successive
comments, which are not exactly always polite but factually correct, reminding the facts laid out in
the present post ([link](https://github.com/bitcoin/bips/pull/1800#issuecomment-2817369270)) ([link](https://github.com/bitcoin/bips/pull/1800#issuecomment-2817376082)) ([link](https://github.com/bitcoin/bips/pull/1800#issuecomment-2817380434)) ([link](https://github.com/bitcoin/bips/pull/1800#issuecomment-2819571594)).

Simultaneously, I open a post on the Delving Bitcoin Forum on Friday 18th, entitled "Some problems
with current bitcoin core MODERATION.md", and this post was very polite and courteous. This post
is immediately take down. When I asked in private explanation for the rational to one of the Delving
Bitcoin maintainer, I have an answer the Monday 21 April local time from the noreply@delvingbtc.erisian.com.au
telling my account is suspended for few months. See for more "bitcoin-core-moderation-1616" in `proofs`.

In parallel, there is an issue opened by a maintainer, if the moderation guidelines apply to
the BIP repository. This was never considered so far, and as I pointed out there is no rational
to have the BIPs and the bitcoin core code software under the same Github repository ([link](https://github.com/bitcoin-core/meta/issues/16)).
The conclusion of the discussion is that BIP editors prefer to moderate the repository. There
were appointed to be editors, and nothing formal was recognized in that sense when a new batch
of BIP editors were approved in April 2024.

The 23th April, there is an issue opened by a chaincode employe again to announce my ban
from the github repository for a month ([link](https://github.com/bitcoin-core/meta/issues/17)). This does even follow their very own guidelines
as for a ban of more than 1 week, the maintainers must agree to and there has been no
publication of their PGP-signed approval of such things according to the keys listed in 
`bitcoin/contrib/verify-commits/trusted-keys`. This is once again a complete abuse of the bitcoin
core dev process by chaincode folks. The issue do not mention agreement or communications
with the maintainers and it's more likely the chaincode employe freakout...

Beyond once again " I am committed to moderating fairly", it doesn't hold objectively when
someone is actually paid for his job i.e arbitrarly banning people with the list of events
listed in this write-up.

The directory `proofs` can be read on for few OTS proofs for the events that did happen 
on the last week.

## My View of the Problem

_Disclaimer: I do no think there is a hidden agenda of a federal agency playing out here._
_According to my information, it's only pure Chaincode politics playing out here._

Zooming out, I'll just copy past Alex's Morcos own words from few years ago ([during the
block size war](https://medium.com/@morcos/no2x-bad-governance-model-97b8e521e751))


"If a few companies, or even a cluster
of companies, can effectively take control of bitcoin governance, and
force a change — that is a definitional failure of Bitcoin’s
decentralised value proposition in itself.
	— Adam Back"

"I think this is one of the least understood reasons for opposing the NYA announced hard
fork in November. The opposition is too often misinterpreted as some sort of sour grapes.
That because the opponent wasn’t leading the meeting or a participant in it, that it wasn’t
the right sort of agreement."

"The difference is not in the participants in the meeting, whether the invite list was closed
or open, or even in the technical details of the plan. The difference is in whether the resulting
product is an agreement or a proposal."

"**This strikes me as a form of bullying**. Yes those companies have influence in the ecosystem (as do
miners and as do developers), but they should not use their influence to compel a change in the rules.
Any group is welcome to propose a change, but the bar for moving forward with it is that the community
must come to consensus. This is a high and difficult bar, and rightfully so."

Those words are the wordf of Alex Morcos said in a Medium post in date of August 9 2017.

**Ask yourself why some people have to see their invitations rescind from in-person invitation-only
meetings for the so-called "moderation rules" to be "freely" adopted by the "community".**

**Ask yourself if it's normal to have 1 dude at 1 company writing the moderation rules for
all the bitcoin core contributors all over the world.**

**Ask yourself why a chaincode employe has to ignore on what say their own guidelines to do
enforcement, and if they have real confidence in the rules they have drawn themselves.**

**Ask yourself why they have to use the cheap "toxic" label to qualify the conduct of someone,
when Chaincode is completely silent when some hard facts are pointed to them in public.**

**Ask yourself if the rules would be applied with the same level of objectivity and fairness
if it was someone like Alex or Suhas had that same line of conduct than mine in the industry.**

**Ask yourself if a lot of contributors or maintainers among the youngest ones are only told a
very partial view of what it's really happening, to obtain not their approval of the mod
guidelines, but at least their silence about what is really wrong here.**

As it's said on the website of CoreDev. 

"No politics. Just code".

Since circa 2022 there has been a deliberate pattern of actions by Chaincode folks
to silence me and drive me out of bitcoin development, including being able to contribute
on bitcoin consensus changes, where neither Alex or Suhas are among the highest skilled
experts there.

So you see I'm not sure if every bitcoin core contributor in the space is holding to the same
"code. no politics" standard, and I'm opening this write-up for everyone in the industry
to make its own opinion, be iteconomic nodes, investors, media influencers, miners, protocol
developers, application devs or the plebs. 

I do apologize by advance that, we, the developers, we have to annoy you with all
those internal stories aboout moderation. At the end of the day, we're touching your money.

_As George Orwell famously said "all animals are equal but some are more equal than others"._

ariard

Block 893862
Hash 00000000000000000000ceb25ba56856d740fd10e46e7527f40dcce0032038d5

2025-04-25 04:56:12

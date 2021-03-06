---
title: The War on License Notices
description: managing uncertainty at the fringes of open licensing
tags:
- Open Source
- Licensing
---

In law, as in life, some things work without us really knowing how.  We do our best, say our prayers, and soldier on.  So it goes with notices and disclaimers in public software licenses, from old-school classics like [MIT](https://spdx.org/licenses/MIT.html) and [GPL](https://www.gnu.org/licenses/gpl-3.0.html) to state-of-the-art forms like [Blue Oak](https://blueoakcouncil.org/license/1.0.0) and [Parity](https://paritylicense.com).

If you were going to pick one open source license at random and guess two terms it would have, you'd pick "notice requirement" and "disclaimer".  Nearly all open source licenses have them.  Even though most everyone agrees that notice requirements are a big pain in the ass.  Even though lawyers can't seem to agree how disclaimers work, when they expect them to work at all.

That tends to ache hackers' brains, since they model legal rules like software.  In software, undefined behavior is a blight, a malignant infection to be isolated, excised, and avoided as first priority, lest it rot an otherwise orderly project from root to stem.  But undefined behavior is normal in law.  Lawyers create uncertainty of our own, quite intentionally, all the time.  We manage uncertainty in laws, regulations, and other people's private contract terms in most projects, including in open source software licenses.  Vagueness, ambiguity, and generality get deals done, rules approved, and bills passed, every day of the year.

Here's the notice requirement from The MIT License:

> The above copyright notice and this permission notice (including the next paragraph) shall be included in all copies or substantial portions of the Software.

The gist of this term is to require people who share the software with others to share the copyright notice and license terms for it, too.  No sharing software bits without their corresponding legal bits.

And here's MIT's disclaimer:

> ***The Software is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and noninfringement. In no event shall the authors or copyright holders be liable for any claim, damages or other liability, whether in an action of contract, tort or otherwise, arising from, out of or in connection with the Software or the use or other dealings in the Software.***

The gist of this bit is to prevent users from suing the developers for technical or other problems with the software they gave away for free.

Ominous Foreshadowing: The "next paragraph" called out explicitly in the notice requirement _is_ the disclaimer.

For more notice requirements, see clauses 1 and 2 of the [two-clause BSD License](https://spdx.org/licenses/BSD-2-Clause.html), section 4 and 5(b) of [GPL 3.0](https://www.gnu.org/licenses/gpl-3.0.html), or section 4 of [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0).  All of those forms also boast disclaimers in line with MIT's.  The [Fair Public License](https://spdx.org/licenses/Fair.html), a flawed but earnest attempt to distill permissive open source licensing down to its essence, is literally just a copyright line, a notice requirement, and a disclaimer, or at least an attempt at one.

So much for the rule.  What about the exceptions?

A number of more recent, "radical" permissive licenses, often from developers fed up with intellectual property licensing as a concept, omit any requirement to include notices of license terms with copies of the software.  The [Do What the Fuck You Want to Public License](http://www.wtfpl.net/about/) says nothing about notices. The [Zero-Clause BSD License](https://spdx.org/licenses/0BSD.html), also known as the "Toybox License" and "Free Public License", copied the BSD license and then deleted the two clauses requiring notices.  Forms that try to put work in the "public domain", such as [Creative Commons' CC0](https://creativecommons.org/publicdomain/zero/1.0/legalcode) and [The Unlicense](https://unlicense.org/), don't require notices, either.

Coders, rejoice!  Have brave license hackers finally vanquished the last legally-imposed license chore: the notice file?  Perhaps.  But at what cost?  And who's paying?

Into this fray stepped the [Blue Oak Model License](https://blueoakcouncil.org/license/1.0.0).  As I've written elsewhere, the Blue Oak license came about by happy accident.  While pulling together a [list of permissive open source licenses](https://blueoakcouncil.org/list), the council ended up with an informal spec for strong permissive license terms.  Some licenses ticked most of those boxes, but no license ticked them all.  So a new license, a "model license", was born to fill the gap, advancing the state of the art in maximally permissive, legally rigorous public software licensing.  Translating "maximally permissive, legally rigorous" from self-affirming gobbledygook to English, the Blue Oak Model License wants to give as much away as possible, with minimal hassle for users, but without doing anything lawyers consider dumb.

Turns out, that spec still compels a notice requirement:

> You must ensure that everyone who gets a copy of any part of this software from you, with or without changes, also gets the text of this license or a link to https://blueoakcouncil.org/license/1.0.0.

Blue Oak asks less here than other licenses.  There's no copyright line to fill out in the Blue Oak license, and no requirement to reproduce copyright notices in source code or special files.  You can meet the requirement to give notice by providing the license's permalink, rather than a full copy.  If you fail to do even this, you might still be saved by Blue Oak's special [forgiveness mechanic](https://blueoakcouncil.org/license/1.0.0#excuse).  But the notice chore remains.  What gives?

The disclaimer.

I'm proud of Blue Oak's, so I'll quote it:

> ***As far as the law allows, this software comes as is, without any warranty or condition, and no contributor will be liable to anyone for any damages related to this software or this license, under any kind of legal claim.***

The gist is the same as under MIT, quoted above.  No suing the developers for problems with work they gave out for free.  A pretty important term for developers!  But how does it work?

In "traditional" software licensing, where money changes hands and two sides negotiate terms, theory of operation harbors no mysteries.  The license agreement between buyer and seller counts as a "contract", or legally enforceable agreement.  Laws about contracts for sales of goods and services, most notably the [Uniform Commercial Code](https://en.wikipedia.org/wiki/Uniform_Commercial_Code) in most of the United States, set defaults for the kinds of warranties sellers make about what they sell, and what kinds of losses buyers can sue for, as money "damages".  Those laws also set out rules for reversing the defaults---"disclaiming" warranties and "excluding" damages---which explains why we see the magic phrase "as is" in nearly every disclaimer, and often long lists of kinds of warranties and damages, as well.

Under other laws, like the unpopular [Uniform Computer Information Transactions Act](https://en.wikipedia.org/wiki/Uniform_Computer_Information_Transactions_Act), or the more general laws of other countries, like Germany's, it's not legally possible to disclaim some or all warranties.  Which is why the question isn't just "How do these disclaimers work?", but "How do these disclaimers work, when they work at all?".

Even in states like California, Texas, or New York, which have the Uniform Commercial Code but didn't fall for the Uniform Computer Information Transactions Act, it's not entirely clear that the usual rules about disclaimers apply to open source license terms.  Those rules apply to "contracts".  Are open source licenses contracts?

For at least two decades, some open source licensing theorists, especially Eben Moglen and the Free Software Foundation, insisted that the GPL and similar terms were licenses _only_, and not contracts.  That's looking more and more incorrect, as we see lawsuits where copyright owners sue not just for copyright infringement---lack of a license---but also breach of contract, even when they chose GPL terms for their work.  But at least theoretically, it's a potential source of confusion, as well as some technical questions about how much you can sue for in court, and how courts will come up with the number of dollars the other side will have to pay.

Blue Oak avoids this theoretical complexity.  If the question is "license or contract?" Blue Oak answers "yes":

> In order to receive this license, you must agree to its rules. The rules of this license are both obligations under that agreement and conditions to your license. You must not do anything with this software that triggers a rule that you cannot or will not follow.

To get permission for the code, you have to "agree" to the terms, not just sit back and passively "accept" a license.  That's the "traditional" model of software licensing, from the legal point of view.  The copyright holder and the user agree to a contract.  Under that contract, the user gets a license.

But in many other ways, open source distribution ain't "traditional" at all.  The developer and their users aren't going to print out and sign the Blue Oak Model License.  Copies of the developer's software will end up all over the Internet, and people will share and use them without the developer even knowing they exist.  No money will change hands. The software will stand on its own, take it or leave it, legal terms included.

Basic contract law isn't totally dumbstruck.  There are legal rules about "unilateral contracts", without any need to communicate acceptance back to the one offering the deal.  There are rules about "implied contracts" that courts enforce in context, even if the two sides didn't say anything explicit about being held to a deal.  And there are rules about treating two sides as having made an agreement---a "quasi-contract"---even if they didn't, because one side, like the user of some software, relied on the other side's statements that doing so was alright.  All of these have come up in arguments and opinions in open source licensing cases, though I'd argue the legal picture isn't much clearer for it.

Under American law, which descends from English law, many rules come from the tradition called "equity", as distinct from the tradition called "law".  A single set of courts applies both sets of rules, law and equity, in these United States.  But in days of yore on foreign shores, law courts in England applied just legal rules, and rather strictly.  That rather indifferent, mechanical approach led to decisions that proved technically correct, but egregiously unfair or even practically absurd.

Since all law derived its power from the king, those on the receiving end of bad legal decisions would petition the king directly to save them.  These petitions came in so often that the king eventually delegated them to an officer, the chancellor, or "king's conscience", usually a churchman.  The Lords Chancellor eventually got so busy that they set up their own, parallel court system, the Courts of Chancery.  If you lost in a court of law, you could march over and make a "save me" plea in a court of equity.

Ancient legal rules tend to be specific, even formulaic.  Rules of equity read more like general guidelines or "maxims".  When we start talking about contracts---a legal concept---without some of the formulaic features of typical contracts---like formal signature---we step into the fuzzier, impressionistic, more intuitive territory of equity.

It doesn't take years of mind-warping legal education to see that disclaimers, like the disclaimers in free public licenses for software, probably shouldn't work on people who've never seen them or been told about them.  Bob finds some robotics software online.  It doesn't come with any license terms.  The software is horribly flawed.  Immediately after reboot, Bob's robot charges into the wall of his garage, overloads its servos, peaks its batteries, catches fire, and burns his house down.  When Bob's lawyer finds the developer and sues, they point to a disclaimer in their open source license.  A disclaimer Bob never heard of.

If the hard and fast rule were that you don't get any protection unless the seller promised some---"buyer beware"---Bob'd be out of luck, whether he'd seen a disclaimer or not.  But "buyer beware" isn't the rule, or at least not the only rule, under typical American law.  It may or may not be the default in any particular situation.

So how to avoid Bob's lawsuit?  Try to make sure users will get copies of your disclaimer, as a start.  How to do that?  On the legal front, make it a requirement under your license.  There's no guarantee that this will work every time, even in countries that usually allow broad disclaimers.  But we don't really expect courts to hold users to privately drafted terms they've never seen or heard about, especially if no obvious steps were taken to help make sure they would be seen.

Put short, notice seems necessary, if not sufficient.  So require notice.  If you require notice of the disclaimer, you might as well require notice of the other license terms, too.

The same logic applied to copyright notices back in the day.  It's no longer necessary, under United States or many other laws, to put a copyright notice on every published copy of your work.  It used to be, but governments got rid of that rule, especially when joining the [Berne Convention](https://en.wikipedia.org/wiki/Berne_Convention).  All the same, early forms like MIT and BSD included fill-in-the-blank copyright lines and required giving notice of both copyright line and license terms.  Some developers liked this requirement, legally necessary or not, since copyright lines could work a bit like credits for work on a film, acknowledgments for work on a book, or liner notes for work on a record.  At least for software that's distributed to users, rather than run for them as services.  Which used to seem like all popular software.

Whether for disclaimers or copyright notices, an obvious question remains: What happens if someone gets a copy of your software from someone who _didn't_ provide notice as you required?  Dana Dev releases some half-baked electric vehicle software under the Blue Oak Model License.  Sam Sharer downloads a copy from GitHub and uploads it to his favorite EV hobbyist forum, but without Dana's license terms.  Harry Hapless downloads the code from the forum and installs it in his golf cart, which careens into a brick wall as soon as he turns the key, snapping his leg.

Perhaps the court would let Dana off.  She applied a disclaimer to her work and took steps to ensure users like Harry would see it.  Perhaps the court would hold Dana responsible instead, but allow her to go after Sam to pay Harry's damages, since it was his fault Harry didn't know he was on his own, by breaching a contract to give notice.  Perhaps the court would hold Sam responsible under laws that put retailers and distributors on the hook for defective products, and deny Sam's claim against Dana, since he saw the disclaimer.  Strictly speaking, there's still a chance the court might just hold Dana responsible, full stop.  But that starts to offend some of our intuitive sense of justice, which may very well affect how courts apply equity-based rules.  Moreso than if Dana had missed the obvious chance to help make users aware of her disclaimer, by not requiring notice at all.

In sum, we could read the Blue Oak Model License as embodying a simple, this-for-that deal between developers and users.  Developers give users free permission to use and share their software.  Users give developers a free pass for any problems with that software.  Developers give up their right to sue users for intellectual property infringement.  Users give up their right to sue developers for breaking standard warranties.

"Radical" permissive licenses and public domain dedications give up the developer's side of that deal.  Users get permission, but developers don't get protection.  Since these licenses don't need notice to communicate a disclaimer, don't care about credit, and don't need to preserve copyright lines, they can do without notice requirements altogether, sparing users and distributors the chore.

Licenses without notice requirements can still have disclaimers, as [The Unlicense](https://unlicense.org/) does.  But there's no legal requirement on distributors to preserve those disclaimers.  Distributors might do it anyway.  And users might find some software, look up the developers, and find license terms with disclaimers elsewhere online.  But the developer's ability to enforce their disclaimer seems weakened.  They've failed to take an obvious step to make others aware of their terms.

That said, the Blue Oak Model License isn't any exercise in extremist lawyer paranoia, where everything goes the developer's way.  Unlike the radical anti-licenses, Blue Oak comes out _against_ getting rid of notice at the cost of risk to the developer.  But the model license also embodies a number of judgment calls with costs on the developer side.  Judgment calls that account not just for relatively well defined legal rules, but also more general principles that fill gaps in those rules.

For one, the license allows notice of the permalink for the license terms, rather than a copy of them.  In many legal circumstances, terms incorporated by reference get treated just like terms that were copied and pasted in place.  In fuzzier circumstances, like those just discussed, a court might decide that it isn't fair to hold a user to a disclaimer they had a link for, but didn't actually pull up.  Especially if legal rules require that disclaimers stand out as "conspicuous", which some laws due, hence the ALL CAPS in The MIT License or the bold, italic type in Blue Oak.  The folks drafting the Blue Oak Model License decided to allow notice-by-URL anyway, since it's so much easier for users to give a link, especially if multiple Blue Oak-licensed projects end up in one distribution.

To help bolster the notice effect of the permalink, the Blue Oak license might have required some explanation of the link, like the fact that it applies to a particular software project.  Many users do this anyway, using automated tools to spit out long lists of project names, followed by their license notices.  But requiring contextualization, especially with any particular wording, would have made a larger and more unique chore for users.  There are ways of reducing uncertainty around notice requirements, like the "magic string" approach of the [PolyForm licenses](https://polyformproject.org/licenses/noncommercial/1.0.0/#notices).  But those licenses impose more restrictive terms for use, and generally balance out more in favor of developers.  Blue Oak goes the other way.

It's fair to ask whether any of this is really worth it.  Anecdotally, warranty claims against public domain code don't seem to happen very often.  Some countries don't even allow broad disclaimers in the first place.  If it's good enough for Germany, is it good enough for the world?

The Blue Oak Model License says "no".  That the risk can be very real, even if it's not very common.  By implication, that laws prohibiting broad disclaimers, like Germany's, don't make much sense when applied to software given away for free under fixed terms, rather than licensed in the "traditional" manner, where money changes hands.  By extension, that there's something fundamental and fair about exempting developers who give their work away for free from the responsibilities imposed on those who ply their trade in private, for pay.  In the end, that open source contribution isn't just a bunch of developers waiving the rules in favor of users, but a different set of rules for a different kind of game.

I'll be sending this to other members of Blue Oak Council.  Needless to say---though I'll say it to be sure---they won't necessarily agree with what's written here.  These thoughts are mine and now.  But I hope they can bring to light some of the craft and shop knowledge of the strange, rarefied company open licensing wonks keep.

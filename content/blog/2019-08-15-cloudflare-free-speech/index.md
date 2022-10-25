---
title: "Cloudflare, free speech and the rule of law"
date: 2019-08-15
modified: 2019-08-15
draft: false
tags: ["Company Culture", "Startups", "Politics"]
summary: "Cloudflare, free speech and the rule of law. Taking advantage of 
centuries of development of democratic process is better than private, 
unaccountable censorship from the likes of Facebook."
url: cloudflare-free-speech-and-the-rule-of-law
---

Defining exactly where a particular vendor sits in the infrastructure stack is
important because this determines which legal rules apply around liability for
content. If they are a publisher, they have much more responsibility for the
content on their platform than if they are just a distributor.

As [nicely summarised on
Stratechery](https://stratechery.com/2019/a-framework-for-moderation/), any form
of editorial control (automated or otherwise) is what defines a publisher (as
per [Cubby v
CompuServe](https://law.justia.com/cases/federal/district-courts/FSupp/776/135/2340509/) (1991)
and the subsequent decision in [Stratton v
Prodigy](https://h2o.law.harvard.edu/cases/4540) (1995)). To adjust this
liability and allow firms to moderate content online, the US passed the
Communications Decency Act in 1996, section 230 of which allows for:

> any action voluntarily taken in good faith to restrict access to or
> availability of material that the provider or user considers to be obscene,
> lewd, lascivious, filthy, excessively violent, harassing, or otherwise
> objectionable, whether or not such material is constitutionally protected
>
> <cite>[47 U.S. Code § 230.Protection for private blocking and screening of offensive
> material](https://www.law.cornell.edu/uscode/text/47/230)</cite>

At the time this was passed, [the reasoning
was](https://www.economist.com/leaders/2018/09/08/should-the-tech-giants-be-liable-for-content) that
the small but growing tech industry needed the protection offered to network
providers like telecoms. Phone companies do not listen into all phone calls and
major internet backbone providers offer a neutral service to distribute packets
on the internet without filtering. As systems that purely distribute content,
should they really be held liable for how the network is used?

Things become more challenging as the network vendor becomes a content platform.

## Moving from network to content enabler

[Cloudflare](https://www.cloudflare.com/) is an internet security service that
sits in front of your website, distributing the content faster via their global
network and protecting it from threats such as denial of service attacks.

Since launching in 2009, it has grown quickly, now providing services to 19
million sites – a significant portion of the internet. [In 2018 it was
processing](https://blog.cloudflare.com/http-analytics-for-6m-requests-per-second-using-clickhouse/) over
6 million requests per second. This places it in the group of companies
providing crucial internet infrastructure like AWS and Google. It has grown from
the original DNS, CDN + DDoS protection services to offering a much wider
portfolio of infrastructure products. Does that mean it has graduated from being
merely a neutral network or does it have some greater responsibilities for the
activities it enables?

Cloudflare has historically positioned itself as neutral when it comes to the
content it serves. This has caused controversy because of the types of website
it has allowed to use its services, although it is by no means alone. Gizmodo
ran some research in July 2019 which showed almost 400 sites considered to
promote “hate” that were being hosted by major tech infrastructure companies:

> We reached out to a handful of non-profit organizations that work to monitor
> and counter hate—the Southern Poverty Law Center, the Anti-Defamation League,
> Hope Not Hate, the Canadian Anti-Hate Network, and the Counter Extremism
> Project. They each provided us a list of groups they see as being involved in
> the propagation of hate.  
> …  
> The organizations we looked at run the gamut from white supremacists,
> neo-Nazis, and chapters of the Ku Klux Klan to groups dedicated to stripping
> the rights of immigrants and LGBT people. There are also
> some [neo-Confederates](https://www.splcenter.org/fighting-hate/extremist-files/ideology/neo-confederate), [black
> nationalists](https://www.splcenter.org/fighting-hate/extremist-files/ideology/black-nationalist) and [racist
> Odinists](https://www.revealnews.org/article/an-ancient-nordic-religion-is-inspiring-white-supremacist-jihad/) in
> the mix as well. The list includes one website for a white nationalist beer
> company and a whites-only dating site.  
> …  
> [GoDaddy](https://www.godaddy.com/?sp_hp=B&) and its subsidiary [Wild West
> Domains](https://www.wildwestdomains.com/) provided services to the largest
> number of sites on our list, 130. [Cloudflare](https://cloudflare.com/), which
> provides protection against distributed denial-of-service attacks, works with
> the second largest number of sites, 56…Google provided services to 27 sites,
> Amazon works with nine, and Microsoft works with five.
>
> <cite>[The Dirty Business of Hosting Hate
> Online](https://gizmodo.com/the-dirty-business-of-hosting-hate-online-1836286885),
> Gizmodo</cite>

Cloudflare’s position has always been that they follow the law and nothing
more. [They have specifically
stated](https://www.reuters.com/article/net-us-usa-cyberwar-cloudflare/selling-flak-jackets-in-the-cyberwars-idUSBRE8BC0OB20121213) they
do not wish to be making political judgements about what content they should or
should not be serving just because they may disagree with it.

However, there are grey areas such as when they are providing services to
organisations considered to be “terrorist” groups by the US Government:

> Among Cloudflare’s millions of customers are several groups that are on the
> State Department’s list of [foreign terrorist
> organizations](https://www.state.gov/j/ct/rls/crt/2016/272238.htm), including
> al-Shabab, the Popular Front for the Liberation of Palestine, al-Quds
> Brigades, the Kurdistan Workers’ Party (PKK), al-Aqsa Martyrs Brigade and
> Hamas — as well as the Taliban, which, like the other groups, [is
> sanctioned](https://sanctionssearch.ofac.treas.gov/Details.aspx?id=263) by the
> Treasury Department’s Office of Foreign Assets Control (OFAC). These
> organizations own and operate active websites that are protected by
> Cloudflare, according to fournational security and counterextremism experts
> who reviewed the sites at HuffPost’s request.
>
> <cite>[U.S. Tech Giant Cloudflare Provides Cybersecurity For At Least 7 Terror
> Groups](https://www.huffingtonpost.co.uk/entry/cloudflare-cybersecurity-terrorist-groups_n_5c127778e4b0835fe3277f2f),
> HuffPost</cite>

Here, the law prohibits anyone from offering “material support” but what
constitutes “material” is vague:

> …the [Electronic Frontier
> Foundation](https://www.eff.org/deeplinks/2015/05/congress-must-not-authorize-more-chilling-first-amendment-material-support-laws),
> argue that “material support” can and has been abused to silence speech.
> Cloudflare’s general counsel, Doug Kramer, told Gizmodo over the phone that
> the company works closely with the U.S. government to ensure that it meets all
> of its legal obligations. He said that it is “proactive to screen for
> sanctioned groups and reactive to respond when its made aware of a sanctioned
> group” to which it may be providing services.
>
> <cite>[Cloudflare Under Fire for Allegedly Providing DDoS Protection for Terrorist
> Websites](https://gizmodo.com/cloudflare-under-fire-for-allegedly-providing-ddos-prot-1831107649),
> Gizmodo</cite>

Whilst the groups that Cloudflare have been serving are clearly producing
content that many find horrible (including myself), the material is not illegal
in the US.

The First Amendment of the US Constitution prevents the US government from
placing restrictions on freedom of speech. This does not apply to commercial
entities and Cloudflare’s own terms of service allow them to terminate accounts
for whatever reason they like. But they have decided to use the legal minimum.

I don’t like some of the outcomes of what this allows, but it does mean
certainty and transparency. The alternative is worse.

## The US government is offering no alternative

The technical design of the internet is decentralised. A large number of
networks run by many separate entities all come together to provide a neutral
service that allows everyone to communicate without rules. This has allowed
amazing innovation but has also created huge societal problems as we deal with
the fact that no single state or organisation has oversight.

One of the biggest challenges is that whilst the underlying architecture of the
internet is decentralised, most of the services built on top of it are
centralised. For example, there are only 2 major mobile platforms – iOS and
Android; only two major desktop operating systems – macOS and Windows; only one
major search engine – Google; only a few major social network operators –
Facebook (owning Instagram and WhatsApp), Twitter, Snapchat.

The network is decentralised and neutral, so the distinction of distributor vs
publisher makes sense. But when content is available on only a few platforms,
decentralised neutrality disappears. Cloudflare is more than a neutral
distributor because of the protection and CDN services it offers, but it isn’t a
publisher because it is not hosting or editing the content. It enables content
to exist but does nothing to edit, review or promote that content. In contrast,
Facebook and Google (especially YouTube) actively promote the content they host
to drive engagement with their ads.

In this middle zone, Cloudflare has decided to take the approach of a
distributor network. The rules they apply are whatever US law says. They have
co-opted the machinery of the US state – the government, legislature and
judiciary – so they don’t need to make a decision themselves. If a the
legislature or courts system decide to tighten up the definition of “material
support”, we would expect Cloudflare’s position to change to apply those new
rules too.

Whilst this has resulted in some horrific organisations having an easier job
remaining accessible, the alternative is the arbitrary and opaque rulings of the
content moderation operations of the major platforms like Facebook. Instead,
Cloudflare are outsourcing their decisions to the democratically accountable US
rule of law. If the constitution prevents the government from providing more
clarity, then so be it. This contrasts with Facebook and Google who are defining
their own rules in private, with no debate and no accountability.

> Policing content is a problem that has been solved in the past through the
> development of Western legal systems and the rule of law. The separate powers
> of the state – government, judiciary and legislature – counter-balance each
> other with various checks and stages to allow for change. It’s not perfect,
> but it has had hundreds of years of production deployment and new version
> releases!
>
> What has changed is the scale. And the fact that governments are delegating
> the responsibility of the implementation to a small number of massive, private
> firms.
>
> <cite>[Leaving the policing of the internet up to Google and
> Facebook](https://davidmytton.blog/leaving-the-policing-of-the-internet-up-to-google-and-facebook/),
> David Mytton</cite>

We are seeing two approaches:

- **Cloudflare**: Applying a legal minimum, but in doing so providing
  consistency, clarity and transparency. If you don’t like it then you have a
  route through the legal system and/or legislature to get the law changed,
  assuming Cloudflare adapt their approach to any changes in the law.
- **Facebook/Google**: [Adding their own
  layer](https://www.economist.com/business/2018/09/08/how-social-media-platforms-dispense-justice) on
  top of the legal minimum. We are only aware of what they are doing through
  leaks of operating documentation and there is no route to appeal or even
  review of what the current rules are.

Indeed, this is how Cloudflare have described their approach:

> We get labeled as being free speech absolutists, but I think that has
> absolutely nothing to do with this case. There is a different area of the law
> that matters: in the U.S. it is the idea of due process, the Aristotelian idea
> is that of the rule of law. Those principles are set down in order to give
> governments legitimacy: transparency, consistency, accountability…if you go to
> Germany and say “The First Amendment” everyone rolls their eyes, but if you
> talk about the rule of law, everyone agrees with you…
>
> It felt like people were acknowledging that the deeper you were in the stack
> the more problematic it was [to take down content], because you couldn’t be
> transparent, because you couldn’t be judged as to whether you’re consistent or
> not, because you weren’t fundamentally accountable. It became really difficult
> to make that determination.
>
> <cite>[8chan and El Paso, Cloudflare Drops 8chan, An Interview with Cloudflare CEO
> Matthew
> Prince](https://stratechery.com/2019/8chan-and-el-paso-cloudflare-drops-8chan-an-interview-with-cloudflare-ceo-matthew-prince/),
> Stratechery</cite>

## Moving away from the rule of law?

Things changed following the recent mass shooting incidents in the US
when [Cloudflare decided to terminate the service of one of its
customers](https://new.blog.cloudflare.com/terminating-service-for-8chan/),
8Chan:

> The mass shootings in El Paso, Texas and Dayton, Ohio are horrific tragedies.
> In the case of the El Paso shooting, the suspected terrorist gunman appears to
> have been inspired by the forum website known as 8chan. Based on evidence
> we’ve seen, it appears that he posted a screed to the site immediately before
> beginning his terrifying attack on the El Paso Walmart killing 20 people.  
> …  
> 8chan is among the more than 19 million Internet properties that use
> Cloudflare’s service. We just sent notice that we are terminating 8chan as a
> customer effective at midnight tonight Pacific Time. The rationale is simple:
> they have proven themselves to be lawless and that lawlessness has caused
> multiple tragic deaths. Even if 8chan may not have violated the letter of the
> law in refusing to moderate their hate-filled community, they have created an
> environment that revels in violating its spirit.
>
> <cite>[Terminating Service for
> 8Chan](https://new.blog.cloudflare.com/terminating-service-for-8chan/),
> Cloudflare</cite>

This is only the second time Cloudflare has terminated service for a customer,
having done so with The Daily Stormer in 2017:

> Our terms of service reserve the right for us to terminate users of our
> network at our sole discretion. The tipping point for us making this decision
> was that the team behind Daily Stormer made the claim that we were secretly
> supporters of their ideology.
>
> Our team has been thorough and have had thoughtful discussions for years about
> what the right policy was on censoring. Like a lot of people, we’ve felt angry
> at these hateful people for a long time but we have followed the law and
> remained content neutral as a network. We could not remain neutral after these
> claims of secret support by Cloudflare.
>
> <cite>[Why We Terminated Daily
> Stormer](https://blog.cloudflare.com/why-we-terminated-daily-stormer/),
> Cloudflare</cite>

Cloudflare have clearly developed their thinking since terminating The Daily
Stormer. In that instance, their reputation was at stake and they could not
tolerate the claims of support. One could argue that this is libel and so
protection under the First Amendment could be forfeited. This is debatable. The
8chan decision is much easier to understand:

> There is a flaw in the system which is that this all works so long as the end
> platform is responsible. But if the platform itself has been designed from the
> beginning to be lawless, to not respect the rule of law, to not respect abuse
> complaints and, in the case of 8chan, actually take an abuse complaint as an
> opportunity to threaten and harass whoever was sending it, the question
> becomes, “Who else then has an obligation to deal with it”?
>
> If you are on Twitter right now all of the 8chan supporters are saying “Why
> don’t you cut off Facebook or Twitter because there are horrible things that
> get posted to them?” That’s true, there are horrible things that get posted to
> them. The difference is that those aren’t lawless platforms. They have teams
> and they have procedures and they take these things seriously, and they’re
> trying to create a community that respects the rule of law. If you don’t have
> that, then you do fall into a different bucket. That was the rationale that we
> came to.
>
> <cite>[8chan and El Paso, Cloudflare Drops 8chan, An Interview with Cloudflare CEO
> Matthew
> Prince](https://stratechery.com/2019/8chan-and-el-paso-cloudflare-drops-8chan-an-interview-with-cloudflare-ceo-matthew-prince/)**_,
> Stratechery_**</cite>

Put simply, Cloudflare are saying: if the platform we provide service to applies
the rule of law, we will too. If not, we may take action.

I find this to be a well considered elaboration. It continues to be clear what
is and is not allowed, and it removes some of the risk of Cloudflare making
political or ideological decisions.

Instead of inventing their own pseudo-legal system with rules and guidelines
based on the values of the company which happens to be founded in a Western
democracy, Cloudflare are able to take advantage of the public system of law. If
the values of that system change, we would expect Cloudflare to adapt their
approach too. But it will be in the knowledge that such change has been brought
about by proper democratic process. That is the rule of law.

## Eroding free speech

Speech is different from action. This is why they are legislated differently.
Talking about killing is not the same as the action of killing. Things start to
blur as you get closer to the action
e.g. [conspiracy](https://www.cps.gov.uk/legal-guidance/inchoate-offences#_Toc533156583),
but there is still a distinction.

In the UK, section 4 of the Public Order Act 1986 creates an offence if a person
“uses threatening, abusive or insulting words or behaviour, or disorderly
behaviour” with “intent to cause a person harassment, alarm or distress”. This
causes problems of interpretation because what is “insulting” for one person
could be completely benign for another.

The Human Rights Act incorporates a right to freedom of expression but that is
limited in such a broad way that it essentially allows the government to
legislate how it wishes. You can say whatever you like so long as it is not
prohibited. This might seem broad but there are many restrictions.

Freedom of speech is defined as an absolute right in the US First Amendment
because it is so tricky to determine what exceptions should be made. [We can see
this with how difficult a job Facebook are finding
it](https://www.theguardian.com/news/2017/may/21/revealed-facebook-internal-rulebook-sex-terrorism-violence) to
moderate content on their platforms.

Distinguishing between action and speech is important:

> A website is speech. It is not a bomb. There is no imminent danger it creates
> and no provider has an affirmative obligation to monitor and make
> determinations about the theoretically harmful nature of speech a site may
> contain.
>
> <cite>[Cloudflare and Free
> Speech](https://blog.cloudflare.com/cloudflare-and-free-speech/)</cite>

But this is not satisfactory when speech is the first step towards action.
“Incitement” used to be a common law offence in England & Wales which used to
make it illegal if you:

> incite another to do or cause to be done an act or acts which, if done, will
> involve the commission of an offence or offences by the other
>
> <cite>[Inchoate Offences –
> Incitement](https://www.cps.gov.uk/legal-guidance/inchoate-offences#_Toc533156577),
> CPS</cite>

In many cases, the law has become more precise in how it limits free speech.
This offence of incitement was abolished in Section 59 of the Serious Crime Act
2007, leaving such statutory offences [as in the Misuse of Drugs Act
1971](https://www.legislation.gov.uk/ukpga/1971/38/section/19). However, [a lot
of things are still
prohibited](https://en.wikipedia.org/wiki/Censorship_in_the_United_Kingdom) resulting
in some absurd situations:

> Section 127 of the Communications Act 2003 makes it an offence to send a
> message by means of a public electronic communications network which is
> grossly offensive, or of an indecent, obscene or menacing character. This
> offence is incredibly broad and has been used to address jovial, albeit
> misjudged communications – it carries huge implications for freedom of
> expression especially now that social media is so widely used. Section 127 has
> been used to prosecute a young man who tweeted his frustration about being
> unable to see his girlfriend due to airport closure. His tweets, which were
> made without intent to carry out their content or incite others to do so,
> resulted in his conviction for being a menace under the Act – thankfully that
> conviction has now been overturned
>
> <cite>[Speech
> offences](https://www.libertyhumanrights.org.uk/human-rights/free-speech-and-protest/speech-offences),
> Liberty</cite>

The US constitution is absolute in its protection of free speech so there is no
middle ground. This why we have the different positions being adopted by
Cloudflare on the one hand and Facebook, YouTube, etc on the other. Since the US
government is unable to facilitate a debate using democratic systems, there is a
wide gap without regulation. This leaves it open to political pressure,
something that has become a major problem on university campuses:

> It would be one thing if the students were polled and a majority said they
> wanted the name changed, or some other process was used. At least the
> university could say that it was making decisions based on some objective
> democratic process, and wasn’t just being pushed around. But this is not what
> happened. No polls were taken. There was no authoritative process. The school
> said no for a few months, then caved. If the school were actually confident in
> its position to resist, it could have easily pushed back on the protests.
> Instead, it folded on demands from a small number of students willing to make
> noise.
>
> <cite>[The Real Problem At Yale Is Not Free
> Speech](https://palladiummag.com/2019/08/05/the-real-problem-at-yale-is-not-free-speech/),
> Palladium</cite>

Whether it takes the form of “no platforming” or political activist pressure on
companies to deny service to customers they dislike, it’s an attack on free
speech.

> Freedom is rarely killed off by people chanting “Down with Freedom!” It is
> killed off by people claiming that the greater good/the general will/the
> community/the proletariat requires “examination of the parameters” (or some
> such cant phrase) of individual liberty. If the criterion for censorship is
> that nobody’s feelings can be hurt, we are finished as a free society.
>
> <cite>[Trump slips and slides; the real US tyrants
> strike](http://www.niallferguson.com/journalism/politics/trump-slips-and-slides-the-real-us-tyrants-strike),
> Niall Ferguson</cite>

The legislative process is being bypassed because of the aspects that make it
work so well – it is slow and deliberate. Or in the case of the US constitution,
has very high barriers to change. This is by design – it doesn’t just allow a
single viewpoint from a minority to force change. The downside is that you have
to accept the existence of views that you do not agree with.

> “If you think of the 10 companies that have the infrastructure to really
> survive on the crazy dangerous internet that is out there, a huge percentage
> of them are advertising-driven companies,” said Prince. “They will by their
> very nature have a much more filtered, cleaned up version of the internet
> because that is where their economic incentives are.”
>
> The overwhelming dominance of cyberspace by those handful of companies means
> that the battle over speech that is protected by the first amendment, rather
> than corporate terms of service, will be relegated to the remaining, truly
> public spaces in the real world, such as the public university campuses that
> have become the forum of choice for rightwing provocateurs like internet troll
> Milo Yiannopoulos and white nationalist Richard Spencer.
>
> <cite>[The far right is losing its ability to speak freely online. Should the left
> defend
> it?](https://www.theguardian.com/technology/2017/aug/28/daily-stormer-alt-right-cloudflare-breitbart) The
> Guardian</cite>

The likes of the Southern Poverty Law Center, the Anti-Defamation League, Hope
Not Hate, the Canadian Anti-Hate Network, and the Counter Extremism Project
might seem to be doing some good work in helping create the list Gizmodo used
for their research quoted above but they are still unaccountable organisations.

Regardless of which “side” the definitions come from, it is the unaccountable,
un-appealable arbitrary decisions that place campus protestors in the same
category as Facebook and Google. At least the definition of “insulting” in the
Public Order Act offences above are determined through a legal process. [It’s a
problem when one world view turns into the basis for
censorship](https://www.bostonglobe.com/opinion/2017/08/21/there-more-than-one-side-story-there-more-than-one-side-story-worms-turn-trump-there-are-three-sides-story/TMgaLJgXpWydeLi05chWVM/story.html).

## Which rule of law?

It just so happens that all the major tech companies have been founded in a
Western democracy with liberal values that I agree with (having been brought up
in a similar society), so I have no problem with most of the rules they create.
It might have been a different story if the major internet platforms had ended
up deriving their values from more authoritarian or less-liberal societies. What
would this have looked like if Facebook had been a Chinese organisation
instead? [We only need to look at the censorship within China to get an
idea](https://en.wikipedia.org/wiki/Internet_censorship_in_China).

Although it has many problems, the US is still a modern, liberal democracy where
the rule of law applies and freedom (of all types) is a core part of the
constitution. Cloudflare are based in the US so they have a well developed
framework from which to start with. The challenge comes when operating in
countries with completely different approaches to the same issue.

Companies have to abide by the rules in the countries they operate otherwise
they face retaliation. As noted in the Cloudflare interview:

> I think it’s hard. I don’t think we have a perfect answer. We don’t have
> people in every country around the world, but we do have equipment in 80
> countries I think today. We operate in a lot of places and we increasingly
> have people in a lot of places. We have a team that’s now based in China. We
> have offices all around the world. It’s one thing if your servers get seized.
> It’s totally another thing when one of your employees gets thrown in jail. You
> have to think about those consequences as you’re thinking about how you
> operate around the world.
>
> <cite>[8chan and El Paso, Cloudflare Drops 8chan, An Interview with Cloudflare CEO
> Matthew
> Prince](https://stratechery.com/2019/8chan-and-el-paso-cloudflare-drops-8chan-an-interview-with-cloudflare-ceo-matthew-prince/)**_,
> Stratechery_**</cite>

Cloudflare are approaching this by minimising the amount of personal information
their systems store, so there is nothing for them to turn over from a government
request. But when they do get requests to take down content, they can simply
apply the policy of complying only with due legal process:

> We regularly get requests from governments that say, “This particular thing is
> causing harm and they’re not responding to us, take them down.” For example,
> there’s an LGBT support group that operates in the Middle East, and a lot of
> the Middle Eastern governments really hate them and say they are corrupting
> the children of their particular region.
>
> <cite>[8chan and El Paso, Cloudflare Drops 8chan, An Interview with Cloudflare CEO
> Matthew
> Prince](https://stratechery.com/2019/8chan-and-el-paso-cloudflare-drops-8chan-an-interview-with-cloudflare-ceo-matthew-prince/)**_,
> Stratechery_**</cite>

If you start developing your own set of rules of acceptable content like
Facebook and Google have done, that has to be localised in every jurisdiction
you operate in. It is much easier to apply the rule of law of each country,
because the law making process has already been defined. A court order is
distinct from the government requesting a site be terminated:

> Cloudflare abides by all applicable laws in the countries in which we operate
> and we firmly support the due process of law. If we were to receive a valid
> court order that compelled us to not provide service to a customer then we
> would comply with that court order.
>
> <cite>[Cloudflare and Free
> Speech](https://blog.cloudflare.com/cloudflare-and-free-speech/)</cite>

Other companies either choose not to operate in those jurisdictions e.g. Google
withdrawing from China ([although they are now trying to re-enter with filtered
search results](https://www.techinasia.com/history-of-google-in-china)) or
comply with the local requirements e.g. [Apple hosting Chinese citizen’s iCloud
content in Chinese controlled
facilities](https://www.theregister.co.uk/2018/01/11/icloud_china_goes_to_china/).

Commercial entities always have a choice about which countries they operate in.
If the people in those organisations do not agree with the laws of the land then
they should not operate there in the first place. Some people will take an
absolutist view of this, others will be more pragmatic if they think the
benefits outweigh the disadvantages.

Sometimes there are even specific requests to keep such sites online so they can
be tracked rather than have them disappear into the darker areas of the
internet:

> Prince [Cloudflare’s CEO] had argued that keeping “bad” sites within
> Cloudflare’s network means that the company is able to help monitor activity
> and flag illegal content to law enforcement. While he would not comment on
> specifics, he said that Cloudflare receives “regular requests” from law
> enforcement not to ban certain sites.
>
> <cite>[8chan: the far-right website linked to the rise in hate
> crimes](https://www.theguardian.com/technology/2019/aug/04/mass-shootings-el-paso-texas-dayton-ohio-8chan-far-right-website),
> The Guardian</cite>

We have yet to find a better method of deciding what is acceptable in society
than a deliberative legislative process backed by democratic accountability. It
is dangerous to rely on definitions of “hate” or what is “acceptable” that are
not set by this process because they cannot be subject to a sufficient level of
scrutiny and debate.

The scale that internet companies now operate at means they are having to deal
with problems that have mostly been solved by society over hundreds of years.
Our democratic institutions are imperfect but do the job best. But instead of
the approach developing in public, private companies are deciding policy,
sometimes at the direction of a single person (the CEO).

Each country has its own approach. This worked when activity was contained
within borders, but the internet changes all that. China has the most developed
system with the Great Firewall – the internet inside China is essentially its
own entity, entirely separate from the rest of the world. Will we see that
happen in other countries too?

> …if a country like Germany says that a particular site is a Nazi-promoting
> site, that content is illegal in Germany, and we can’t do anything that
> thwarts Germany’s ability to enforce that law. And increasingly, especially as
> more and more of the connection to websites becomes encrypted, more and more
> of those requirements are going to fall to us. I think that if Germany sets
> policy inside of Germany and if that policy doesn’t spill over beyond its
> borders, and if there’s transparency to it, so that if you try to access one
> of these sites and it says “You can’t get this because” and there is a copy of
> the court order, that’s not the Internet that some of us have all imagined,
> which is one network all over the world, but it’s probably the Internet that
> is able to survive and thrive over the long-term.
>
> <cite>[8chan and El Paso, Cloudflare Drops 8chan, An Interview with Cloudflare CEO
> Matthew
> Prince](https://stratechery.com/2019/8chan-and-el-paso-cloudflare-drops-8chan-an-interview-with-cloudflare-ceo-matthew-prince/)**_,
> Stratechery_**</cite>

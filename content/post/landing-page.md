---
title: "Landing Page"
date: 2018-03-09T16:24:01-05:00
draft: true
---

This is going to be a short post, as there's not a *whole* lot that
you can mess up with a landing page. But there's a few things that
definitely could be improved. Let's open the page:

![Not the worst design I've seen](/img/landing-page/albert-landing.png)

Well that's not so bad. I've certainly seen worse. However, let's take
a look at the url.

![Oh](/img/landing-page/albert-url.png)

Um, why does it say `albert_index.html`? We're on the Albert website,
we don't need to be told that we're at the **Albert** index. I
know, that's really arbitrary. But it's the little things. I'd expect
a name like `albert_index.html` from a beginner developer or maybe a
student. Not a professional.

Second thing, there's no HTTPS. Now, right about now, most people who
are familiar with HTTPS would say "why would you need HTTPS? This
isn't a login page". And yes, this is not a login page. But, this
links to the login page. In fact, the login page has a particularly
nasty url:
https://shibboleth.nyu.edu/idp/profile/SAML2/Redirect/SSO?execution=e1s1
So basically, this is the only way to get to the URL. Which means that
theoretically, someone could execute a man in the middle attack,
replacing the link to the login page with a link to their own page,
let's say https://shibbolethnyu.com. Heck, this page could have HTTPS,
a signed certificate and everything. It just wouldn't be NYU's
site. If you want an excellent explanation of this attack, check out
[Troy Hunt's
blog](https://www.troyhunt.com/im-sorry-you-feel-this-way-natwest-but-https-on-your-landing-page-is-important/). And
really, HTTPS is not hard to get. This blog has HTTPS, courtesy of
Amazon's Certificate Manager, but you can also get it from Let's
Encrypt for 100% free.

Moving on, let's go to the login page.

![A rather familiar sight](/img/landing-page/albert-login.png)

Anybody who's ever logged into a NYU site has probably seen this. Now,
show of hands here, how many people have actually read the little grey
text on the side? I mean, this part:

![The greatest security ever](/img/landing-page/albert-grey-text.png)

I don't know about you, but until I had to write this blog, I had
never read this text. Anyways, let's talk about the second part. Oh
look at that! The attack that I discussed before would clearly have
been foiled by this countermeasure. Obviously people would read this
and realize that they in fact not at
https://shibboleth.nyu.edu. Except for the part where that's totally
wrong. First of all, the odds of someone reading this and actually
figuring out they're at the wrong link are astronomically
small. Second, you could just change the text.

![Welcome to Zombocom](/img/landing-page/albert-zombo.png)

Yeah...this is the digital equivalent of:

![NYU security in a gist](/img/landing-page/simpsons-sign.jpg)

Final thing, why are the links red? If you've ever been to Wikipedia,
you've seen that red links signify that they are dead.

![If you haven't been to Wikipedia I don't know what to tell
 you](/img/landing-page/wikipedia-red-link.png)

So why would NYU break that convention? Oh sure, some designer
probably decided it "fit NYU's brand better" to use these pinkish red
links. But honestly, I find this a lot more sensible:

![Blue is best](/img/landing-page/albert-blue-link.png)

Alright, let's move on to every NYU student's favorite part of logging
in: Multi Factor Authentication or MFA!

![MFA FTW](/img/landing-page/albert-mfa.png)

To be quite honest, I'm not going to argue with NYU's decision to
implement MFA. I personally use MFA, or 2 Factor Authentication as
it's often called, on most of my accounts. However, I do think that
NYU did not implement it very well. Namely, the decision to require
MFA *every* *single* day is pretty ridiculous. The point of MFA is
that if an attacker somehow gets your password, they cannot log in to
your account on *their* computer, and in fact you get alerted that
your password is compromised. Therefore, you should be able to log in,
use MFA **once** and then have it remember your computer for some time
period, maybe a month. Now, the argument then is "well what if the
attacker gets access to that computer?" Frankly, if an attacker were
to gain physical access to your computer and get your password, you're
already screwed.

This wraps up the landing and login page. So far nothing *that* bad
has happened. You're probably thinking that maybe I'm wrong and Albert
really is great. Well stay tuned. Shit's about to go down.
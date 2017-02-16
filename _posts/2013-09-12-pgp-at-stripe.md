---
layout: newpost
title: PGP at Stripe?
---

A rekindled interest in PGP (due in part to recent revelations about the NSA) led me to perusing public keyservers for people I know. After clicking around a bit, I found that there is a reasonably large number of [people](http://pgp.surfnet.nl:11371/pks/lookup?op=vindex&search=stripe.com) who share the folowing characteristics:

* They all have stripe.com email addresses (implying that they work at [Stripe](https://stripe.com)).
* Many of them have signed each other's keys, forming a tight web-of-trust.
* Many of them are signed by [Stripe (CA-ish) &lt;all@stripe.com&gt;](http://pgp.surfnet.nl:11371/pks/lookup?op=vindex&fingerprint=on&search=0x35788230538E54D7)
* Many of them are signed by [Stripe Deploy Key &lt;deploy@stripe.com&gt;](http://pgp.surfnet.nl:11371/pks/lookup?op=vindex&fingerprint=on&search=0x4CFCE381530BF7C9)

So what can we (the non-Stripe-employee public) infer from this? Clearly they care about [security](https://stripe.com/help/security) at Stripe.

Here are a few theories of mine:

1. __Stripe uses PGP for internal communications.__ It would make sense, given the level of security that must be required at Stripe. I'm only slightly familiar with PCI requirements, but it would make sense to go even further with security this way. Signing everyone with a "CA-ish" isn't a technique I've seen before, but isn't that farfetched. It provides a decent mechanism for saying "Yes, that PGP key belongs to a Stripe employee".
2. __Stripe uses PGP as an authenticator for deployments.__ When deploying new code, it's necessary to verify that the person pushing the code is authorized to do so. Normally this is done with ssh keys and user accounts on a deploy machine, but perhaps Stripe has a more sophisticated system using PGP.

Another thing to note is that not all Stripe employees are represented here. Maybe it's only techincal/engineering employees?

It would be cool to hear about how Stripe is using PGP for either of these purposes, and why the used public keyservers rather than having their own internal system. Anyone have any insight on this?

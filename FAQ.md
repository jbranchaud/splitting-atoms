# Frequently Asked Questions

An extension to the [official FAQ](https://atom.io/faq).

## How can I get an invite to the Atom beta?

There are a few ways to get an invite.

 - Invites can be requested on [http://www.atom.io](atom.io) by entering your email address. However, it may take some time to receive your invite
 - The first users get 3 invites that they can give to friends. So ask friends with invites for one.
 - Hang out on Twitter, IRC, or other social networks. Many people are willing to give out invites.

## What is Atom's IRC chanel?

Atom: ##atom

Invites: ##atom-invitations

## Will Atom core be open-sourced?

The [official Atom FAQ](https://atom.io/faq) says,

> We have not finalized licensing on Atom's core (nucleus?),
> but we're aiming for a common ground between fully-closed and fully-open.

And then goes on to assure that any non-core packages that are developed by
GitHub will be released under the MIT license.

There is some earlier discussion around this question from the
[Atom discourse page](http://discuss.atom.io/t/why-is-atom-closed-source/82)
in which Mojombo (or Tom if you prefer) responds:

> Atom won't be closed source, but it won't be open source either. It will be
> somewhere inbetween, making it easy for us to charge for Atom while still
> making the source available under a restrictive license so you can see how
> everything works. We haven't finalized exactly how this will work yet.
> We will have full details ready for the official launch.

In response to a follow-up question, Mojombo goes on to affirm that,
[yes](http://discuss.atom.io/t/why-is-atom-closed-source/82/13),
anyone will be able to submit pull requests to Atom core.

## What will the price of Atom be?

Atom will be competitively priced compared to similar editors, which typically range between $30 and $100.

[Source](https://atom.io/faq), [original discussion](http://discuss.atom.io/t/any-idea-of-atoms-price/40)

## What is the technology behind Atom?

See [TechStack.md](TechStack.md)

## When can we expect a Linux and Windows client?

Not any time soon. The Atom team is focusing on fixing bugs and having a Mac-only beta.

[Source](http://discuss.atom.io/t/timeline-on-windows-and-linux-betas/66/50)

## Why CoffeeScript?

Using CoffeeScript and CSON is a matter of preference and readability as well as compatibility with EC6.

[See the discussion](http://discuss.atom.io/t/why-coffeescript/131)

## Is CoffeeScript required for developing plugins?

JavaScript and JSON can be used in Atom packages, there is no requirement to write a single line of CoffeeScript or CSON to make an Atom package.

In Atom any `.coffee`/`.cson`/`.less` files can always be `.js`/`.json`/`.css` files instead.

[Source](http://discuss.atom.io/t/is-coffeescript-required-for-developing-plug-ins/65/4)

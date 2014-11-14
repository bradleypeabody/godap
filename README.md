godap
=====

Demo/skeleton of minimalistic LDAP serving in Go

What is this thing?
-------------------

This is the beginnings of LDAP serving functionality written in Go.  It is not intended
to be or become a full LDAP server, it's just minimal bind and simplistic search functionality.
It aims to be enough to implement authentication-related LDAP services for use with Apache
httpd or anything else that supports LDAP auth.

Theoretically more could be built out to approach the functionality of
a full LDAP server. I don't have time for that stuff.

Why was this made?
------------------

Because the road to hell is paved with good intentions.

The short version of the story goes like this:
I hate LDAP.  I used to love it.  But I loved it for all the wrong reasons.
LDAP is supported as an authentication solution by many different pieces of
software.  Aside from it's de jure standard status, it's wide deployment
cements it as a de facto standard as well.

However, just because it is a standard doesn't mean it is a great idea.

I'll admit that given it's age LDAP has had a good run.  I'm sure it's
authors carefully considered how to construct the protocol and chose
ASN.1 and it's encoding with all of wellest of well meaning intentions.

The trouble is that with today's Internet, LDAP is just a pain in the ass.
You can't call it from your browser.  It's not human readable or easy
to debug.  Tooling is often arcane and confusing.  It's way more complicated
than what is needed for most simple authentication-only uses.

Likely owing to the complexity of the protocol, there seems to be virtually
no easy to use library to implement the server side of the LDAP protocol
that isn't tied in with some complete directory server system; and certainly
not in a language as easy to "make it work" as Go.

So this means that if you are a web developer and you have a database table
with usernames and (hopefully properly hashed) passwords in it, and you
have a third party application that supports LDAP authentication, you
can't easily use your own user data source and just make it "speak LDAP"
to this other application.

Well, this project provides the basic guts to make that work.
Have a look at the test file for an example of what to do.

In a way, with this project I embrace LDAP.  In the sense that a wrestler
embraces the neck of his opponent to form a headlock, and the unruly
brute is muscled into submission.

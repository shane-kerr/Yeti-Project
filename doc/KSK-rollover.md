Introduction
============
This document describes the method used to roll the KSK for Yeti.

Description of the Yeti root KSK 
================================
The Yeti root KSK uses the RSA/SHA-256 algorithm with a 2048 bit key,
the same as the IANA root KSK. It is generated on software, and stored
on systems secured with similar security to enterprise computing
resources; no HSM is used, and no documented procedures exist for
access or updating the KSK.

The Yeti Root KSK Rollover Procedure
====================================
The Yeti root KSK rollover uses the KSK Double-DS rollover as
described in RFC 6787, although without publishing the DS in the
parent (since the root has no parent):

https://tools.ietf.org/html/rfc6781#section-4.1.2

It also follows the timings described in RFC 5011, to allow resolvers
to update their trust anchors.

https://tools.ietf.org/html/rfc5011

During a key rollover, the approach is:

1. Generate a new KSK. A copy is delivered to all distribution
   masters, who add this to the Yeti root zone.

2. Wait 30 days.

3. Set the "revoked" flag on the old KSK at each distribution master.
   Replace the old KSK in the Yeti root zone with this version. Sign
   ZSK with the old and the new KSK.

4. Wait 30 days.

5. Remove the old KSK at each distribution master.

The Yeti KSK rollover communication plan is followed.

Discussion
==========
There are several possible issues with this plan.

The proposed ICANN KSK rollover plan goes to great lengths to
plan the IANA root KSK rollover in a way that minimizes the number of
rollovers that happen at one time - both KSK and ZSK. There is a lot
of concern about the impact on resolvers if the packet size is too
large.

The Yeti rollover plan is more straightforward, and may indeed
encounter some issues with packet size. However, the Yeti servers
already have answers that result in fragmentation, so this is not
considered a great concern.

In a future KSK rollover, Yeti can use the ICANN KSK rollover plan,
and document the differences between the more complicated ICANN
proposal and a simple KSK Double-DS rollover.

Thanks to 龚道彪 (Kevin) at BII for the initial documentation of the
process.


Introduction
============
This document describes the communication plan we use when the Yeti
root KSK is rolled.

Since Yeti is an experimental network, we do not need to be very
cautious, however it is still useful to make sure that we do things in
a clear way for all participants.

Rollover Summary
================
The Yeti KSK rollover is not yet documented on the Yeti repository.
When this is done, this communication plan will link to that document.

The basic approach is from RFC 6781:

1. Generate a new KSK
2. Publish the new KSK, signing with old KSK only
3. Wait a bit
4. Publish the old KSK with revocation bit, signing with both old KSK
   and new KSK
5. Wait a bit
6. Remove the old KSK with revocation bit, signing with new KSK only
7. Champagne

Note that this is not the same as the proposed IANA root KSK rollover.
The ICANN team is very concerned about packet size, so making the
process a bit more complex to minimize number of signatures needed at
any time. Yeti should run an experiment rolling the key using the IANA
approach.

Communications Plan
===================

1. Maintain a web page with all past and present KSK, including the
   dates when they were active. Include dates of planned future KSK
   rollovers. Also include a history of changes to the web page
   itself.

2. Announce any changes to the web page to the yeti-discuss list.

3. During a roll, announce the following changes to the yeti-discuss
   and yeti-operators mailing lists. Also put them in a visible place
   on the front page of http://yeti-dns.org

   1. 14 days before a KSK roll starts

   2. 1 day before publishing the new key

   3. Immediately after the new key is published

   4. 1 day before revoking the old key
   
   5. Immediately after the old key is revoked

   6. 1 day before removing the old key

   7. Immediately after the old key is removed

4. BII staff will be monitoring the roll and be available during the
   process. Any issues should be mailed to the yeti-discuss
   (preferred) or yeti-operators (for issues only appropriate for
   operators) list.

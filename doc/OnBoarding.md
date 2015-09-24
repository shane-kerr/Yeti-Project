# OnBoarding document for Yeti operator

**Scope**: 
The document will:
* Document the basic technical requirement for Yeti root servers as well as 
  the expectation of human resources as a Yeti root operator.
* Specify the procedure of how to join and how to quit as yeti root operator.
* Consider the case of one operator running multiple root servers.
* Make some recommendations to Yeti root server operators.

### Basic requirement for Yeti root server operator

To be come a Yeti root operator, you should know the basic requirements and 
our expectations:

* Understand the purpose and the goal of Yeti project

* Have some experience on operation of relevant DNS server(s)

* Software, hardware, and network requirements:
 * A dedicated server or VPS which only hosts the Yeti root zone
 * A stable and non-tunneled IPv6 network
 * A dedicated IPv6 address (EU64 IPv6 address is not recommended)
 * A dedicated domain name for the server which only has an AAAA record
   attached to it
 * The authority servers should be stable and the NS servers of that domain
   name should be stable 
 
* Human resources commitment

  Because it is a live testbed for root system experiment, so we do not expect 
  any urgent configuration changes. However, the server cannot be fully on
  auto-pilot, due to experiments that will affect the distribution master
  servers and may require changes to the authority servers. Therefore, we
  expect authority operators to offer 24-hour response time to questions and
  outage notifications, and 72-hour response time for planned configuration
  changes.

**Note**: The coordinators of Yeti DNS project reserve the right to deny the
application or remove an existing operator if they can not meet the basic
requirements.

### How to join and how to quit

Regarding how to join Yeti as a root operator, there is a document
<https://github.com/bii-lab/Yeti-Project#how-to-join-yeti> which describes the
steps to apply and setup the server.

From the coordinators' side, to setup we need the following information:
  
  * IPv6 address to serve (EUI-64 based address should be avoided).
  * FQDN of the server.
  * IPv6 address used to pull the zone (this may be different from the service
    address, especially if the service is provided by multiple machines).
    This may be required by the ACL at the DMs.
  * The software and version.
  * E-mail address for each of the responsible persons.
  * Responsible persons' PGP key (registered at pgp.mit.edu is preferable).

If any operator want to quit for some reason, you should to send a mail to 
the operator 7 days in advance.

### Considerations in running multiple Yeti root servers by one operator

From both research and operational aspects it sounds OK, given that in the IANA
root system Verisign runs the A and J root servers. The only concerns are: 

1) The diversity of system and network, and
2) The opportunity for future participants given 25 is our target number of
   of Yeti root servers (ideally 25 operator are from different countries and
   a various continents).

There is an agreement for Yeti operator who would like to run **Additional root
server**.  A Yeti operator can apply additional root server only when:

* The number of Yeti root servers is less than the maximum number of roots in
  the Yeti testbed (currently 25),
* They meet the basic technical requirements for the additional server, and
* They provide the information of additional server, IPv6 address(AFXR), domain
  name, the software and version.

Coordinators reserve the right to reclaim the **Additional root server** in
case no room for new Yeti root operator (given that there is a limit).


### Make some recommendations to yeti root server operators

[TODO]

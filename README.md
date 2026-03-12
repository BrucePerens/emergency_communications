# emergency_communications
Policy discussions and software for a new emergency communications system

# The Goals

Create a system for Incident Management System communications that can not
only be used by Radio Amateurs, but becomes the *standard* for emergency
response organizations at the federal, state, and municipial level, including 
FEMA itself.

* The proposed design is a multi-head system for the ICS workflow, feeding a
  local router which selects from one or more data-link layers according to
  address and availability. Each ICS form entered receives a UUID and digital
  signature, and this is preserved, with an audit-trail, as it is routed through
  the system.

  Data-link software is to be modular, drop-in, and
  headless as much as possible (government restrictions on Amateur Radio
  communications may make an operator necessary on some data links).
  You should be able to add a data-link such as packet, HF with various modems,
  internet, or even USB-stick sneakernet to an operating system.

* The Winlink architecture is more like old telephone systems than the
  more modern Internet.
  There are centrally-managed servers which
  are not Open Source. Management of the servers is controlled by one
  organization, not really responsible to anyone although they have been
  responsive to issues somewhat. The absence of another system makes it
  difficult for users to move away from Winlink, despite their deficiencies.

* Winlink is a hub-and-spoke architecture. A peer-to-peer and mesh
  store-and-forward architecture, as with the Internet, would be
  more robust and capable of supporting more stations, for redundancy,
  including ad-hoc stations set up to support a specific disaster operation.
  To preserve reliability and message integrity in
  such an environment, checksums or CRC and digital signature,
  and end-to-end acknowledgement, with retransmission if necessary, must be
  used. Delivery notices must be part of the ICS form workflow, the existence
  of un-delivered
  messages must be immediately visible to responsible personnel, and
  there should be great attention to the need to not lose a form in the
  system through failure to deliver it. In that context, duplication of
  delivery is permissible and must be handled without creating duplication
  of work. Winlink does not presently employ these security and integrity
  facilities.
 
  Digital signature is legal on US Amateur Radio as long as it doesn't obscure
  information, see §97.113(a)(4). )

* The Winlink server software is not available for public security audit,
  as is the standard with the software that implements the Internet. This
  is a critical consideration, as nothing but constant public review has
  proven to be capable of supporting something so large and distributed
  as the Internet.

  In contrast to the security and integrity of the Internet in the face
  of constant attacks, the use
  of in-band-signalling was very widely deployed in the long-distance
  telephone system primarily operated by ATT as the Bell System, making
  it wide open to exploits (see https://en.wikipedia.org/wiki/Blue_box ).
  A public review would have made such an obvious mistake clear, and avoided
  the great expense borne by phone companies in moving all of that control
  signalling out-of-band.

  The same standard currently applied to the Internet must be applied to
  systems for when infrastructure *does* collapse.

* Due to all of the above, interoperability with Winlink is *NOT A GOAL*.
  This is the next generation, and must stand alone.

* FEMA and the states have a severe audit burden connected with emergency
  funding. If the state doesn't prove to FEMA that funds granted were
  spent as required by FEMA's policies, they have to pay FEMA back!
  Implementing something to help with this would probably be a
  grant-funded implementation using Odoo accounting, logistics,
  and resource management modules. The goal is for such a system to
  output a full audit packet for FEMA, either as paper forms or digital
  information. **We don't** have the information, or money, to do this
  now. But we will make sure that we communicate personnel, resource, and
  cost information in a way that could be conveyed to an accounting system.

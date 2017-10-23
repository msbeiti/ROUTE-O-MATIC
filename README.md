Description
============
ROUTE-O-MATIC provides  a  set  of  necessary  but  not  natively  supported  services and interfaces for the development of mesh routing protocols on Linux. In wireless mesh networks, especially in mobile scenarios, reactive  ad-hoc  routing  protocols  are  used  to  discover  routes on  demand  between  mesh  nodes.  Those  protocols  depend  on special  features  for  which  the  current  network  subsystem  of Linux is not designed. These include among others an interface to  notify  about  a  required  route  discovery  to  a  certain  host, and  a  buffer  to  temporarily  store  all  data  while  the  route discovery  is  performed.  The ROUTE-O-MATIC framework  adds these features to the Linux kernel. Additionally, the framework offers a  Link  Layer  Feedback  support,  which  reports  every transmission failure in order to accelerate the detection of broken links (see http://ieeexplore.ieee.org/document/6504255/?reload=true for more details)

Copyright: (C) 2012 Communication Networks Institute (CNI - Prof. Dr.-Ing. Christian Wietfeld) at Technische Universitaet Dortmund, Germany: http://www.kn.e-technik.tu-dortmund.de/.

This implementation is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation; either version 2 of the License, or (at your option) any later version.

Authors: Carsten.Vogel and Mohamad.Sbeiti.

Installation
------------

Run make. 

Configuration
-------------

ROUTE-O-MATIC supports currently three configuration parameters that might be set when inserting the module: isGateway,  enableLLF and LLFPerSecond. isGateway ist set to 1 if the node is a gateway, its default value is 0.  enableLLF is set to 1 if Link Layer Feedback should be activated, its default value is 0.  The LLFPerSecond option is used in combination with the enableLLF option. It defines the number of required LLFs in one second in order to consider a route broken. The default value of this option is 1.

Enabling Link Layer Feedback for mobile scenarios: To enable the Link Layer Feedback module, your wireless card must be using the ath9k driver. You have to patch you driver using the LLF_ath9k.patch provided in the ROUTE-O-MATIC directory.

Activation
-----------

Run insmod <PATH>/kmod/rom.ko isGateway=<0|1> enable_llf_support=<0|1> <LLFPerSecond=<3>>

Termination
------------

Run rmmod rom.ko.

Documentation
--------------
A thorough documentation of this code is provided at: www.paser.info.
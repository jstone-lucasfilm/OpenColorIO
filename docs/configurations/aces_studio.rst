..
  SPDX-License-Identifier: CC-BY-4.0
  Copyright Contributors to the OpenColorIO Project.

.. _aces_studio:

ACES Studio Config
==================

The ACES Studio Config is the successor to the widely used :ref:`ACES config <aces_1.0.3>`
for OCIO v1.

It contains the complete set of ACES color spaces, displays, and views.  In addition, it
contains some extra color spaces that are widely used in the VFX and post-production 
industries.

Users who need a simpler config that contains just the basics needed to use ACES color
management in common DCC tools are encouraged to check out the :ref:`aces_cg`.

The latest version of this config may be downloaded from the Releases page of its GitHub
`repo. <https://github.com/AcademySoftwareFoundation/OpenColorIO-Config-ACES/releases>`_

The ACES Studio Config leverages the high quality ACES implementation built into OCIO itself
and so requires no external LUT files.  In fact, even the config file is built into OCIO
and users may access it from any application that uses OCIO 2.2 or higher by using the
following string in place of the config path::
    ocio://studio-config-v1.0.0_aces-v1.3_ocio-v2.1

The OCIO Configs Working Group collected input from the community and simplified the
naming scheme relative to the earlier OCIO v1 ACES configs.  However, aliases have been 
added so that the original color space names continue to work (if there is an equivalent
space in the new config).

Please note that with OCIO v2 we are trying to be more rigorous about what constitutes a 
"color space". For this reason, the new configs do not bake view transforms or looks into 
the display color spaces.  Therefore, it is necessary to use a DisplayViewTransform rather 
than a ColorSpaceTransform if you want to bake in an ACES Output Transform.  This is not 
only more rigorous from a color management point of view, it also helps clarify to end-users 
the important role of a view transform in the process.  Baking in a view transform is a 
fundamentally different process than just converting between color space encodings, and it 
should be perceived as such by users.

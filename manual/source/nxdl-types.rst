===================================
NXDL: Data Types and Units
===================================

.. index:: ! NXDL data type 

.. _nxdl-types:
		
Data Types allowed in NXDL specifications
#########################################

Data types for use in NXDL
describe the expected type of data for a NeXus field. These terms are very
broad. More specific terms are used in actual NeXus data files that describe
size and array dimensions. In addition to the types in the following table, the
``NAPI`` type is defined when one wishes to permit a field
with any of these data types.

..  Generated from ../nxdlTypes.xsd via a custom Python tool
    ../../utils/types2rst.py ../../nxdlTypes.xsd > types.table

.. include:: types.table



.. index:: ! NXDL units type 

.. _nxdl-units:

Unit Categories allowed in NXDL specifications
##############################################

Unit categories in NXDL specifications
describe the expected type of units for a NeXus field. They should describe
valid units consistent with the :ref:`NeXus units <Design-Units>` section.
The values for unit categories are restricted (by
an enumeration) to the following table.

..  Generated from ../nxdlTypes.xsd via a custom Python tool
    ../../utils/units2rst.py ../../nxdlTypes.xsd > units.table

.. include:: units.table

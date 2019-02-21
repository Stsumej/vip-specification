.. This file is auto-generated.  Do not edit it by hand!

.. _multi-xml-electoral-district:

ElectoralDistrict
=================

The ``ElectoralDistrict`` object represents the geographic area in which contests are held. Examples
of ``ElectoralDistrict`` include: "the state of Maryland", "Virginia's 5th Congressional District",
or "Union School District". The geographic area that comprises a ``ElectoralDistrict`` is defined by
which precincts link to the ``ElectoralDistrict``.

+---------------------+---------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| Tag                 | Data Type                             | Required?    | Repeats?     | Description                              | Error Handling                           |
+=====================+=======================================+==============+==============+==========================================+==========================================+
| ExternalIdentifiers | :ref:`multi-xml-external-identifiers` | Optional     | Single       | Other identifiers that link to external  | If the element is invalid or not         |
|                     |                                       |              |              | datasets (e.g. `OCD-IDs`_)               | present, then the implementation is      |
|                     |                                       |              |              |                                          | required to ignore it.                   |
+---------------------+---------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| Name                | ``xs:string``                         | **Required** | Single       | Specifies the electoral area's name.     | If the field is invalid or not present,  |
|                     |                                       |              |              |                                          | then the implementation is required to   |
|                     |                                       |              |              |                                          | ignore the ``ElectoralDistrict`` object  |
|                     |                                       |              |              |                                          | containing it.                           |
+---------------------+---------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| Number              | ``xs:integer``                        | Optional     | Single       | Specifies the district number of the     | If the field is invalid or not present,  |
|                     |                                       |              |              | district (e.g. 34, in the case of the    | then the implementation is required to   |
|                     |                                       |              |              | 34th State Senate District). If a number | ignore it.                               |
|                     |                                       |              |              | is not applicable, instead of leaving    |                                          |
|                     |                                       |              |              | the field blank, leave this field out of |                                          |
|                     |                                       |              |              | the object; empty strings are not valid  |                                          |
|                     |                                       |              |              | for xs:integer fields.                   |                                          |
+---------------------+---------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| Type                | :ref:`multi-xml-district-type`        | **Required** | Single       | Specifies the type of electoral area.    | If the field is invalid or not present,  |
|                     |                                       |              |              |                                          | then the implementation is required to   |
|                     |                                       |              |              |                                          | ignore the ``ElectoralDistrict`` object  |
|                     |                                       |              |              |                                          | containing it.                           |
+---------------------+---------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+
| OtherType           | ``xs:string``                         | Optional     | Single       | Allows for cataloging a new              | If the field is invalid or not present,  |
|                     |                                       |              |              | :ref:`multi-xml-district-type` option    | then the implementation is required to   |
|                     |                                       |              |              | when ``Type`` is specified as "other".   | ignore it.                               |
+---------------------+---------------------------------------+--------------+--------------+------------------------------------------+------------------------------------------+

.. _OCD-IDs: http://opencivicdata.readthedocs.org/en/latest/ocdids.html

.. code-block:: xml
   :linenos:

   <ElectoralDistrict id="ed60129">
      <ExternalIdentifiers>
        <ExternalIdentifier>
          <Type>ocd-id</Type>
          <Value>ocd-division/country:us/state:va</Value>
        </ExternalIdentifier>
        <ExternalIdentifier>
          <Type>fips</Type>
          <Value>51</Value>
        </ExternalIdentifier>
      </ExternalIdentifiers>
      <Name>Commonwealth of Virginia</Name>
      <Type>state</Type>
   </ElectoralDistrict>

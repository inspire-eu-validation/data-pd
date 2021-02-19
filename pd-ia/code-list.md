# Code lists

**Purpose**: Verify that code lists extensions can be accessed.

**Prerequisites**

**Test method**

* Verify that any code list extensions are publicly accessible via HTTP, i.e. inspect extensible code list values property elements. If a reference (@xlink:href) has a value that does not start with http://inspire.ec.europa.eu/codelist/, verify that a HTTP GET request to the URI retrieves a document. Otherwise report [brokenLink](#brokenLink).

This data theme currently has the following empty codelists:

* [ClassificationTypeValue](#ClassificationTypeValue): http://inspire.ec.europa.eu/codelist/ClassificationTypeValue
* [VariableValue](#VariableValue): http://inspire.ec.europa.eu/codelist/VariableValue


**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (3)
* [TG DS-PD ](./README.md#ref_TG_DS_PD) Annex C


**Test type**: Automated

**Notes**

Annex C of the [TG DS-PD ](./README.md#ref_TG_DS_PD) includes recommended values that may be used by data providers. They are published in the INSPIRE Registry. Before creating new terms, please check if one of them can be used.

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
brokenLink <a name="brokenLink"/>  |  XML document '$filename', $featureType '$gmlid': The property '$propertyName' has a value '$value' that cannot be retrieved using HTTP. Every code list value must be made available in an online registry. 

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                                               |  XPath expression      |Multiplicity   |Voidable
---------------------------------------------------------- | -----------------------|---------------|---------------------------------
ClassificationTypeValue <a name ="ClassificationTypeValue"></a> | //schema-element(pd:StatisticalDistribution)/pd:classification/pd:Classification/pd:type/@xlink:href | 1 (0..\* for the parent) | No
VariableValue <a name ="VariableValue"></a> | //schema-element(pd:StatisticalDistribution)/pd:measure/@xlink:href | 1 | No
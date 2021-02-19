# Constraints

**Purpose**: Verify that the features provided in the dataset adhere to the constraints specified in the INSPIRE application schema.

**Prerequisites**

**Test method**

The following check is performed for every feature in the dataset.

* Check that either the [value](#value) or the [specialValue](#specialValue) attribute is provided.


**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (2)
* [TG DS-PD](./README.md#ref_TG_DS_PD) 5.3.2.2.4.

**Test type**: Automated

**Notes** 

Verify that the OCL constraints that are specified in the UML model of the application schema are met, i.e. validate features against the constraints. For unmet constraints report [constraintViolation](#constraintViolation).

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
constraintViolation <a name="constraintViolation"/>  |  XML document '$filename', $featureType '$gmlid': The constraint '$constraint' is violated.

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                   |  XPath expression                 |Multiplicity       |Voidable
------------------------------ | --------------------------------- | ------------------|----------
value <a name="value"></a> | //schema-element(pd:StatisticalDistribution)/pd:value/pd:StatisticalValue/pd:value | 0..1 (1..\* for the parent) | No
specialValue <a name="specialValue"></a> | //schema-element(pd:StatisticalDistribution)/pd:value/pd:StatisticalValue/pd:specialValue/@xlink:href | 0..1 (1..\* for the parent) | No
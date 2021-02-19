# Code list values

**Purpose**: Verify whether all attributes whose value type is a code list take the values set out therein

**Prerequisites**

**Test method**

When an attribute has a code list as its type, verify that the values comply with the definitions and include the values set out in Annex II, III and IV of the Implementing Rule. To pass this test verify that any instance of an attribute:

* takes only values explicitly specified in the INSPIRE code list register when the code list‘s extensibility is 'none'.
* takes only a value explicitly specified in the INSPIRE code list register or shall take a value that is narrower (i.e. more specific) than those explicitly specified in the application schema when the code list‘s extensibility is 'narrower'.
* takes values explicitly specified in the INSPIRE code list register when the code list‘s extensibility is 'open' or if a value is not one of the values listed in the code list register check that any extensions do not overlap with the code lists that are defined in Annexes II, III and IV of the Implementing Rule and that all extensions conform to the requirements (This last check is a manual test).


The following checks are performed for every feature in the dataset, for the 'open' codelists:

* Check that all the [type](#type) elements has a xlink:href attribute pointing to a [pre-defined value](#preDefinedValue1). If the check fails a manual check will be required asking to review the code list definition in order to verify that any extensions do not overlap with the code lists that are defined in Annexes II, III and IV of the Implementing Rule. If the check fails report [reviewCodeListValue](#reviewCodeListValue).

* Check that all the [measurementMethod](#measurementMethod) elements has a xlink:href attribute pointing to a [pre-defined value](#preDefinedValue2). If the check fails a manual check will be required asking to review the code list definition in order to verify that any extensions do not overlap with the code lists that are defined in Annexes II, III and IV of the Implementing Rule. If the check fails report [reviewCodeListValue](#reviewCodeListValue).

* Check that all the [generalStatus](#generalStatus) and [status](#status) elements has a xlink:href attribute pointing to a [pre-defined value](#preDefinedValue3). If the check fails a manual check will be required asking to review the code list definition in order to verify that any extensions do not overlap with the code lists that are defined in Annexes II, III and IV of the Implementing Rule. If the check fails report [reviewCodeListValue](#reviewCodeListValue).

* Check that all the [specialValue](#specialValue) elements has a xlink:href attribute pointing to a [pre-defined value](#preDefinedValue4). If the check fails a manual check will be required asking to review the code list definition in order to verify that any extensions do not overlap with the code lists that are defined in Annexes II, III and IV of the Implementing Rule. If the check fails report [reviewCodeListValue](#reviewCodeListValue).


| <a name="preDefinedValue1"></a> Pre-defined values for xlink:href attribute of [type](#type) element are available in the INSPIRE Registry | 
| ---- | 
| ClassificationItemTypeValue: http://inspire.ec.europa.eu/codelist/ClassificationItemTypeValue |

| <a name="preDefinedValue2"></a> Pre-defined values for xlink:href attribute of [measurementMethod](#measurementMethod) element are available in the INSPIRE Registry | 
| ---- | 
| StatisticsMeasurementMethodValue: http://inspire.ec.europa.eu/codelist/StatisticsMeasurementMethodValue |

| <a name="preDefinedValue3"></a> Pre-defined values for xlink:href attribute of [generalStatus](#generalStatus) and [status](#status) elements are available in the INSPIRE Registry | 
| ---- | 
| StatisticalDataStatusValue: http://inspire.ec.europa.eu/codelist/StatisticalDataStatusValue |

| <a name="preDefinedValue4"></a> Pre-defined values for xlink:href attribute of [specialValue](#specialValue) element are available in the INSPIRE Registry | 
| ---- | 
| SpecialValue: http://inspire.ec.europa.eu/codelist/SpecialValue |


**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (1)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (3)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (1)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (2)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (3)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (4)

**Test type**: Automated

**Notes**

The ClassificationItemTypeValue codelist includes the values of the following "not extensible" code lists:

	* AgeBy5YearsValue: http://inspire.ec.europa.eu/codelist/AgeBy5YearsValue
	* AgeByYearValue: http://inspire.ec.europa.eu/codelist/AgeByYearValue
	* NACECodeValue: http://inspire.ec.europa.eu/codelist/NACECodeValue
	* GenderValue: http://inspire.ec.europa.eu/codelist/GenderValue


## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
disallowedCodeListValue <a name="disallowedCodeListValue"/> | XML document '$filename', $featureType '$gmlid': The property '$propertyName' has a value '$value' that is not one of the allowed values listed at $codelist. Please note that the URIs of all code list values from the INSPIRE Registry shall be referenced using the http protocol.
reviewCodeListValue <a name="reviewCodeListValue"/> | XML document '{filename}', {featureType} '{gmlid}': The property '{property}' has a value '{value}' that is not one of the pre-defined values in the INSPIRE data specification. The same value is used by {count} other features in the dataset, too. Extensions to the pre-defined values are allowed, but must not overlap with one of the pre-defined values and be consistent with the specification of the property. Please review the definition of the value. Please note that the URIs of all code list values from the INSPIRE Registry shall be referenced using the http protocol. 

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                                               |  XPath expression				|Multiplicity       |Voidable
---------------------------------------------------------- | -------------------------------|-------------------|---------
type <a name="type"></a> | //schema-element(pd:StatisticalDistribution)/pd:value/pd:StatisticalValue/pd:dimensions/pd:Dimensions/pd:thematic/pd:ClassificationItem/pd:type/@xlink:href <br> //schema-element(pd:StatisticalDistribution)/pd:classification/pd:Classification/pd:item/pd:ClassificationItem/pd:type/@xlink:href | 1 (0..\* for the parent) | No
measurementMethod <a name="measurementMethod"></a> | //schema-element(pd:StatisticalDistribution)/pd:measurementMethod/@xlink:href | 1 | No
generalStatus <a name="generalStatus"></a> | //schema-element(pd:StatisticalDistribution)/pd:generalStatus/@xlink:href | 1 | No
status <a name="status"></a> | //schema-element(pd:StatisticalDistribution)/pd:value/pd:StatisticalValue/pd:status/@xlink:href | 1 (1..\* for the parent) | No
specialValue <a name="specialValue"></a> | //schema-element(pd:StatisticalDistribution)/pd:value/pd:StatisticalValue/pd:specialValue/@xlink:href | 0..1 (1..\* for the parent) | No
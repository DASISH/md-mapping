#Mapfiles
A mapfile with xpath expressions for each field have the folowing structure

``` xml
<?xml version="1.0" encoding="UTF-8" ?>
<mapping-table>
  <!-- Specify the namespaces used in this section -->
  <namespaces>
    <namespace ns="dc" uri="http://purl.org/dc/elements/1.1/"/>
  </namespaces>
  <mappings>
    <!-- This field can be multiple values, join each distinct value and separate them with ';' -->
    <field name="Creator">
      <xpath>string-join(distinct-values(//dc:creator/text()), '; ')</xpath>
    </field>
    
    <!-- Each xpath is evaluated in order, if no result the next one will be evaluated -->
    <field name="url">
      <xpath>if (contains (//dc:identifier[1]/text(),'doi:')) then concat('http://dx.doi.org/',substring-after(//dc:identifier[1]/text(),'doi:')) else //dc:identifier/text()</xpath>
      <xpath>if (contains(//dc:source/text(),     '[doi:')) then concat('http://dx.doi.org/',substring-before(substring-after(//dc:source/text(), '[doi: '), ']')) else //dc:source/text()</xpath>
    </field>    
  </mappings>
</mapping-table>  
```

| Field            | Multiple      | Note       |
| ---------------- | ------------- | ---------- |
| Access           | No            |            | 
| Collection       | No            |            | 
| Community        | No            |            | 
| Contributor      | Yes           |            | 
| Country          | Yes           |            | 
| CreationDate     | Yes           |            | 
| Creator          | Yes           |            | 
| DataFormat       | Yes           |            | 
| DataProvider     | No            |            | 
| Discipline       | Yes           |            | 
| Fulltext         | No            |  Full text representation of the metadata (e.g. full xml source) | 
| Language         | Yes           |            | 
| MetadataSchema   | No            |            | 
| MetadataSource   | No            |            | 
| Notes            | Yes           |            | 
| ResourceType     | Yes           |            | 
| SpatialCoverage  | Yes           |            | 
| Subject          | Yes           |            | 
| TemporalCoverage | Yes           |            | 
| Title            | No            |            | 
| Url              | No            | Source Url for the landing page (e.g. catalouge) |


#Used Metadata Standards
##CMDI

##DataCite 3.0

##Dublin Core (dc)

##DDI 1.2.2


##DDI 3.1
Main XSD: http://www.ddialliance.org/Specification/DDI-Lifecycle/3.1/XMLSchema/instance.xsd


| Module Name	   |  Namespace	   | Filename/Link  |
| ---------------- | ------------- | -------------- |
| Archive	| ddi:archive:3_1 |	archive.xsd |
| Comparative	| ddi:comparative:3_1	| comparative.xsd |
| Conceptual Component	| ddi:conceptualcomponent:3_1	| conceptualcomponent.xsd |
| Data Collection	| ddi:datacollection:3_1	| datacollection.xsd |
| Dataset	| ddi:dataset:3_1	| dataset.xsd |
| Group	| ddi:group:3_1	| group.xsd |
| Instance	| ddi:instance:3_1	| instance.xsd |
| Logical Product	| ddi:logicalproduct:3_1	| logicalproduct.xsd |
| Physical Data Product	| ddi:physicaldataproduct:3_1	| physicaldataproduct.xsd |
| Physical Data Product - NCube - Inline	| ddi:physicaldataproduct_ncube_inline:3_1	| physicaldataproduct_ncube_inline.xsd |
| Physical Data Product - NCube - Normal	| ddi:physicaldataproduct_ncube_normal:3_1	| physicaldataproduct_ncube_normal.xsd |
| Physical Data Product - Proprietary	| ddi:physicaldataproduct_ncube_proprietary:3_1	| physicaldataproduct_proprietary.xsd |
| Physical Data Product - NCube - Tabular	| ddi:physicaldataproduct_ncube_tabular:3_1	| physicaldataproduct_ncube_tabular.xsd |
| Physical Instance	| ddi:physicalinstance:3_1	| physicalinstance.xsd |
| DDI Profile	| ddi:profile:3_1	| ddiprofile.xsd |
| [Reusable](http://www.ddialliance.org/Specification/DDI-Lifecycle/3.1/XMLSchema/FieldLevelDocumentation/namespaces/ddi_reusable_3_1/namespace-summary.html)	| ddi:reusable:3_1	| [reusable.xsd](http://www.ddialliance.org/Specification/DDI-Lifecycle/3.1/XMLSchema/reusable.xsd) |
| [Study Unit](http://www.ddialliance.org/Specification/DDI-Lifecycle/3.1/XMLSchema/FieldLevelDocumentation/namespaces/ddi_studyunit_3_1/namespace-summary.html)	| ddi:studyunit:3_1	| [studyunit.xsd](http://www.ddialliance.org/Specification/DDI-Lifecycle/3.1/XMLSchema/studyunit.xsd) |

Following modules provide an interface to Dublin Core and XHTML.

| Module Name	   |Namespace	   |Filename/Link   |
| ---------------- | ------------- | -------------- |
| Dublin Core Elements	| ddi:dcelements:3_1	| dcelements.xsd | 
| DDI XHTML 1.1 Model	| http://www.w3.org/1999/xhtml	| ddi-xhtml11-model-1.xsd |
| DDI XHTML 1.1 Modules	| http://www.w3.org/1999/xhtml	| ddi-xhtml11-modules-1.xsd |
| DDI XHMTL 1.1	| http://www.w3.org/1999/xhtml	| ddi-xhtml11.xsd |

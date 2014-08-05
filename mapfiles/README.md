A mapfile with xpath expressions for each field have the folowing structure

```
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

| Field            | Multiple      |
| ---------------- | ------------- |
| Access           | No            |
| Collection       | No            |
| Community        | No            | 
| Contributor      | Yes           |
| Country          | Yes           |
| CreationDate     | Yes           |
| Creator          | Yes           |
| DataFormat       | Yes           |
| DataProvider     | No            | 
| Discipline       | Yes           |
| Fulltext         | No            | 
| Language         | Yes           |
| MetadataSchema   | No            | 
| MetadataSource   | No            | 
| Notes            | Yes           |
| ResourceType     | Yes           |
| SpatialCoverage  | Yes           |
| Subject          | Yes           |
| TemporalCoverage | Yes           |
| Title            | No            | 
| Url              | No            | 

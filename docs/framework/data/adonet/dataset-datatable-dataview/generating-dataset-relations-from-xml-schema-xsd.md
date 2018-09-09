---
title: Generar relaciones de objetos DataSet en un esquema XML (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: 7c73dcec3d23b094436791af6649de83b9eacad9
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44251646"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>Generar relaciones de objetos DataSet en un esquema XML (XSD)
En un <xref:System.Data.DataSet>, para formar una asociación entre dos o más columnas se debe crear una relación primaria-secundaria. Hay tres formas para representar un **DataSet** relación dentro de un esquema (XSD) del lenguaje de definición de esquemas XML:  
  
-   Especificar tipos complejos anidados.  
  
-   Use la **msdata: Relationship** anotación.  
  
-   Especifique un **xs: keyref** sin el **msdata: ConstraintOnly** anotación.  
  
## <a name="nested-complex-types"></a>Tipos complejos anidados  
 Las definiciones de tipos complejos anidados de un esquema indican las relaciones primaria-secundaria de los elementos. El siguiente fragmento de esquema XML muestra que **OrderDetail** es un elemento secundario de la **orden** elemento.  
  
```xml  
<xs:element name="Order">  
  <xs:complexType>  
     <xs:sequence>          
       <xs:element name="OrderDetail" />  
           <xs:complexType>               
           </xs:complexType>  
     </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 El proceso de asignación de esquema XML crea tablas en la **DataSet** que corresponden a los tipos complejos anidados en el esquema. También crea columnas adicionales que se usan como elemento primario**-** columnas secundarias para las tablas generadas. Tenga en cuenta que estos primario**-** columnas secundaria especifican relaciones, que no es lo mismo que especificar restricciones de clave principal/clave externa.  
  
## <a name="msdatarelationship-annotation"></a>Anotación msdata:Relationship  
 El **msdata: Relationship** anotación le permite especificar explícitamente relaciones de elementos primarios y secundarios entre los elementos en el esquema que no están anidados. El ejemplo siguiente muestra la estructura de la **relación** elemento.  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 Los atributos de la **msdata: Relationship** anotación identificar los elementos que participan en la relación de elementos primarios y secundarios, así como la **parentkey** y **childkey** los elementos y atributos implicados en la relación. El proceso de asignación utiliza esta información para generar tablas en el **DataSet** y crear la relación de clave principal/clave externa entre estas tablas.  
  
 Por ejemplo, el siguiente fragmento de esquema especifica **orden** y **OrderDetail** elementos del mismo nivel (no están anidados). El esquema especifica un **msdata: Relationship** anotación, que especifica la relación primario-secundario entre estos dos elementos. En este caso, se debe especificar una relación explícita mediante la **msdata: Relationship** anotación.  
  
```xml  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetail">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
       <xs:element name="Order">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
    </xs:choice>  
  </xs:complexType>  
</xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrdDetailRelation"  
          msdata:parent="Order"  
          msdata:child="OrderDetail"   
          msdata:parentkey="OrderNumber"  
          msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
```  
  
 El proceso de asignación utiliza el **relación** elemento para crear una relación de elementos primarios y secundarios entre el **OrderNumber** columna en el **orden** tabla y el **OrderNo** columna en el **OrderDetail** de tabla en la **DataSet**. El proceso de asignación sólo especifica la relación; no especifica automáticamente ninguna restricción para los valores de estas columnas, como ocurre en las restricciones de clave principal y clave externa de las bases de datos relacionales.  
  
### <a name="in-this-section"></a>En esta sección  
 [Asignación de relaciones implícitas entre elementos de esquema anidados](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 Describe las restricciones y relaciones que se crean implícitamente en un **DataSet** cuando se encuentran elementos anidados en el esquema XML.  
  
 [Asignación de relaciones especificadas para elementos anidados](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 Describe cómo establecer explícitamente relaciones en un **DataSet** para elementos anidados en el esquema XML.  
  
 [Definición de relaciones entre elementos sin anidamiento](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 Describe cómo crear relaciones en un **DataSet** entre los elementos de esquema XML que no están anidados.  
  
### <a name="related-sections"></a>Secciones relacionadas  
 [Derivación de una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Describe la estructura relacional, o esquema, de un **DataSet** creado a partir de esquema (XSD).  
  
 [Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones de clave únicas y externas en un **DataSet**.  
  
## <a name="see-also"></a>Vea también  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)

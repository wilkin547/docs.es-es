---
title: Generar relaciones de objetos DataSet en un esquema XML (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: feb0be7f66bf0f407e54ef0830c13f0c4a8a6418
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151135"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>Generar relaciones de objetos DataSet en un esquema XML (XSD)
En un <xref:System.Data.DataSet>, para formar una asociación entre dos o más columnas se debe crear una relación primaria-secundaria. Hay tres maneras de representar una relación **DataSet** dentro de un esquema de lenguaje de definición de esquemas XML (XSD):  
  
- Especificar tipos complejos anidados.  
  
- Utilice la anotación **msdata:Relationship.**  
  
- Especifique un **xs:keyref** sin la anotación **msdata:ConstraintOnly.**  
  
## <a name="nested-complex-types"></a>Tipos complejos anidados  
 Las definiciones de tipos complejos anidados de un esquema indican las relaciones primaria-secundaria de los elementos. El siguiente fragmento de esquema XML muestra que **OrderDetail** es un elemento secundario de la **Order** elemento.  
  
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
  
 El proceso de asignación de esquemas XML crea tablas en el **conjunto** de datos que corresponden a los tipos complejos anidados en el esquema. También crea columnas adicionales que**-** se usan como columnas primarias secundarias para las tablas generadas. Tenga en**-** cuenta que estas columnas primarias secundarias especifican relaciones, que no es lo mismo que especificar restricciones de clave principal/clave externa.  
  
## <a name="msdatarelationship-annotation"></a>Anotación msdata:Relationship  
 La anotación **msdata:Relationship** permite especificar explícitamente las relaciones primario-secundario entre los elementos del esquema que no están anidados. En el ejemplo siguiente se muestra la estructura del elemento **Relationship.**  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"
msdata:parent=""
msdata:child=""
msdata:parentkey=""
msdata:childkey="" />  
```  
  
 Los atributos de la anotación **msdata:Relationship** identifican los elementos implicados en la relación primario-secundario, así como los elementos y atributos **parentkey** y **childkey** implicados en la relación. El proceso de asignación utiliza esta información para generar tablas en el **conjunto** de datos y para crear la relación clave principal/clave externa entre estas tablas.  
  
 Por ejemplo, el siguiente fragmento de esquema especifica **Order** y **OrderDetail** elementos en el mismo nivel (no anidado). El esquema especifica una anotación **msdata:Relationship,** que especifica la relación primario-secundario entre estos dos elementos. En este caso, se debe especificar una relación explícita mediante la anotación **msdata:Relationship.**  
  
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
  
 El proceso de asignación utiliza el elemento **Relationship** para crear una relación primario-secundario entre la columna **OrderNumber** de la tabla **Order** y la columna **OrderNo** de la tabla **OrderDetail** del **conjunto de datos**. El proceso de asignación sólo especifica la relación; no especifica automáticamente ninguna restricción para los valores de estas columnas, como ocurre en las restricciones de clave principal y clave externa de las bases de datos relacionales.  
  
### <a name="in-this-section"></a>En esta sección  
 [Asignar relaciones implícitas entre elementos de esquema anidados](map-implicit-relations-between-nested-schema-elements.md)  
 Describe las restricciones y relaciones que se crean implícitamente en un **DataSet** cuando se encuentran elementos anidados en el esquema XML.  
  
 [Asignar relaciones especificadas para elementos anidados](map-relations-specified-for-nested-elements.md)  
 Describe cómo establecer explícitamente relaciones en un **DataSet** para elementos anidados en el esquema XML.  
  
 [Especificar relaciones entre elementos sin anidamiento](specify-relations-between-elements-with-no-nesting.md)  
 Describe cómo crear relaciones en un **DataSet** entre elementos de esquema XML que no están anidados.  
  
### <a name="related-sections"></a>Secciones relacionadas  
 [Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Describe la estructura relacional, o esquema, de un **DataSet** que se crea a partir del esquema del lenguaje de definición de esquemas XML (XSD).  
  
 [Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones de clave únicas y externas en un **dataset**.  
  
## <a name="see-also"></a>Consulte también

- [Información general de ADO.NET](../ado-net-overview.md)

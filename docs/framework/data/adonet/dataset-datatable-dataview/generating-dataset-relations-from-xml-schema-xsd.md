---
title: Generar relaciones de objetos DataSet en un esquema XML (XSD)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: bda9ff0052c6dc2462f007e3febb3cbf9ca7d5ac
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>Generar relaciones de objetos DataSet en un esquema XML (XSD)
En un <xref:System.Data.DataSet>, para formar una asociación entre dos o más columnas se debe crear una relación primaria-secundaria. Hay tres formas de representar un **conjunto de datos** relación dentro de un esquema de lenguaje (XSD) de definición de esquema XML:  
  
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
  
 El proceso de asignación de esquema XML crea tablas en la **conjunto de datos** que corresponden a los tipos complejos anidados en el esquema. También crea columnas adicionales que se usan como primario**-**columnas primaria-secundaria para las tablas generadas. Tenga en cuenta que estos primario**-**columnas primaria-secundaria especifican relaciones, que no es lo mismo que especificar restricciones de clave externa y clave principal.  
  
## <a name="msdatarelationship-annotation"></a>Anotación msdata:Relationship  
 El **msdata: Relationship** anotación permite especificar explícitamente relaciones primaria-secundaria entre los elementos del esquema que no están anidados. En el ejemplo siguiente se muestra la estructura de la **relación** elemento.  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 Los atributos de la **msdata: Relationship** anotación identifican los elementos implicados en la relación de elementos primarios y secundarios, así como el **parentkey** y **childkey** elementos y atributos implicados en la relación. El proceso de asignación utiliza esta información para generar tablas en el **conjunto de datos** y para crear la relación de clave principal/clave externa entre estas tablas.  
  
 Por ejemplo, el siguiente fragmento de esquema especifica **orden** y **OrderDetail** elementos del mismo nivel (no están anidados). El esquema especifica un **msdata: Relationship** anotación, que especifica la relación de elementos primarios y secundarios entre estos dos elementos. En este caso, se debe especificar una relación explícita mediante la **msdata: Relationship** anotación.  
  
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
  
 El proceso de asignación utiliza el **relación** elemento que se va a crear una relación de elementos primarios y secundarios entre el **OrderNumber** columna en el **orden** tabla y la **OrderNo** columna en el **OrderDetail** tabla el **conjunto de datos**. El proceso de asignación sólo especifica la relación; no especifica automáticamente ninguna restricción para los valores de estas columnas, como ocurre en las restricciones de clave principal y clave externa de las bases de datos relacionales.  
  
### <a name="in-this-section"></a>En esta sección  
 [Asignar relaciones implícitas entre elementos de esquema anidados](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 Describe las restricciones y relaciones que se crean implícitamente en un **conjunto de datos** cuando se encuentran elementos anidados en el esquema XML.  
  
 [Asignar relaciones especificadas para elementos anidados](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 Describe cómo establecer explícitamente relaciones en un **conjunto de datos** para los elementos anidados del esquema XML.  
  
 [Especificar relaciones entre elementos sin anidamiento](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 Describe cómo crear relaciones en un **conjunto de datos** entre elementos de esquema XML que no están anidados.  
  
### <a name="related-sections"></a>Secciones relacionadas  
 [Derivar la estructura relacional de un conjunto de datos de esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Describe la estructura relacional, o esquema, de un **conjunto de datos** creado a partir de esquema XML Schema definition language (XSD).  
  
 [Asignar restricciones de esquema (XSD) de XML a las restricciones de conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones de clave únicas y externas en un **conjunto de datos**.  
  
## <a name="see-also"></a>Vea también  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)

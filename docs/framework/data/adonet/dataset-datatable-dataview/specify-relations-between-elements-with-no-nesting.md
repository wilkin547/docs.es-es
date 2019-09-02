---
title: Especificar relaciones entre elementos sin anidamiento
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: 83dce7173c016a7d7d2d626bb7a3606de29d54ae
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204473"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a>Especificar relaciones entre elementos sin anidamiento
Cuando los elementos no están anidados, no se crea ninguna relación implícita. Sin embargo, puede especificar explícitamente las relaciones entre elementos que no están anidados mediante la anotación **msdata: Relationship** .  
  
 En el ejemplo siguiente se muestra un esquema XML en el que se especifica la anotación **msdata: Relationship** entre los elementos **Order** y **OrderDetail** , que no están anidados. La anotación **msdata: Relationship** se especifica como el elemento secundario del elemento **Schema** .  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
             xmlns:xs="http://www.w3.org/2001/XMLSchema"   
             xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:string" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNumber" type="xs:string" />  
           <xs:element name="EmpNumber" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  </xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrderDetailRelation"  
                            msdata:parent="Order"   
                            msdata:child="OrderDetail"   
                            msdata:parentkey="OrderNumber"   
                            msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
</xs:schema>  
```  
  
 El proceso de asignación del esquema del lenguaje de definición de esquemas <xref:System.Data.DataSet> XML (XSD) crea un objeto con las tablas **Order** y **OrderDetail** y una relación especificada entre estas dos tablas, como se muestra a continuación.  
  
```  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber   
ChildTable: OrderDetail  
ChildColumns: OrderNo   
Nested: False  
```  
  
## <a name="see-also"></a>Vea también

- [Generación de relaciones de objetos DataSet en un esquema XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)

---
title: Asignar relaciones especificadas para elementos anidados
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: 510a5e676df7bac274c6086b94e9a23e7540da20
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204636"
---
# <a name="map-relations-specified-for-nested-elements"></a>Asignar relaciones especificadas para elementos anidados
Un esquema puede incluir una anotación **msdata: Relationship** para especificar explícitamente la asignación entre dos elementos cualesquiera del esquema. Los dos elementos especificados en **msdata: Relationship** se pueden anidar en el esquema, pero no tienen que ser. El proceso de asignación usa **msdata: Relationship** en el esquema para generar la relación de clave principal y clave externa entre las dos columnas.  
  
 En el ejemplo siguiente se muestra un esquema XML en el que el elemento **OrderDetail** es un elemento secundario de **Order**. La **anotación msdata:** identifica esta relación de elementos primarios y secundarios y especifica que la columna **OrderNumber** de la tabla de **pedidos** resultante esté relacionada con la columna **OrderNo** de la tabla **OrderDetail** resultante.  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
 <xs:complexType>  
  <xs:choice maxOccurs="unbounded">  
   <xs:element name="Order">  
    <xs:complexType>  
     <xs:sequence>  
       <xs:element name="OrderNumber" type="xs:string" />  
       <xs:element name="EmpNumber" type="xs:string" />  
       <xs:element name="OrderDetail">  
          <xs:annotation>  
           <xs:appinfo>  
            <msdata:Relationship name="OrdODRelation"   
                                msdata:parent="Order"   
                                msdata:child="OrderDetail"   
                                msdata:parentkey="OrderNumber"   
                                msdata:childkey="OrderNo"/>  
           </xs:appinfo>  
          </xs:annotation>  
          <xs:complexType>  
            <xs:sequence>  
             <xs:element name="OrderNo" type="xs:string" />  
             <xs:element name="ItemNo" type="xs:string" />  
            </xs:sequence>  
         </xs:complexType>  
       </xs:element>  
     </xs:sequence>  
    </xs:complexType>  
   </xs:element>  
  </xs:choice>  
 </xs:complexType>  
</xs:element>  
</xs:schema>  
```  
  
 El proceso de asignación del esquema XML crea lo siguiente en el <xref:System.Data.DataSet>:  
  
- Un **pedido** y una tabla **OrderDetail** .  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- Una relación entre las tablas **Order** y **OrderDetail** . La propiedad Nested de esta relación está establecida en **true** porque los elementos **Order** y **OrderDetail** están anidados en el esquema.  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 El proceso de asignación no crea ninguna restricción.  
  
## <a name="see-also"></a>Vea también

- [Generación de relaciones de objetos DataSet en un esquema XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)

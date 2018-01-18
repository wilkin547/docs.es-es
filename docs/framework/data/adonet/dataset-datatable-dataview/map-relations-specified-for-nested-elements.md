---
title: Asignar relaciones especificadas para elementos anidados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c23e951ee2fd6f5956ab41d4425c9e8af8f12b95
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="map-relations-specified-for-nested-elements"></a>Asignar relaciones especificadas para elementos anidados
Un esquema puede incluir una **msdata: Relationship** anotación que se debe especificar explícitamente la asignación entre dos elementos cualesquiera del esquema. Los dos elementos especificados en **msdata: Relationship** pueden estar anidados en el esquema, pero no tiene que ser. El proceso de asignación utiliza **msdata: Relationship** en el esquema para generar la relación de clave principal/clave externa entre las dos columnas.  
  
 En el ejemplo siguiente se muestra un esquema XML en el que el **OrderDetail** trata de un elemento secundario de **orden**. El **msdata: Relationship** identifica esta relación primaria-secundaria y especifica que la **OrderNumber** columna del resultante **orden** tabla se relaciona con la **OrderNo** columna del resultante **OrderDetail** tabla.  
  
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
  
-   Un **orden** y **OrderDetail** tabla.  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
-   Una relación entre la **orden** y **OrderDetail** tablas. El **Nested** propiedad para esta relación se establece en **True** porque el **orden** y **OrderDetail** elementos están anidados en el esquema .  
  
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
 [Generación de relaciones de objetos DataSet en un esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)

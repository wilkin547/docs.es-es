---
title: Especificar relaciones entre elementos sin anidamiento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 036085160e9e4817964754a85db627e4d4ba8654
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="b0120-102">Especificar relaciones entre elementos sin anidamiento</span><span class="sxs-lookup"><span data-stu-id="b0120-102">Specify Relations Between Elements with No Nesting</span></span>
<span data-ttu-id="b0120-103">Cuando los elementos no están anidados, no se crea ninguna relación implícita.</span><span class="sxs-lookup"><span data-stu-id="b0120-103">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="b0120-104">Sin embargo, puede especificar explícitamente relaciones entre elementos que no están anidados utilizando la **msdata: Relationship** anotación.</span><span class="sxs-lookup"><span data-stu-id="b0120-104">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="b0120-105">En el ejemplo siguiente se muestra un esquema XML en el que el **msdata: Relationship** anotación se especifica entre el **orden** y **OrderDetail** elementos, que no son anidar.</span><span class="sxs-lookup"><span data-stu-id="b0120-105">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="b0120-106">El **msdata: Relationship** anotación se especifica como el elemento secundario de la **esquema** elemento.</span><span class="sxs-lookup"><span data-stu-id="b0120-106">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
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
  
 <span data-ttu-id="b0120-107">El proceso de asignación de esquema de esquema XML definition language (XSD) crea un <xref:System.Data.DataSet> con **orden** y **OrderDetail** tablas y una relación entre estas dos tablas, tal y como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="b0120-107">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber   
ChildTable: OrderDetail  
ChildColumns: OrderNo   
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0120-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0120-108">See Also</span></span>  
 [<span data-ttu-id="b0120-109">Generar las relaciones de conjunto de datos desde un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="b0120-109">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="b0120-110">Asignar restricciones de esquema (XSD) de XML a las restricciones de conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="b0120-110">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="b0120-111">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="b0120-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

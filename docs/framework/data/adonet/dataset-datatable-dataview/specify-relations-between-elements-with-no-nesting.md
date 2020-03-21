---
title: Especificar relaciones entre elementos sin anidamiento
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: bee427c6cdf76792773ea827c8772b276ff29c31
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150823"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="7d0f7-102">Especificar relaciones entre elementos sin anidamiento</span><span class="sxs-lookup"><span data-stu-id="7d0f7-102">Specify Relations Between Elements with No Nesting</span></span>
<span data-ttu-id="7d0f7-103">Cuando los elementos no están anidados, no se crea ninguna relación implícita.</span><span class="sxs-lookup"><span data-stu-id="7d0f7-103">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="7d0f7-104">Sin embargo, puede especificar explícitamente relaciones entre elementos que no están anidados mediante la anotación **msdata:Relationship.**</span><span class="sxs-lookup"><span data-stu-id="7d0f7-104">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="7d0f7-105">En el ejemplo siguiente se muestra un esquema XML en el que se especifica la anotación **msdata:Relationship** entre los elementos **Order** y **OrderDetail,** que no están anidados.</span><span class="sxs-lookup"><span data-stu-id="7d0f7-105">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="7d0f7-106">La anotación **msdata:Relationship** se especifica como el elemento secundario del elemento **Schema.**</span><span class="sxs-lookup"><span data-stu-id="7d0f7-106">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
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
  
 <span data-ttu-id="7d0f7-107">El proceso de asignación de esquemas <xref:System.Data.DataSet> del lenguaje de definición de esquemas XML (XSD) crea un con **Order** y **OrderDetail** tablas y una relación especificada entre estas dos tablas, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="7d0f7-107">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```text  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber
ChildTable: OrderDetail  
ChildColumns: OrderNo
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d0f7-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d0f7-108">See also</span></span>

- [<span data-ttu-id="7d0f7-109">Generación de relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="7d0f7-109">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="7d0f7-110">Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="7d0f7-110">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="7d0f7-111">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7d0f7-111">ADO.NET Overview</span></span>](../ado-net-overview.md)

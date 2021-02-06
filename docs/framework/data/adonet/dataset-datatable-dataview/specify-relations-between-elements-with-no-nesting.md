---
description: 'Más información sobre: especificar relaciones entre elementos sin anidamiento'
title: Especificar relaciones entre elementos sin anidamiento
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: 68f6edad0c282091529bf9182f5161d0808a47aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651631"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="450e6-103">Especificar relaciones entre elementos sin anidamiento</span><span class="sxs-lookup"><span data-stu-id="450e6-103">Specify Relations Between Elements with No Nesting</span></span>

<span data-ttu-id="450e6-104">Cuando los elementos no están anidados, no se crea ninguna relación implícita.</span><span class="sxs-lookup"><span data-stu-id="450e6-104">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="450e6-105">Sin embargo, puede especificar explícitamente las relaciones entre elementos que no están anidados mediante la anotación **msdata: Relationship** .</span><span class="sxs-lookup"><span data-stu-id="450e6-105">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="450e6-106">En el ejemplo siguiente se muestra un esquema XML en el que se especifica la anotación **msdata: Relationship** entre los elementos **Order** y **OrderDetail** , que no están anidados.</span><span class="sxs-lookup"><span data-stu-id="450e6-106">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="450e6-107">La anotación **msdata: Relationship** se especifica como el elemento secundario del elemento **Schema** .</span><span class="sxs-lookup"><span data-stu-id="450e6-107">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
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
  
 <span data-ttu-id="450e6-108">El proceso de asignación del esquema del lenguaje de definición de esquemas XML (XSD) crea un <xref:System.Data.DataSet> objeto con las tablas **Order** y **OrderDetail** y una relación especificada entre estas dos tablas, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="450e6-108">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```text  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber
ChildTable: OrderDetail  
ChildColumns: OrderNo
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="450e6-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="450e6-109">See also</span></span>

- [<span data-ttu-id="450e6-110">Generar relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="450e6-110">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="450e6-111">Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="450e6-111">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="450e6-112">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="450e6-112">ADO.NET Overview</span></span>](../ado-net-overview.md)

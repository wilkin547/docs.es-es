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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 221e204c9eef5a861fbd6b85c1e23a0674c6aa4c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="0fcfc-102">Asignar relaciones especificadas para elementos anidados</span><span class="sxs-lookup"><span data-stu-id="0fcfc-102">Map Relations Specified for Nested Elements</span></span>
<span data-ttu-id="0fcfc-103">Un esquema puede incluir una **msdata: Relationship** anotación que se debe especificar explícitamente la asignación entre dos elementos cualesquiera del esquema.</span><span class="sxs-lookup"><span data-stu-id="0fcfc-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="0fcfc-104">Los dos elementos especificados en **msdata: Relationship** pueden estar anidados en el esquema, pero no tiene que ser.</span><span class="sxs-lookup"><span data-stu-id="0fcfc-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="0fcfc-105">El proceso de asignación utiliza **msdata: Relationship** en el esquema para generar la relación de clave principal/clave externa entre las dos columnas.</span><span class="sxs-lookup"><span data-stu-id="0fcfc-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="0fcfc-106">En el ejemplo siguiente se muestra un esquema XML en el que el **OrderDetail** trata de un elemento secundario de **orden**.</span><span class="sxs-lookup"><span data-stu-id="0fcfc-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="0fcfc-107">El **msdata: Relationship** identifica esta relación primaria-secundaria y especifica que la **OrderNumber** columna del resultante **orden** tabla se relaciona con la **OrderNo** columna del resultante **OrderDetail** tabla.</span><span class="sxs-lookup"><span data-stu-id="0fcfc-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
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
  
 <span data-ttu-id="0fcfc-108">El proceso de asignación del esquema XML crea lo siguiente en el <xref:System.Data.DataSet>:</span><span class="sxs-lookup"><span data-stu-id="0fcfc-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
-   <span data-ttu-id="0fcfc-109">Un **orden** y **OrderDetail** tabla.</span><span class="sxs-lookup"><span data-stu-id="0fcfc-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
-   <span data-ttu-id="0fcfc-110">Una relación entre la **orden** y **OrderDetail** tablas.</span><span class="sxs-lookup"><span data-stu-id="0fcfc-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="0fcfc-111">El **Nested** propiedad para esta relación se establece en **True** porque el **orden** y **OrderDetail** elementos están anidados en el esquema .</span><span class="sxs-lookup"><span data-stu-id="0fcfc-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="0fcfc-112">El proceso de asignación no crea ninguna restricción.</span><span class="sxs-lookup"><span data-stu-id="0fcfc-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fcfc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fcfc-113">See Also</span></span>  
 [<span data-ttu-id="0fcfc-114">Generación de relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="0fcfc-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="0fcfc-115">Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="0fcfc-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="0fcfc-116">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="0fcfc-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

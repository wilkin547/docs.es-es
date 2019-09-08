---
title: Asignar relaciones especificadas para elementos anidados
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: e8cdf73b6277abdaab1256ca87e615a5e25e7336
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786086"
---
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="f1021-102">Asignar relaciones especificadas para elementos anidados</span><span class="sxs-lookup"><span data-stu-id="f1021-102">Map Relations Specified for Nested Elements</span></span>
<span data-ttu-id="f1021-103">Un esquema puede incluir una anotación **msdata: Relationship** para especificar explícitamente la asignación entre dos elementos cualesquiera del esquema.</span><span class="sxs-lookup"><span data-stu-id="f1021-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="f1021-104">Los dos elementos especificados en **msdata: Relationship** se pueden anidar en el esquema, pero no tienen que ser.</span><span class="sxs-lookup"><span data-stu-id="f1021-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="f1021-105">El proceso de asignación usa **msdata: Relationship** en el esquema para generar la relación de clave principal y clave externa entre las dos columnas.</span><span class="sxs-lookup"><span data-stu-id="f1021-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="f1021-106">En el ejemplo siguiente se muestra un esquema XML en el que el elemento **OrderDetail** es un elemento secundario de **Order**.</span><span class="sxs-lookup"><span data-stu-id="f1021-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="f1021-107">La **anotación msdata:** identifica esta relación de elementos primarios y secundarios y especifica que la columna **OrderNumber** de la tabla de **pedidos** resultante esté relacionada con la columna **OrderNo** de la tabla **OrderDetail** resultante.</span><span class="sxs-lookup"><span data-stu-id="f1021-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
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
  
 <span data-ttu-id="f1021-108">El proceso de asignación del esquema XML crea lo siguiente en el <xref:System.Data.DataSet>:</span><span class="sxs-lookup"><span data-stu-id="f1021-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="f1021-109">Un **pedido** y una tabla **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="f1021-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- <span data-ttu-id="f1021-110">Una relación entre las tablas **Order** y **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="f1021-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="f1021-111">La propiedad **Nested** de esta relación está establecida en **true** porque los elementos **Order** y **OrderDetail** están anidados en el esquema.</span><span class="sxs-lookup"><span data-stu-id="f1021-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="f1021-112">El proceso de asignación no crea ninguna restricción.</span><span class="sxs-lookup"><span data-stu-id="f1021-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1021-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1021-113">See also</span></span>

- [<span data-ttu-id="f1021-114">Generación de relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="f1021-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="f1021-115">Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="f1021-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="f1021-116">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f1021-116">ADO.NET Overview</span></span>](../ado-net-overview.md)

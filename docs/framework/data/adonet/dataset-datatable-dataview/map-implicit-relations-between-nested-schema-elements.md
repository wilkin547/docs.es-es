---
title: Asignar relaciones implícitas entre elementos de esquema anidados
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: 6fcb0b9bb7c947359c2334d3d116f5317f84af83
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586816"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a><span data-ttu-id="2966d-102">Asignar relaciones implícitas entre elementos de esquema anidados</span><span class="sxs-lookup"><span data-stu-id="2966d-102">Map Implicit Relations Between Nested Schema Elements</span></span>
<span data-ttu-id="2966d-103">Un esquema del lenguaje de definición de esquema XML (XSD) puede tener tipos complejos anidados dentro de otros.</span><span class="sxs-lookup"><span data-stu-id="2966d-103">An XML Schema definition language (XSD) schema can have complex types nested inside one another.</span></span> <span data-ttu-id="2966d-104">En este caso, el proceso de asignación aplica la asignación predeterminada y crea lo siguiente en el <xref:System.Data.DataSet>:</span><span class="sxs-lookup"><span data-stu-id="2966d-104">In this case, the mapping process applies default mapping and creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="2966d-105">Una tabla para cada uno de los tipos complejos (primario y secundario).</span><span class="sxs-lookup"><span data-stu-id="2966d-105">One table for each of the complex types (parent and child).</span></span>  
  
- <span data-ttu-id="2966d-106">Si no existe ninguna restricción única en el elemento primario, una columna de clave principal adicional por cada definición de tabla denominado *TableName*_Id donde *TableName* es el nombre de la tabla primaria.</span><span class="sxs-lookup"><span data-stu-id="2966d-106">If no unique constraint exists on the parent, one additional primary key column per table definition named *TableName*_Id where *TableName* is the name of the parent table.</span></span>  
  
- <span data-ttu-id="2966d-107">Una restricción primary key en la tabla primaria que identifica la columna adicional como clave principal (estableciendo la **IsPrimaryKey** propiedad **True**).</span><span class="sxs-lookup"><span data-stu-id="2966d-107">A primary key constraint on the parent table identifying the additional column as the primary key (by setting the **IsPrimaryKey** property to **True**).</span></span> <span data-ttu-id="2966d-108">La restricción recibe el nombre Constraint\#, donde \# es 1, 2, 3, etc.</span><span class="sxs-lookup"><span data-stu-id="2966d-108">The constraint is named Constraint\# where \# is 1, 2, 3, and so on.</span></span> <span data-ttu-id="2966d-109">Por ejemplo, el nombre predeterminado de la primera restricción es Constraint1.</span><span class="sxs-lookup"><span data-stu-id="2966d-109">For example, the default name for the first constraint is Constraint1.</span></span>  
  
- <span data-ttu-id="2966d-110">Una restricción de clave externa en la tabla secundaria que identifica la columna adicional como clave externa que hace referencia a la clave principal de la tabla primaria.</span><span class="sxs-lookup"><span data-stu-id="2966d-110">A foreign key constraint on the child table identifying the additional column as the foreign key referring to the primary key of the parent table.</span></span> <span data-ttu-id="2966d-111">La restricción recibe el nombre *ParentTable_ChildTable* donde *ParentTable* es el nombre de la tabla primaria y *ChildTable* es el nombre de la tabla secundaria.</span><span class="sxs-lookup"><span data-stu-id="2966d-111">The constraint is named *ParentTable_ChildTable* where *ParentTable* is the name of the parent table and *ChildTable* is the name of the child table.</span></span>  
  
- <span data-ttu-id="2966d-112">Una relación de datos entre las tablas primaria y secundaria.</span><span class="sxs-lookup"><span data-stu-id="2966d-112">A data relation between the parent and child tables.</span></span>  
  
 <span data-ttu-id="2966d-113">El ejemplo siguiente muestra un esquema donde **OrderDetail** es un elemento secundario de **orden**.</span><span class="sxs-lookup"><span data-stu-id="2966d-113">The following example shows a schema where **OrderDetail** is a child element of **Order**.</span></span>  
  
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
  
 <span data-ttu-id="2966d-114">El proceso de asignación de esquema XML crea lo siguiente en el **DataSet**:</span><span class="sxs-lookup"><span data-stu-id="2966d-114">The XML Schema mapping process creates the following in the **DataSet**:</span></span>  
  
- <span data-ttu-id="2966d-115">Un **orden** y un **OrderDetail** tabla.</span><span class="sxs-lookup"><span data-stu-id="2966d-115">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
- <span data-ttu-id="2966d-116">Una restricción unique en la **orden** tabla.</span><span class="sxs-lookup"><span data-stu-id="2966d-116">A unique constraint on the **Order** table.</span></span> <span data-ttu-id="2966d-117">Tenga en cuenta que el **IsPrimaryKey** propiedad está establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="2966d-117">Note that the **IsPrimaryKey** property is set to **True**.</span></span>  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
- <span data-ttu-id="2966d-118">Una restricción foreign key en el **OrderDetail** tabla.</span><span class="sxs-lookup"><span data-stu-id="2966d-118">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
- <span data-ttu-id="2966d-119">Una relación entre el **orden** y **OrderDetail** tablas.</span><span class="sxs-lookup"><span data-stu-id="2966d-119">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="2966d-120">El **Nested** propiedad para esta relación se establece en **True** porque el **orden** y **OrderDetail** elementos están anidados en el esquema .</span><span class="sxs-lookup"><span data-stu-id="2966d-120">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```  
    ParentTable: Order  
    ParentColumns: Order_Id   
    ChildTable: OrderDetail  
    ChildColumns: Order_Id   
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2966d-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="2966d-121">See also</span></span>

- [<span data-ttu-id="2966d-122">Generación de relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="2966d-122">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="2966d-123">Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="2966d-123">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="2966d-124">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="2966d-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

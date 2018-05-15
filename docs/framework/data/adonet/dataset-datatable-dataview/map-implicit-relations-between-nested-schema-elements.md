---
title: Asignar relaciones implícitas entre elementos de esquema anidados
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: 1bce0c2815ac94787055794942807777232df295
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a><span data-ttu-id="d2fa0-102">Asignar relaciones implícitas entre elementos de esquema anidados</span><span class="sxs-lookup"><span data-stu-id="d2fa0-102">Map Implicit Relations Between Nested Schema Elements</span></span>
<span data-ttu-id="d2fa0-103">Un esquema del lenguaje de definición de esquema XML (XSD) puede tener tipos complejos anidados dentro de otros.</span><span class="sxs-lookup"><span data-stu-id="d2fa0-103">An XML Schema definition language (XSD) schema can have complex types nested inside one another.</span></span> <span data-ttu-id="d2fa0-104">En este caso, el proceso de asignación aplica la asignación predeterminada y crea lo siguiente en el <xref:System.Data.DataSet>:</span><span class="sxs-lookup"><span data-stu-id="d2fa0-104">In this case, the mapping process applies default mapping and creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
-   <span data-ttu-id="d2fa0-105">Una tabla para cada uno de los tipos complejos (primario y secundario).</span><span class="sxs-lookup"><span data-stu-id="d2fa0-105">One table for each of the complex types (parent and child).</span></span>  
  
-   <span data-ttu-id="d2fa0-106">Si no existe ninguna restricción única en el elemento primario, una columna de clave principal adicional por cada definición de tabla denominada *TableName*_Id donde *TableName* es el nombre de la tabla primaria.</span><span class="sxs-lookup"><span data-stu-id="d2fa0-106">If no unique constraint exists on the parent, one additional primary key column per table definition named *TableName*_Id where *TableName* is the name of the parent table.</span></span>  
  
-   <span data-ttu-id="d2fa0-107">Una restricción primary key en la tabla primaria que identifica la columna adicional como clave principal (estableciendo la **IsPrimaryKey** propiedad **True**).</span><span class="sxs-lookup"><span data-stu-id="d2fa0-107">A primary key constraint on the parent table identifying the additional column as the primary key (by setting the **IsPrimaryKey** property to **True**).</span></span> <span data-ttu-id="d2fa0-108">La restricción recibe el nombre Constraint*#* donde *#* es 1, 2, 3 y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="d2fa0-108">The constraint is named Constraint*#* where *#* is 1, 2, 3, and so on.</span></span> <span data-ttu-id="d2fa0-109">Por ejemplo, el nombre predeterminado de la primera restricción es Constraint1.</span><span class="sxs-lookup"><span data-stu-id="d2fa0-109">For example, the default name for the first constraint is Constraint1.</span></span>  
  
-   <span data-ttu-id="d2fa0-110">Una restricción de clave externa en la tabla secundaria que identifica la columna adicional como clave externa que hace referencia a la clave principal de la tabla primaria.</span><span class="sxs-lookup"><span data-stu-id="d2fa0-110">A foreign key constraint on the child table identifying the additional column as the foreign key referring to the primary key of the parent table.</span></span> <span data-ttu-id="d2fa0-111">La restricción recibe el nombre *ParentTable_ChildTable* donde *ParentTable* es el nombre de la tabla primaria y *ChildTable* es el nombre de la tabla secundaria.</span><span class="sxs-lookup"><span data-stu-id="d2fa0-111">The constraint is named *ParentTable_ChildTable* where *ParentTable* is the name of the parent table and *ChildTable* is the name of the child table.</span></span>  
  
-   <span data-ttu-id="d2fa0-112">Una relación de datos entre las tablas primaria y secundaria.</span><span class="sxs-lookup"><span data-stu-id="d2fa0-112">A data relation between the parent and child tables.</span></span>  
  
 <span data-ttu-id="d2fa0-113">En el ejemplo siguiente se muestra un esquema donde **OrderDetail** es un elemento secundario de **orden**.</span><span class="sxs-lookup"><span data-stu-id="d2fa0-113">The following example shows a schema where **OrderDetail** is a child element of **Order**.</span></span>  
  
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
  
 <span data-ttu-id="d2fa0-114">El proceso de asignación de esquema XML crea lo siguiente en el **conjunto de datos**:</span><span class="sxs-lookup"><span data-stu-id="d2fa0-114">The XML Schema mapping process creates the following in the **DataSet**:</span></span>  
  
-   <span data-ttu-id="d2fa0-115">Un **orden** y **OrderDetail** tabla.</span><span class="sxs-lookup"><span data-stu-id="d2fa0-115">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
-   <span data-ttu-id="d2fa0-116">Una restricción unique en la **orden** tabla.</span><span class="sxs-lookup"><span data-stu-id="d2fa0-116">A unique constraint on the **Order** table.</span></span> <span data-ttu-id="d2fa0-117">Tenga en cuenta que la **IsPrimaryKey** propiedad está establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="d2fa0-117">Note that the **IsPrimaryKey** property is set to **True**.</span></span>  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
-   <span data-ttu-id="d2fa0-118">Una restricción foreign key en la **OrderDetail** tabla.</span><span class="sxs-lookup"><span data-stu-id="d2fa0-118">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
-   <span data-ttu-id="d2fa0-119">Una relación entre la **orden** y **OrderDetail** tablas.</span><span class="sxs-lookup"><span data-stu-id="d2fa0-119">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="d2fa0-120">El **Nested** propiedad para esta relación se establece en **True** porque el **orden** y **OrderDetail** elementos están anidados en el esquema .</span><span class="sxs-lookup"><span data-stu-id="d2fa0-120">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d2fa0-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2fa0-121">See Also</span></span>  
 [<span data-ttu-id="d2fa0-122">Generación de relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="d2fa0-122">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="d2fa0-123">Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="d2fa0-123">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="d2fa0-124">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="d2fa0-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

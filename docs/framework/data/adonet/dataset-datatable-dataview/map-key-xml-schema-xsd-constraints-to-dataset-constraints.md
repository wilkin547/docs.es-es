---
title: Asignar restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 5ebf333b065157fa9497cc1471a45698663638e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150940"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="bd9f3-102">Asignar restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="bd9f3-102">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="bd9f3-103">En un esquema, puede especificar una restricción de clave en un elemento o atributo mediante el elemento **key.**</span><span class="sxs-lookup"><span data-stu-id="bd9f3-103">In a schema, you can specify a key constraint on an element or attribute using the **key** element.</span></span> <span data-ttu-id="bd9f3-104">El elemento o el atributo para el que se especifica una restricción de clave debe tener valores únicos en cualquier instancia del esquema y no puede tener valores nulos.</span><span class="sxs-lookup"><span data-stu-id="bd9f3-104">The element or attribute on which a key constraint is specified must have unique values in any schema instance, and cannot have null values.</span></span>  
  
 <span data-ttu-id="bd9f3-105">La restricción de clave es similar a la restricción única, excepto en que la columna sobre la que se define una restricción de clave no puede tener valores nulos.</span><span class="sxs-lookup"><span data-stu-id="bd9f3-105">The key constraint is similar to the unique constraint, except that the column on which a key constraint is defined cannot have null values.</span></span>  
  
 <span data-ttu-id="bd9f3-106">En la tabla siguiente se describen los atributos **msdata** que puede especificar en el elemento **key.**</span><span class="sxs-lookup"><span data-stu-id="bd9f3-106">The following table outlines the **msdata** attributes that you can specify in the **key** element.</span></span>  
  
|<span data-ttu-id="bd9f3-107">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="bd9f3-107">Attribute name</span></span>|<span data-ttu-id="bd9f3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd9f3-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="bd9f3-109">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="bd9f3-109">**msdata:ConstraintName**</span></span>|<span data-ttu-id="bd9f3-110">Si se especifica este atributo, su valor se utiliza como nombre de la restricción.</span><span class="sxs-lookup"><span data-stu-id="bd9f3-110">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="bd9f3-111">De lo contrario, el atributo **name** proporciona el valor del nombre de la restricción.</span><span class="sxs-lookup"><span data-stu-id="bd9f3-111">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="bd9f3-112">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="bd9f3-112">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="bd9f3-113">Si `PrimaryKey="true"` está presente, la propiedad de restricción **IsPrimaryKey** se establece en **true,** lo que la convierte en una clave principal.</span><span class="sxs-lookup"><span data-stu-id="bd9f3-113">If `PrimaryKey="true"` is present, the **IsPrimaryKey** constraint property is set to **true**, thus making it a primary key.</span></span> <span data-ttu-id="bd9f3-114">La propiedad de columna **AllowDBNull** se establece en **false**, porque las claves principales no pueden tener valores NULL.</span><span class="sxs-lookup"><span data-stu-id="bd9f3-114">The **AllowDBNull** column property is set to **false**, because primary keys cannot have null values.</span></span>|  
  
 <span data-ttu-id="bd9f3-115">Al convertir el esquema en el que se especifica una restricción de clave, el proceso de asignación crea una restricción única en la tabla con la propiedad de columna **AllowDBNull** establecida en **false** para cada columna de la restricción.</span><span class="sxs-lookup"><span data-stu-id="bd9f3-115">In converting schema in which a key constraint is specified, the mapping process creates a unique constraint on the table with the **AllowDBNull** column property set to **false** for each column in the constraint.</span></span> <span data-ttu-id="bd9f3-116">La propiedad **IsPrimaryKey** de la restricción unique también `msdata:PrimaryKey="true"` se establece en **false** a menos que haya especificado en el elemento **de clave.**</span><span class="sxs-lookup"><span data-stu-id="bd9f3-116">The **IsPrimaryKey** property of the unique constraint is also set to **false** unless you have specified `msdata:PrimaryKey="true"` on the **key** element.</span></span> <span data-ttu-id="bd9f3-117">Esto es idéntico a una restricción única del esquema donde `PrimaryKey="true"`.</span><span class="sxs-lookup"><span data-stu-id="bd9f3-117">This is identical to a unique constraint in the schema in which `PrimaryKey="true"`.</span></span>  
  
 <span data-ttu-id="bd9f3-118">En el ejemplo de esquema siguiente, el elemento **key** especifica la restricción key en el elemento **CustomerID.**</span><span class="sxs-lookup"><span data-stu-id="bd9f3-118">In the following schema example, the **key** element specifies the key constraint on the **CustomerID** element.</span></span>  
  
```xml  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>
```  
  
 <span data-ttu-id="bd9f3-119">El elemento **key** especifica que los valores del elemento secundario **CustomerID** del elemento **Customers** deben tener valores únicos y no pueden tener valores null.</span><span class="sxs-lookup"><span data-stu-id="bd9f3-119">The **key** element specifies that the values of the **CustomerID** child element of the **Customers** element must have unique values and cannot have null values.</span></span> <span data-ttu-id="bd9f3-120">Al traducir el esquema del lenguaje de definición de esquema XML (XSD), el proceso de asignación crea la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="bd9f3-120">In translating the XML Schema definition language (XSD) schema, the mapping process creates the following table:</span></span>  
  
```text  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="bd9f3-121">La asignación de esquema XML también crea un **UniqueConstraint** <xref:System.Data.DataSet>en la columna **CustomerID,** como se muestra en el siguiente archivo .</span><span class="sxs-lookup"><span data-stu-id="bd9f3-121">The XML Schema mapping also creates a **UniqueConstraint** on the **CustomerID** column, as shown in the following <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="bd9f3-122">Para simplificar, sólo se muestran las propiedades relevantes.</span><span class="sxs-lookup"><span data-stu-id="bd9f3-122">(For simplicity, only relevant properties are shown.)</span></span>  
  
```text  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID
      IsPrimaryKey: True  
```  
  
 <span data-ttu-id="bd9f3-123">En el **DataSet** que se genera, el **IsPrimaryKey** propiedad de la **UniqueConstraint** se establece `msdata:PrimaryKey="true"` en **true** porque el esquema especifica en el elemento **de clave.**</span><span class="sxs-lookup"><span data-stu-id="bd9f3-123">In the **DataSet** that is generated, the **IsPrimaryKey** property of the **UniqueConstraint** is set to **true** because the schema specifies `msdata:PrimaryKey="true"` in the **key** element.</span></span>  
  
 <span data-ttu-id="bd9f3-124">El valor de la **Propiedad ConstraintName** de **UniqueConstraint** en el **DataSet** es el valor del atributo **msdata:ConstraintName** especificado en el elemento **clave** del esquema.</span><span class="sxs-lookup"><span data-stu-id="bd9f3-124">The value of the **ConstraintName** property of the **UniqueConstraint** in the **DataSet** is the value of the **msdata:ConstraintName** attribute specified in the **key** element in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd9f3-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd9f3-125">See also</span></span>

- [<span data-ttu-id="bd9f3-126">Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="bd9f3-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="bd9f3-127">Generación de relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="bd9f3-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="bd9f3-128">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bd9f3-128">ADO.NET Overview</span></span>](../ado-net-overview.md)

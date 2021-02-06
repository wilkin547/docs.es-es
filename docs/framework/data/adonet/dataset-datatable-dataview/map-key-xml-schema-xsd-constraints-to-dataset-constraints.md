---
description: Más información acerca de cómo asignar restricciones Key de esquema XML (XSD) a restricciones de conjunto de los conjuntos de claves
title: Asignar restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 0c07b53e06dc6b80395764b2bdd76045ee80bffd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651995"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="952d6-103">Asignar restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="952d6-103">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>

<span data-ttu-id="952d6-104">En un esquema, puede especificar una restricción de clave en un elemento o atributo mediante el elemento **key** .</span><span class="sxs-lookup"><span data-stu-id="952d6-104">In a schema, you can specify a key constraint on an element or attribute using the **key** element.</span></span> <span data-ttu-id="952d6-105">El elemento o el atributo para el que se especifica una restricción de clave debe tener valores únicos en cualquier instancia del esquema y no puede tener valores nulos.</span><span class="sxs-lookup"><span data-stu-id="952d6-105">The element or attribute on which a key constraint is specified must have unique values in any schema instance, and cannot have null values.</span></span>  
  
 <span data-ttu-id="952d6-106">La restricción de clave es similar a la restricción única, excepto en que la columna sobre la que se define una restricción de clave no puede tener valores nulos.</span><span class="sxs-lookup"><span data-stu-id="952d6-106">The key constraint is similar to the unique constraint, except that the column on which a key constraint is defined cannot have null values.</span></span>  
  
 <span data-ttu-id="952d6-107">En la tabla siguiente se describen los atributos **msdata** que puede especificar en el elemento **key** .</span><span class="sxs-lookup"><span data-stu-id="952d6-107">The following table outlines the **msdata** attributes that you can specify in the **key** element.</span></span>  
  
|<span data-ttu-id="952d6-108">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="952d6-108">Attribute name</span></span>|<span data-ttu-id="952d6-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="952d6-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="952d6-110">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="952d6-110">**msdata:ConstraintName**</span></span>|<span data-ttu-id="952d6-111">Si se especifica este atributo, su valor se utiliza como nombre de la restricción.</span><span class="sxs-lookup"><span data-stu-id="952d6-111">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="952d6-112">De lo contrario, el atributo **Name** proporciona el valor del nombre de la restricción.</span><span class="sxs-lookup"><span data-stu-id="952d6-112">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="952d6-113">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="952d6-113">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="952d6-114">Si `PrimaryKey="true"` está presente, la propiedad de restricción **IsPrimaryKey** está establecida en **true**, por lo que se convierte en una clave principal.</span><span class="sxs-lookup"><span data-stu-id="952d6-114">If `PrimaryKey="true"` is present, the **IsPrimaryKey** constraint property is set to **true**, thus making it a primary key.</span></span> <span data-ttu-id="952d6-115">La propiedad de columna **AllowDBNull** está establecida en **false**, ya que las claves principales no pueden tener valores NULL.</span><span class="sxs-lookup"><span data-stu-id="952d6-115">The **AllowDBNull** column property is set to **false**, because primary keys cannot have null values.</span></span>|  
  
 <span data-ttu-id="952d6-116">En la conversión del esquema en el que se especifica una restricción de clave, el proceso de asignación crea una restricción UNIQUE en la tabla con la propiedad de columna **AllowDBNull** establecida en **false** para cada columna de la restricción.</span><span class="sxs-lookup"><span data-stu-id="952d6-116">In converting schema in which a key constraint is specified, the mapping process creates a unique constraint on the table with the **AllowDBNull** column property set to **false** for each column in the constraint.</span></span> <span data-ttu-id="952d6-117">La propiedad **IsPrimaryKey** de la restricción UNIQUE también se establece en **false** , a menos que haya especificado `msdata:PrimaryKey="true"` en el elemento **key** .</span><span class="sxs-lookup"><span data-stu-id="952d6-117">The **IsPrimaryKey** property of the unique constraint is also set to **false** unless you have specified `msdata:PrimaryKey="true"` on the **key** element.</span></span> <span data-ttu-id="952d6-118">Esto es idéntico a una restricción única del esquema donde `PrimaryKey="true"`.</span><span class="sxs-lookup"><span data-stu-id="952d6-118">This is identical to a unique constraint in the schema in which `PrimaryKey="true"`.</span></span>  
  
 <span data-ttu-id="952d6-119">En el siguiente ejemplo de esquema, el elemento **key** especifica la restricción KEY en el elemento **CustomerID** .</span><span class="sxs-lookup"><span data-stu-id="952d6-119">In the following schema example, the **key** element specifies the key constraint on the **CustomerID** element.</span></span>  
  
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
  
 <span data-ttu-id="952d6-120">El elemento **key** especifica que los valores del elemento secundario **CustomerID** del elemento **Customers** deben tener valores únicos y no pueden tener valores NULL.</span><span class="sxs-lookup"><span data-stu-id="952d6-120">The **key** element specifies that the values of the **CustomerID** child element of the **Customers** element must have unique values and cannot have null values.</span></span> <span data-ttu-id="952d6-121">Al traducir el esquema del lenguaje de definición de esquema XML (XSD), el proceso de asignación crea la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="952d6-121">In translating the XML Schema definition language (XSD) schema, the mapping process creates the following table:</span></span>  
  
```text  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="952d6-122">La asignación de esquemas XML también crea una **UniqueConstraint** en la columna **CustomerID** , como se muestra a continuación <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="952d6-122">The XML Schema mapping also creates a **UniqueConstraint** on the **CustomerID** column, as shown in the following <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="952d6-123">Para simplificar, sólo se muestran las propiedades relevantes.</span><span class="sxs-lookup"><span data-stu-id="952d6-123">(For simplicity, only relevant properties are shown.)</span></span>  
  
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
  
 <span data-ttu-id="952d6-124">En el **conjunto de DataSet** que se genera, la propiedad **IsPrimaryKey** de la **UniqueConstraint** se establece en **true** porque el esquema especifica `msdata:PrimaryKey="true"` en el elemento **key** .</span><span class="sxs-lookup"><span data-stu-id="952d6-124">In the **DataSet** that is generated, the **IsPrimaryKey** property of the **UniqueConstraint** is set to **true** because the schema specifies `msdata:PrimaryKey="true"` in the **key** element.</span></span>  
  
 <span data-ttu-id="952d6-125">El valor de la propiedad **ConstraintName** de la **UniqueConstraint** en el **DataSet** es el valor del atributo **msdata: ConstraintName** especificado en el elemento **key** del esquema.</span><span class="sxs-lookup"><span data-stu-id="952d6-125">The value of the **ConstraintName** property of the **UniqueConstraint** in the **DataSet** is the value of the **msdata:ConstraintName** attribute specified in the **key** element in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="952d6-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="952d6-126">See also</span></span>

- [<span data-ttu-id="952d6-127">Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="952d6-127">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="952d6-128">Generar relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="952d6-128">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="952d6-129">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="952d6-129">ADO.NET Overview</span></span>](../ado-net-overview.md)

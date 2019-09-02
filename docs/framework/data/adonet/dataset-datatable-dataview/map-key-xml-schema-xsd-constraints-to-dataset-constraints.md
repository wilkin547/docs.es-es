---
title: Asignar restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: d6fcdae77c2f2ac07ea5cd16baf07cd5de36d25b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203468"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="14247-102">Asignar restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="14247-102">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="14247-103">En un esquema, puede especificar una restricción de clave en un elemento o atributo mediante el elemento **key** .</span><span class="sxs-lookup"><span data-stu-id="14247-103">In a schema, you can specify a key constraint on an element or attribute using the **key** element.</span></span> <span data-ttu-id="14247-104">El elemento o el atributo para el que se especifica una restricción de clave debe tener valores únicos en cualquier instancia del esquema y no puede tener valores nulos.</span><span class="sxs-lookup"><span data-stu-id="14247-104">The element or attribute on which a key constraint is specified must have unique values in any schema instance, and cannot have null values.</span></span>  
  
 <span data-ttu-id="14247-105">La restricción de clave es similar a la restricción única, excepto en que la columna sobre la que se define una restricción de clave no puede tener valores nulos.</span><span class="sxs-lookup"><span data-stu-id="14247-105">The key constraint is similar to the unique constraint, except that the column on which a key constraint is defined cannot have null values.</span></span>  
  
 <span data-ttu-id="14247-106">En la tabla siguiente se describen los atributos **msdata** que puede especificar en el elemento **key** .</span><span class="sxs-lookup"><span data-stu-id="14247-106">The following table outlines the **msdata** attributes that you can specify in the **key** element.</span></span>  
  
|<span data-ttu-id="14247-107">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="14247-107">Attribute name</span></span>|<span data-ttu-id="14247-108">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="14247-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="14247-109">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="14247-109">**msdata:ConstraintName**</span></span>|<span data-ttu-id="14247-110">Si se especifica este atributo, su valor se utiliza como nombre de la restricción.</span><span class="sxs-lookup"><span data-stu-id="14247-110">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="14247-111">De lo contrario, el atributo **Name** proporciona el valor del nombre de la restricción.</span><span class="sxs-lookup"><span data-stu-id="14247-111">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="14247-112">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="14247-112">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="14247-113">Si `PrimaryKey="true"` está presente, la propiedad de restricción **IsPrimaryKey** está establecida en **true**, por lo que se convierte en una clave principal.</span><span class="sxs-lookup"><span data-stu-id="14247-113">If `PrimaryKey="true"` is present, the **IsPrimaryKey** constraint property is set to **true**, thus making it a primary key.</span></span> <span data-ttu-id="14247-114">La propiedad de columna **AllowDBNull** está establecida en **false**, ya que las claves principales no pueden tener valores NULL.</span><span class="sxs-lookup"><span data-stu-id="14247-114">The **AllowDBNull** column property is set to **false**, because primary keys cannot have null values.</span></span>|  
  
 <span data-ttu-id="14247-115">En la conversión del esquema en el que se especifica una restricción de clave, el proceso de asignación crea una restricción UNIQUE en la tabla con la propiedad de columna **AllowDBNull** establecida en **false** para cada columna de la restricción.</span><span class="sxs-lookup"><span data-stu-id="14247-115">In converting schema in which a key constraint is specified, the mapping process creates a unique constraint on the table with the **AllowDBNull** column property set to **false** for each column in the constraint.</span></span> <span data-ttu-id="14247-116">La propiedad **IsPrimaryKey** de la restricción UNIQUE también se establece en **false** , a menos que `msdata:PrimaryKey="true"` haya especificado en el elemento **key** .</span><span class="sxs-lookup"><span data-stu-id="14247-116">The **IsPrimaryKey** property of the unique constraint is also set to **false** unless you have specified `msdata:PrimaryKey="true"` on the **key** element.</span></span> <span data-ttu-id="14247-117">Esto es idéntico a una restricción única del esquema donde `PrimaryKey="true"`.</span><span class="sxs-lookup"><span data-stu-id="14247-117">This is identical to a unique constraint in the schema in which `PrimaryKey="true"`.</span></span>  
  
 <span data-ttu-id="14247-118">En el siguiente ejemplo de esquema, el elemento **key** especifica la restricción KEY en el elemento **CustomerID** .</span><span class="sxs-lookup"><span data-stu-id="14247-118">In the following schema example, the **key** element specifies the key constraint on the **CustomerID** element.</span></span>  
  
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
  
 <span data-ttu-id="14247-119">El elemento **key** especifica que los valores del elemento secundario **CustomerID** del elemento **Customers** deben tener valores únicos y no pueden tener valores NULL.</span><span class="sxs-lookup"><span data-stu-id="14247-119">The **key** element specifies that the values of the **CustomerID** child element of the **Customers** element must have unique values and cannot have null values.</span></span> <span data-ttu-id="14247-120">Al traducir el esquema del lenguaje de definición de esquema XML (XSD), el proceso de asignación crea la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="14247-120">In translating the XML Schema definition language (XSD) schema, the mapping process creates the following table:</span></span>  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="14247-121">La asignación de esquemas XML también crea una **UniqueConstraint** en la columna **CustomerID** , como se muestra <xref:System.Data.DataSet>a continuación.</span><span class="sxs-lookup"><span data-stu-id="14247-121">The XML Schema mapping also creates a **UniqueConstraint** on the **CustomerID** column, as shown in the following <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="14247-122">Para simplificar, sólo se muestran las propiedades relevantes.</span><span class="sxs-lookup"><span data-stu-id="14247-122">(For simplicity, only relevant properties are shown.)</span></span>  
  
```  
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
  
 <span data-ttu-id="14247-123">En el **conjunto de DataSet** que se genera, la propiedad **IsPrimaryKey** de la **UniqueConstraint** se establece en **true** porque el `msdata:PrimaryKey="true"` esquema especifica en el elemento **key** .</span><span class="sxs-lookup"><span data-stu-id="14247-123">In the **DataSet** that is generated, the **IsPrimaryKey** property of the **UniqueConstraint** is set to **true** because the schema specifies `msdata:PrimaryKey="true"` in the **key** element.</span></span>  
  
 <span data-ttu-id="14247-124">El valor de la propiedad **ConstraintName** de la **UniqueConstraint** en el **DataSet** es el valor del atributo **msdata: ConstraintName** especificado en el elemento **key** del esquema.</span><span class="sxs-lookup"><span data-stu-id="14247-124">The value of the **ConstraintName** property of the **UniqueConstraint** in the **DataSet** is the value of the **msdata:ConstraintName** attribute specified in the **key** element in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14247-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="14247-125">See also</span></span>

- [<span data-ttu-id="14247-126">Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="14247-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="14247-127">Generación de relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="14247-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="14247-128">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="14247-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

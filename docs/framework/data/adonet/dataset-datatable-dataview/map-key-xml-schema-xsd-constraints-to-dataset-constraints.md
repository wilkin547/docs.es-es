---
title: Asignar restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6b999e6b1d6d73f107b7e1f4cb0d7e14c099a1f6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="6da06-102">Asignar restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="6da06-102">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="6da06-103">En un esquema, puede especificar una restricción de clave en un elemento o atributo mediante la **clave** elemento.</span><span class="sxs-lookup"><span data-stu-id="6da06-103">In a schema, you can specify a key constraint on an element or attribute using the **key** element.</span></span> <span data-ttu-id="6da06-104">El elemento o el atributo para el que se especifica una restricción de clave debe tener valores únicos en cualquier instancia del esquema y no puede tener valores nulos.</span><span class="sxs-lookup"><span data-stu-id="6da06-104">The element or attribute on which a key constraint is specified must have unique values in any schema instance, and cannot have null values.</span></span>  
  
 <span data-ttu-id="6da06-105">La restricción de clave es similar a la restricción única, excepto en que la columna sobre la que se define una restricción de clave no puede tener valores nulos.</span><span class="sxs-lookup"><span data-stu-id="6da06-105">The key constraint is similar to the unique constraint, except that the column on which a key constraint is defined cannot have null values.</span></span>  
  
 <span data-ttu-id="6da06-106">La siguiente tabla se describen los **msdata** atributos que se pueden especificar en el **clave** elemento.</span><span class="sxs-lookup"><span data-stu-id="6da06-106">The following table outlines the **msdata** attributes that you can specify in the **key** element.</span></span>  
  
|<span data-ttu-id="6da06-107">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="6da06-107">Attribute name</span></span>|<span data-ttu-id="6da06-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="6da06-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="6da06-109">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="6da06-109">**msdata:ConstraintName**</span></span>|<span data-ttu-id="6da06-110">Si se especifica este atributo, su valor se utiliza como nombre de la restricción.</span><span class="sxs-lookup"><span data-stu-id="6da06-110">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="6da06-111">En caso contrario, el **nombre** atributo proporciona el valor del nombre de restricción.</span><span class="sxs-lookup"><span data-stu-id="6da06-111">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="6da06-112">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="6da06-112">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="6da06-113">Si `PrimaryKey="true"` está presente, el **IsPrimaryKey** propiedad de restricción se establece en **true**, lo que una clave principal.</span><span class="sxs-lookup"><span data-stu-id="6da06-113">If `PrimaryKey="true"` is present, the **IsPrimaryKey** constraint property is set to **true**, thus making it a primary key.</span></span> <span data-ttu-id="6da06-114">El **AllowDBNull** propiedad de columna se establece en **false**, porque las claves principales no pueden tener valores nulos.</span><span class="sxs-lookup"><span data-stu-id="6da06-114">The **AllowDBNull** column property is set to **false**, because primary keys cannot have null values.</span></span>|  
  
 <span data-ttu-id="6da06-115">Convertir un esquema en el que se especifica una restricción de clave, el proceso de asignación crea una restricción unique en la tabla con el **AllowDBNull** propiedad column establecida en **false** para cada columna de la restricción.</span><span class="sxs-lookup"><span data-stu-id="6da06-115">In converting schema in which a key constraint is specified, the mapping process creates a unique constraint on the table with the **AllowDBNull** column property set to **false** for each column in the constraint.</span></span> <span data-ttu-id="6da06-116">El **IsPrimaryKey** propiedad de la restricción única también se establece en **false** a menos que haya especificado `msdata:PrimaryKey="true"` en el **clave** elemento.</span><span class="sxs-lookup"><span data-stu-id="6da06-116">The **IsPrimaryKey** property of the unique constraint is also set to **false** unless you have specified `msdata:PrimaryKey="true"` on the **key** element.</span></span> <span data-ttu-id="6da06-117">Esto es idéntico a una restricción única del esquema donde `PrimaryKey="true"`.</span><span class="sxs-lookup"><span data-stu-id="6da06-117">This is identical to a unique constraint in the schema in which `PrimaryKey="true"`.</span></span>  
  
 <span data-ttu-id="6da06-118">En el siguiente ejemplo de esquema, el **clave** elemento especifica la restricción de clave en el **CustomerID** elemento.</span><span class="sxs-lookup"><span data-stu-id="6da06-118">In the following schema example, the **key** element specifies the key constraint on the **CustomerID** element.</span></span>  
  
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
  
 <span data-ttu-id="6da06-119">El **clave** elemento especifica que los valores de la **CustomerID** elemento secundario de la **clientes** elemento debe tener valores únicos y no pueden tener valores nulos.</span><span class="sxs-lookup"><span data-stu-id="6da06-119">The **key** element specifies that the values of the **CustomerID** child element of the **Customers** element must have unique values and cannot have null values.</span></span> <span data-ttu-id="6da06-120">Al traducir el esquema del lenguaje de definición de esquema XML (XSD), el proceso de asignación crea la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="6da06-120">In translating the XML Schema definition language (XSD) schema, the mapping process creates the following table:</span></span>  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="6da06-121">La asignación de esquema XML crea también un **UniqueConstraint** en el **CustomerID** columna, tal y como se muestra en la siguiente <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6da06-121">The XML Schema mapping also creates a **UniqueConstraint** on the **CustomerID** column, as shown in the following <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6da06-122">Para simplificar, sólo se muestran las propiedades relevantes.</span><span class="sxs-lookup"><span data-stu-id="6da06-122">(For simplicity, only relevant properties are shown.)</span></span>  
  
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
  
 <span data-ttu-id="6da06-123">En el **conjunto de datos** que se genera, la **IsPrimaryKey** propiedad de la **UniqueConstraint** está establecido en **true** porque el esquema especifica `msdata:PrimaryKey="true"` en el **clave** elemento.</span><span class="sxs-lookup"><span data-stu-id="6da06-123">In the **DataSet** that is generated, the **IsPrimaryKey** property of the **UniqueConstraint** is set to **true** because the schema specifies `msdata:PrimaryKey="true"` in the **key** element.</span></span>  
  
 <span data-ttu-id="6da06-124">El valor de la **ConstraintName** propiedad de la **UniqueConstraint** en el **conjunto de datos** es el valor de la **msdata: ConstraintName** el atributo especificado en el **clave** elemento en el esquema.</span><span class="sxs-lookup"><span data-stu-id="6da06-124">The value of the **ConstraintName** property of the **UniqueConstraint** in the **DataSet** is the value of the **msdata:ConstraintName** attribute specified in the **key** element in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6da06-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="6da06-125">See Also</span></span>  
 [<span data-ttu-id="6da06-126">Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="6da06-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="6da06-127">Generación de relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="6da06-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="6da06-128">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="6da06-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

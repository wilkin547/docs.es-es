---
title: Inferir columnas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 858a23fb8fec7b7f2eee95a1365d16e846beb548
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="inferring-columns"></a><span data-ttu-id="4f8d2-102">Inferir columnas</span><span class="sxs-lookup"><span data-stu-id="4f8d2-102">Inferring Columns</span></span>
<span data-ttu-id="4f8d2-103">Una vez que ADO.NET determina a partir de un documento XML los elementos que se van a inferir como tablas para un <xref:System.Data.DataSet>, se deducen las columnas para dichas tablas.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-103">After ADO.NET has determined from an XML document which elements to infer as tables for a <xref:System.Data.DataSet>, it then infers the columns for those tables.</span></span> <span data-ttu-id="4f8d2-104">ADO.NET 2.0 incorporó un nuevo motor de inferencia de esquemas que deduce un tipo de datos fuertemente tipados para cada **simpleType** elemento.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-104">ADO.NET 2.0 introduced a new schema inference engine that infers a strongly typed data type for each **simpleType** element.</span></span> <span data-ttu-id="4f8d2-105">En versiones anteriores, el tipo de datos de un deducido **simpleType** elemento siempre era **xsd: String**.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-105">In previous versions, the data type of an inferred **simpleType** element was always **xsd:string**.</span></span>  
  
## <a name="migration-and-backward-compatibility"></a><span data-ttu-id="4f8d2-106">Migración y compatibilidad con versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="4f8d2-106">Migration and Backward Compatibility</span></span>  
 <span data-ttu-id="4f8d2-107">El **ReadXml** método toma un argumento de tipo **InferSchema**.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-107">The **ReadXml** method takes an argument of type **InferSchema**.</span></span> <span data-ttu-id="4f8d2-108">Este argumento le permite especificar un comportamiento de inferencia compatible con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-108">This argument allows you to specify inference behavior compatible with previous versions.</span></span> <span data-ttu-id="4f8d2-109">Los valores disponibles para la **InferSchema** enumeración se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-109">The available values for the **InferSchema** enumeration are shown in the following table.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 <span data-ttu-id="4f8d2-110">Proporciona compatibilidad con versiones anteriores al deducir siempre un tipo simple como <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-110">Provides backward compatibility by always inferring a simple type as <xref:System.String>.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 <span data-ttu-id="4f8d2-111">Infiere un tipo de datos fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-111">Infers a strongly typed data type.</span></span> <span data-ttu-id="4f8d2-112">Inicia una excepción si se utiliza con una <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-112">Throws an exception if used with a <xref:System.Data.DataTable>.</span></span>  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 <span data-ttu-id="4f8d2-113">Omite cualquier esquema alineado y lee los datos del esquema del <xref:System.Data.DataSet> existente.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-113">Ignores any inline schema and reads data into the existing <xref:System.Data.DataSet> schema.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="4f8d2-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="4f8d2-114">Attributes</span></span>  
 <span data-ttu-id="4f8d2-115">Tal como se define en [deducir tablas](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), un elemento con atributos se deducirá como una tabla.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-115">As defined in [Inferring Tables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), an element with attributes will be inferred as a table.</span></span> <span data-ttu-id="4f8d2-116">Los atributos de dicho elemento se deducirán como columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-116">The attributes of that element will then be inferred as columns for the table.</span></span> <span data-ttu-id="4f8d2-117">El **ColumnMapping** propiedad de las columnas se establecerá en **MappingType.Attribute**para asegurarse de que los nombres de columna se escribirán como atributos si el esquema se vuelve a escribir XML.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-117">The **ColumnMapping** property of the columns will be set to **MappingType.Attribute**, to ensure that the column names will be written as attributes if the schema is written back to XML.</span></span> <span data-ttu-id="4f8d2-118">Los valores de los atributos se almacenan en una fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-118">The values of the attributes are stored in a row in the table.</span></span> <span data-ttu-id="4f8d2-119">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="4f8d2-119">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="4f8d2-120">El proceso de inferencia producirá una tabla denominada **Element1** con dos columnas, **attr1** y **attr2**.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-120">The inference process will produce a table named **Element1** with two columns, **attr1** and **attr2**.</span></span> <span data-ttu-id="4f8d2-121">El **ColumnMapping** propiedad de ambas columnas se establecerá en **MappingType.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-121">The **ColumnMapping** property of both columns will be set to **MappingType.Attribute**.</span></span>  
  
 <span data-ttu-id="4f8d2-122">**Conjunto de datos:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="4f8d2-122">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="4f8d2-123">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="4f8d2-123">**Table:** Element1</span></span>  
  
|<span data-ttu-id="4f8d2-124">attr1</span><span class="sxs-lookup"><span data-stu-id="4f8d2-124">attr1</span></span>|<span data-ttu-id="4f8d2-125">attr2</span><span class="sxs-lookup"><span data-stu-id="4f8d2-125">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="4f8d2-126">value1</span><span class="sxs-lookup"><span data-stu-id="4f8d2-126">value1</span></span>|<span data-ttu-id="4f8d2-127">value2</span><span class="sxs-lookup"><span data-stu-id="4f8d2-127">value2</span></span>|  
  
## <a name="elements-without-attributes-or-child-elements"></a><span data-ttu-id="4f8d2-128">Elementos sin atributos o elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4f8d2-128">Elements Without Attributes or Child Elements</span></span>  
 <span data-ttu-id="4f8d2-129">Si un elemento no tiene elementos secundarios o atributos, se deducirá como una columna.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-129">If an element has no child elements or attributes, it will be inferred as a column.</span></span> <span data-ttu-id="4f8d2-130">El **ColumnMapping** propiedad de la columna se establecerá en **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-130">The **ColumnMapping** property of the column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="4f8d2-131">El texto de los elementos secundarios se almacena en una fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-131">The text for child elements is stored in a row in the table.</span></span> <span data-ttu-id="4f8d2-132">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="4f8d2-132">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="4f8d2-133">El proceso de inferencia producirá una tabla denominada **Element1** con dos columnas, **ChildElement1** y **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-133">The inference process will produce a table named **Element1** with two columns, **ChildElement1** and **ChildElement2**.</span></span> <span data-ttu-id="4f8d2-134">El **ColumnMapping** propiedad de ambas columnas se establecerá en **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="4f8d2-134">The **ColumnMapping** property of both columns will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="4f8d2-135">**Conjunto de datos:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="4f8d2-135">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="4f8d2-136">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="4f8d2-136">**Table:** Element1</span></span>  
  
|<span data-ttu-id="4f8d2-137">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="4f8d2-137">ChildElement1</span></span>|<span data-ttu-id="4f8d2-138">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="4f8d2-138">ChildElement2</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="4f8d2-139">Text1</span><span class="sxs-lookup"><span data-stu-id="4f8d2-139">Text1</span></span>|<span data-ttu-id="4f8d2-140">Text2</span><span class="sxs-lookup"><span data-stu-id="4f8d2-140">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f8d2-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f8d2-141">See Also</span></span>  
 [<span data-ttu-id="4f8d2-142">Inferencia de una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="4f8d2-142">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="4f8d2-143">Carga de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="4f8d2-143">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="4f8d2-144">Carga de información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="4f8d2-144">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="4f8d2-145">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="4f8d2-145">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="4f8d2-146">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="4f8d2-146">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="4f8d2-147">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="4f8d2-147">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

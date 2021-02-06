---
description: Más información acerca de cómo deducir columnas
title: Inferir columnas
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: 528d4ea20260b5f1fbf30536eafcaec8c5f9215a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652255"
---
# <a name="inferring-columns"></a><span data-ttu-id="acd7c-103">Inferir columnas</span><span class="sxs-lookup"><span data-stu-id="acd7c-103">Inferring Columns</span></span>

<span data-ttu-id="acd7c-104">Una vez que ADO.NET determina a partir de un documento XML los elementos que se van a inferir como tablas para un <xref:System.Data.DataSet>, se deducen las columnas para dichas tablas.</span><span class="sxs-lookup"><span data-stu-id="acd7c-104">After ADO.NET has determined from an XML document which elements to infer as tables for a <xref:System.Data.DataSet>, it then infers the columns for those tables.</span></span> <span data-ttu-id="acd7c-105">ADO.NET 2,0 presentó un nuevo motor de inferencia de esquemas que deduce un tipo de datos fuertemente tipado para cada elemento **simpleType** .</span><span class="sxs-lookup"><span data-stu-id="acd7c-105">ADO.NET 2.0 introduced a new schema inference engine that infers a strongly typed data type for each **simpleType** element.</span></span> <span data-ttu-id="acd7c-106">En versiones anteriores, el tipo de datos de un elemento **simpleType** deducido siempre era **xsd: String**.</span><span class="sxs-lookup"><span data-stu-id="acd7c-106">In previous versions, the data type of an inferred **simpleType** element was always **xsd:string**.</span></span>  
  
## <a name="migration-and-backward-compatibility"></a><span data-ttu-id="acd7c-107">Migración y compatibilidad con versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="acd7c-107">Migration and Backward Compatibility</span></span>  

 <span data-ttu-id="acd7c-108">El método **ReadXml** toma un argumento de tipo **InferSchema**.</span><span class="sxs-lookup"><span data-stu-id="acd7c-108">The **ReadXml** method takes an argument of type **InferSchema**.</span></span> <span data-ttu-id="acd7c-109">Este argumento le permite especificar un comportamiento de inferencia compatible con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="acd7c-109">This argument allows you to specify inference behavior compatible with previous versions.</span></span> <span data-ttu-id="acd7c-110">En la tabla siguiente se muestran los valores disponibles para la enumeración **InferSchema** .</span><span class="sxs-lookup"><span data-stu-id="acd7c-110">The available values for the **InferSchema** enumeration are shown in the following table.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 <span data-ttu-id="acd7c-111">Proporciona compatibilidad con versiones anteriores al deducir siempre un tipo simple como <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="acd7c-111">Provides backward compatibility by always inferring a simple type as <xref:System.String>.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 <span data-ttu-id="acd7c-112">Infiere un tipo de datos fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="acd7c-112">Infers a strongly typed data type.</span></span> <span data-ttu-id="acd7c-113">Inicia una excepción si se utiliza con una <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="acd7c-113">Throws an exception if used with a <xref:System.Data.DataTable>.</span></span>  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 <span data-ttu-id="acd7c-114">Omite cualquier esquema alineado y lee los datos del esquema del <xref:System.Data.DataSet> existente.</span><span class="sxs-lookup"><span data-stu-id="acd7c-114">Ignores any inline schema and reads data into the existing <xref:System.Data.DataSet> schema.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="acd7c-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="acd7c-115">Attributes</span></span>  

 <span data-ttu-id="acd7c-116">Como se define en [inferencia de tablas](inferring-tables.md), un elemento con atributos se deduce como una tabla.</span><span class="sxs-lookup"><span data-stu-id="acd7c-116">As defined in [Inferring Tables](inferring-tables.md), an element with attributes will be inferred as a table.</span></span> <span data-ttu-id="acd7c-117">Los atributos de dicho elemento se deducirán como columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="acd7c-117">The attributes of that element will then be inferred as columns for the table.</span></span> <span data-ttu-id="acd7c-118">La propiedad **ColumnMapping** de las columnas se establecerá en **MappingType. Attribute** para asegurarse de que los nombres de columna se escribirán como atributos si el esquema se vuelve a escribir en XML.</span><span class="sxs-lookup"><span data-stu-id="acd7c-118">The **ColumnMapping** property of the columns will be set to **MappingType.Attribute**, to ensure that the column names will be written as attributes if the schema is written back to XML.</span></span> <span data-ttu-id="acd7c-119">Los valores de los atributos se almacenan en una fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="acd7c-119">The values of the attributes are stored in a row in the table.</span></span> <span data-ttu-id="acd7c-120">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="acd7c-120">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="acd7c-121">El proceso de inferencia producirá una tabla denominada **Element1** con dos columnas, **attr1** y **attr2**.</span><span class="sxs-lookup"><span data-stu-id="acd7c-121">The inference process will produce a table named **Element1** with two columns, **attr1** and **attr2**.</span></span> <span data-ttu-id="acd7c-122">La propiedad **ColumnMapping** de ambas columnas se establecerá en **MappingType. Attribute**.</span><span class="sxs-lookup"><span data-stu-id="acd7c-122">The **ColumnMapping** property of both columns will be set to **MappingType.Attribute**.</span></span>  
  
 <span data-ttu-id="acd7c-123">**Conjunto** de los: DocumentElement</span><span class="sxs-lookup"><span data-stu-id="acd7c-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="acd7c-124">**Tabla:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="acd7c-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="acd7c-125">attr1</span><span class="sxs-lookup"><span data-stu-id="acd7c-125">attr1</span></span>|<span data-ttu-id="acd7c-126">attr2</span><span class="sxs-lookup"><span data-stu-id="acd7c-126">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="acd7c-127">value1</span><span class="sxs-lookup"><span data-stu-id="acd7c-127">value1</span></span>|<span data-ttu-id="acd7c-128">value2</span><span class="sxs-lookup"><span data-stu-id="acd7c-128">value2</span></span>|  
  
## <a name="elements-without-attributes-or-child-elements"></a><span data-ttu-id="acd7c-129">Elementos sin atributos o elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="acd7c-129">Elements Without Attributes or Child Elements</span></span>  

 <span data-ttu-id="acd7c-130">Si un elemento no tiene elementos secundarios o atributos, se deducirá como una columna.</span><span class="sxs-lookup"><span data-stu-id="acd7c-130">If an element has no child elements or attributes, it will be inferred as a column.</span></span> <span data-ttu-id="acd7c-131">La propiedad **ColumnMapping** de la columna se establecerá en **MappingType. Element**.</span><span class="sxs-lookup"><span data-stu-id="acd7c-131">The **ColumnMapping** property of the column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="acd7c-132">El texto de los elementos secundarios se almacena en una fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="acd7c-132">The text for child elements is stored in a row in the table.</span></span> <span data-ttu-id="acd7c-133">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="acd7c-133">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="acd7c-134">El proceso de inferencia producirá una tabla denominada **Element1** con dos columnas, **ChildElement1** y **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="acd7c-134">The inference process will produce a table named **Element1** with two columns, **ChildElement1** and **ChildElement2**.</span></span> <span data-ttu-id="acd7c-135">La propiedad **ColumnMapping** de ambas columnas se establecerá en **MappingType. Element**.</span><span class="sxs-lookup"><span data-stu-id="acd7c-135">The **ColumnMapping** property of both columns will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="acd7c-136">**Conjunto** de los: DocumentElement</span><span class="sxs-lookup"><span data-stu-id="acd7c-136">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="acd7c-137">**Tabla:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="acd7c-137">**Table:** Element1</span></span>  
  
|<span data-ttu-id="acd7c-138">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="acd7c-138">ChildElement1</span></span>|<span data-ttu-id="acd7c-139">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="acd7c-139">ChildElement2</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="acd7c-140">Text1</span><span class="sxs-lookup"><span data-stu-id="acd7c-140">Text1</span></span>|<span data-ttu-id="acd7c-141">Text2</span><span class="sxs-lookup"><span data-stu-id="acd7c-141">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="acd7c-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="acd7c-142">See also</span></span>

- [<span data-ttu-id="acd7c-143">Inferir una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="acd7c-143">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="acd7c-144">Cargar un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="acd7c-144">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="acd7c-145">Cargar información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="acd7c-145">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="acd7c-146">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="acd7c-146">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="acd7c-147">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="acd7c-147">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="acd7c-148">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="acd7c-148">ADO.NET Overview</span></span>](../ado-net-overview.md)

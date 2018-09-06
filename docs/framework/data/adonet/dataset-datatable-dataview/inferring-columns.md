---
title: Inferir columnas
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: 56de4b4d6cf704473ec46957625ad1c376f595c2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891358"
---
# <a name="inferring-columns"></a><span data-ttu-id="bd5a9-102">Inferir columnas</span><span class="sxs-lookup"><span data-stu-id="bd5a9-102">Inferring Columns</span></span>
<span data-ttu-id="bd5a9-103">Una vez que ADO.NET determina a partir de un documento XML los elementos que se van a inferir como tablas para un <xref:System.Data.DataSet>, se deducen las columnas para dichas tablas.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-103">After ADO.NET has determined from an XML document which elements to infer as tables for a <xref:System.Data.DataSet>, it then infers the columns for those tables.</span></span> <span data-ttu-id="bd5a9-104">ADO.NET 2.0 incorporó un nuevo motor de inferencia de esquemas que deduce un tipo de datos fuertemente tipado para cada **simpleType** elemento.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-104">ADO.NET 2.0 introduced a new schema inference engine that infers a strongly typed data type for each **simpleType** element.</span></span> <span data-ttu-id="bd5a9-105">En versiones anteriores, el tipo de datos de un deducido **simpleType** elemento siempre ha sido **xsd: String**.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-105">In previous versions, the data type of an inferred **simpleType** element was always **xsd:string**.</span></span>  
  
## <a name="migration-and-backward-compatibility"></a><span data-ttu-id="bd5a9-106">Migración y compatibilidad con versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="bd5a9-106">Migration and Backward Compatibility</span></span>  
 <span data-ttu-id="bd5a9-107">El **ReadXml** método toma un argumento de tipo **InferSchema**.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-107">The **ReadXml** method takes an argument of type **InferSchema**.</span></span> <span data-ttu-id="bd5a9-108">Este argumento le permite especificar un comportamiento de inferencia compatible con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-108">This argument allows you to specify inference behavior compatible with previous versions.</span></span> <span data-ttu-id="bd5a9-109">Los valores disponibles para el **InferSchema** enumeración se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-109">The available values for the **InferSchema** enumeration are shown in the following table.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 <span data-ttu-id="bd5a9-110">Proporciona compatibilidad con versiones anteriores al deducir siempre un tipo simple como <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-110">Provides backward compatibility by always inferring a simple type as <xref:System.String>.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 <span data-ttu-id="bd5a9-111">Infiere un tipo de datos fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-111">Infers a strongly typed data type.</span></span> <span data-ttu-id="bd5a9-112">Inicia una excepción si se utiliza con una <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-112">Throws an exception if used with a <xref:System.Data.DataTable>.</span></span>  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 <span data-ttu-id="bd5a9-113">Omite cualquier esquema alineado y lee los datos del esquema del <xref:System.Data.DataSet> existente.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-113">Ignores any inline schema and reads data into the existing <xref:System.Data.DataSet> schema.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="bd5a9-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="bd5a9-114">Attributes</span></span>  
 <span data-ttu-id="bd5a9-115">Tal como se define en [deducir tablas](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), un elemento con atributos se deducirá como una tabla.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-115">As defined in [Inferring Tables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), an element with attributes will be inferred as a table.</span></span> <span data-ttu-id="bd5a9-116">Los atributos de dicho elemento se deducirán como columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-116">The attributes of that element will then be inferred as columns for the table.</span></span> <span data-ttu-id="bd5a9-117">El **ColumnMapping** propiedad de las columnas se establecerá en **MappingType.Attribute**para asegurarse de que los nombres de columna se escribirán como atributos si el esquema se escribe en XML.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-117">The **ColumnMapping** property of the columns will be set to **MappingType.Attribute**, to ensure that the column names will be written as attributes if the schema is written back to XML.</span></span> <span data-ttu-id="bd5a9-118">Los valores de los atributos se almacenan en una fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-118">The values of the attributes are stored in a row in the table.</span></span> <span data-ttu-id="bd5a9-119">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="bd5a9-119">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="bd5a9-120">El proceso de inferencia producirá una tabla denominada **Element1** con dos columnas, **attr1** y **attr2**.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-120">The inference process will produce a table named **Element1** with two columns, **attr1** and **attr2**.</span></span> <span data-ttu-id="bd5a9-121">El **ColumnMapping** propiedad de ambas columnas se establecerá en **MappingType.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-121">The **ColumnMapping** property of both columns will be set to **MappingType.Attribute**.</span></span>  
  
 <span data-ttu-id="bd5a9-122">**Conjunto de datos:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="bd5a9-122">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="bd5a9-123">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="bd5a9-123">**Table:** Element1</span></span>  
  
|<span data-ttu-id="bd5a9-124">attr1</span><span class="sxs-lookup"><span data-stu-id="bd5a9-124">attr1</span></span>|<span data-ttu-id="bd5a9-125">attr2</span><span class="sxs-lookup"><span data-stu-id="bd5a9-125">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="bd5a9-126">value1</span><span class="sxs-lookup"><span data-stu-id="bd5a9-126">value1</span></span>|<span data-ttu-id="bd5a9-127">value2</span><span class="sxs-lookup"><span data-stu-id="bd5a9-127">value2</span></span>|  
  
## <a name="elements-without-attributes-or-child-elements"></a><span data-ttu-id="bd5a9-128">Elementos sin atributos o elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bd5a9-128">Elements Without Attributes or Child Elements</span></span>  
 <span data-ttu-id="bd5a9-129">Si un elemento no tiene elementos secundarios o atributos, se deducirá como una columna.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-129">If an element has no child elements or attributes, it will be inferred as a column.</span></span> <span data-ttu-id="bd5a9-130">El **ColumnMapping** propiedad de la columna se establecerá en **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-130">The **ColumnMapping** property of the column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="bd5a9-131">El texto de los elementos secundarios se almacena en una fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-131">The text for child elements is stored in a row in the table.</span></span> <span data-ttu-id="bd5a9-132">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="bd5a9-132">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="bd5a9-133">El proceso de inferencia producirá una tabla denominada **Element1** con dos columnas, **ChildElement1** y **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-133">The inference process will produce a table named **Element1** with two columns, **ChildElement1** and **ChildElement2**.</span></span> <span data-ttu-id="bd5a9-134">El **ColumnMapping** propiedad de ambas columnas se establecerá en **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="bd5a9-134">The **ColumnMapping** property of both columns will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="bd5a9-135">**Conjunto de datos:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="bd5a9-135">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="bd5a9-136">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="bd5a9-136">**Table:** Element1</span></span>  
  
|<span data-ttu-id="bd5a9-137">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="bd5a9-137">ChildElement1</span></span>|<span data-ttu-id="bd5a9-138">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="bd5a9-138">ChildElement2</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="bd5a9-139">Text1</span><span class="sxs-lookup"><span data-stu-id="bd5a9-139">Text1</span></span>|<span data-ttu-id="bd5a9-140">Text2</span><span class="sxs-lookup"><span data-stu-id="bd5a9-140">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd5a9-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd5a9-141">See Also</span></span>  
 [<span data-ttu-id="bd5a9-142">Inferencia de una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="bd5a9-142">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="bd5a9-143">Carga de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="bd5a9-143">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="bd5a9-144">Carga de información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="bd5a9-144">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="bd5a9-145">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="bd5a9-145">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="bd5a9-146">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="bd5a9-146">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="bd5a9-147">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="bd5a9-147">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

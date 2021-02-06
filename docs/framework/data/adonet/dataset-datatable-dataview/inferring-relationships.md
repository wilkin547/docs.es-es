---
description: 'Más información sobre: inferir relaciones'
title: Inferir relaciones
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: a117581d512c1427c638ea862169ab3c7623d783
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652151"
---
# <a name="inferring-relationships"></a><span data-ttu-id="57658-103">Inferir relaciones</span><span class="sxs-lookup"><span data-stu-id="57658-103">Inferring Relationships</span></span>

<span data-ttu-id="57658-104">Si un elemento que se deduce como una tabla tiene un elemento secundario que también se deduce como una tabla, se creará una <xref:System.Data.DataRelation> entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="57658-104">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="57658-105">Se agregará una nueva columna con el nombre **ParentTableName_Id** a la tabla creada para el elemento primario y a la tabla creada para el elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="57658-105">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="57658-106">La propiedad **ColumnMapping** de esta columna de identidad se establecerá en **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="57658-106">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="57658-107">La columna será una clave principal de incremento automático para la tabla primaria y se utilizará para la **DataRelation** entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="57658-107">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="57658-108">El tipo de datos de la columna de identidad agregada será **System. Int32**, a diferencia del tipo de datos de todas las demás columnas inferidos, que es **System. String**.</span><span class="sxs-lookup"><span data-stu-id="57658-108">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="57658-109"><xref:System.Data.ForeignKeyConstraint>También se   =  creará una con la **cascada** de DeleteRule utilizando la nueva columna en las tablas primaria y secundaria.</span><span class="sxs-lookup"><span data-stu-id="57658-109">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="57658-110">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="57658-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="57658-111">El proceso de inferencia producirá dos tablas: **Element1** y **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="57658-111">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="57658-112">La tabla **Element1** tendrá dos columnas: **Element1_Id** y **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="57658-112">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="57658-113">La propiedad **ColumnMapping** de la columna **Element1_Id** se establecerá en **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="57658-113">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="57658-114">La propiedad **ColumnMapping** de la columna **ChildElement2** se establecerá en **MappingType. Element**.</span><span class="sxs-lookup"><span data-stu-id="57658-114">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="57658-115">La columna de **Element1_Id** se establecerá como la clave principal de la tabla **Element1** .</span><span class="sxs-lookup"><span data-stu-id="57658-115">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="57658-116">La tabla **ChildElement1** tendrá tres columnas: **attr1**, **attr2** y **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="57658-116">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="57658-117">La propiedad **ColumnMapping** de las columnas **attr1** y **Attr2** se establecerá en **MappingType. Attribute**.</span><span class="sxs-lookup"><span data-stu-id="57658-117">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="57658-118">La propiedad **ColumnMapping** de la columna **Element1_Id** se establecerá en **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="57658-118">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="57658-119">Se creará una **DataRelation** y **ForeignKeyConstraint** utilizando el **Element1_Id** columnas de ambas tablas.</span><span class="sxs-lookup"><span data-stu-id="57658-119">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="57658-120">**Conjunto** de los: DocumentElement</span><span class="sxs-lookup"><span data-stu-id="57658-120">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="57658-121">**Tabla:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="57658-121">**Table:** Element1</span></span>  
  
|<span data-ttu-id="57658-122">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="57658-122">Element1_Id</span></span>|<span data-ttu-id="57658-123">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="57658-123">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="57658-124">0</span><span class="sxs-lookup"><span data-stu-id="57658-124">0</span></span>|<span data-ttu-id="57658-125">Text2</span><span class="sxs-lookup"><span data-stu-id="57658-125">Text2</span></span>|  
  
 <span data-ttu-id="57658-126">**Tabla:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="57658-126">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="57658-127">attr1</span><span class="sxs-lookup"><span data-stu-id="57658-127">attr1</span></span>|<span data-ttu-id="57658-128">attr2</span><span class="sxs-lookup"><span data-stu-id="57658-128">attr2</span></span>|<span data-ttu-id="57658-129">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="57658-129">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="57658-130">value1</span><span class="sxs-lookup"><span data-stu-id="57658-130">value1</span></span>|<span data-ttu-id="57658-131">value2</span><span class="sxs-lookup"><span data-stu-id="57658-131">value2</span></span>|<span data-ttu-id="57658-132">0</span><span class="sxs-lookup"><span data-stu-id="57658-132">0</span></span>|  
  
 <span data-ttu-id="57658-133">**DataRelation:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="57658-133">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="57658-134">**ParentTable:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="57658-134">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="57658-135">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="57658-135">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="57658-136">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="57658-136">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="57658-137">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="57658-137">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="57658-138">**Anidado:** Reales</span><span class="sxs-lookup"><span data-stu-id="57658-138">**Nested:** True</span></span>  
  
 <span data-ttu-id="57658-139">**ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="57658-139">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="57658-140">**Columna:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="57658-140">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="57658-141">**ParentTable:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="57658-141">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="57658-142">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="57658-142">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="57658-143">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="57658-143">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="57658-144">**AcceptRejectRule:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="57658-144">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57658-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="57658-145">See also</span></span>

- [<span data-ttu-id="57658-146">Inferir una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="57658-146">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="57658-147">Cargar un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="57658-147">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="57658-148">Cargar información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="57658-148">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="57658-149">Anidar objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="57658-149">Nesting DataRelations</span></span>](nesting-datarelations.md)
- [<span data-ttu-id="57658-150">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="57658-150">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="57658-151">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="57658-151">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="57658-152">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="57658-152">ADO.NET Overview</span></span>](../ado-net-overview.md)

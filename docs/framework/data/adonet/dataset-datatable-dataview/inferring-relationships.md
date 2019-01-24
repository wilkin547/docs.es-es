---
title: Inferir relaciones
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 2d25160b8dae8b8dc883abb589551782925ca325
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536289"
---
# <a name="inferring-relationships"></a><span data-ttu-id="f83e7-102">Inferir relaciones</span><span class="sxs-lookup"><span data-stu-id="f83e7-102">Inferring Relationships</span></span>
<span data-ttu-id="f83e7-103">Si un elemento que se deduce como una tabla tiene un elemento secundario que también se deduce como una tabla, se creará una <xref:System.Data.DataRelation> entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="f83e7-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="f83e7-104">Una nueva columna con el nombre de **ParentTableName_Id** se agregará a la tabla creada para el elemento primario y la tabla creada para el elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="f83e7-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="f83e7-105">El **ColumnMapping** propiedad de esta columna de identidad se establecerá en **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="f83e7-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="f83e7-106">La columna será una clave principal de incremento automático para la tabla primaria y se usará para la **DataRelation** entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="f83e7-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="f83e7-107">El tipo de datos de la columna de identidad agregada será **System.Int32**, a diferencia del tipo de datos de todas las demás columnas deducidas, que es **System.String**.</span><span class="sxs-lookup"><span data-stu-id="f83e7-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="f83e7-108">Un <xref:System.Data.ForeignKeyConstraint> con **DeleteRule** = **Cascade** también se creará con la nueva columna en el elemento primario y secundario de las tablas.</span><span class="sxs-lookup"><span data-stu-id="f83e7-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="f83e7-109">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="f83e7-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="f83e7-110">El proceso de inferencia producirá dos tablas: **Element1** y **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="f83e7-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="f83e7-111">El **Element1** tabla tendrá dos columnas: **Element1_Id** y **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="f83e7-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="f83e7-112">El **ColumnMapping** propiedad de la **Element1_Id** columna se establecerá en **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="f83e7-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="f83e7-113">El **ColumnMapping** propiedad de la **ChildElement2** columna se establecerá en **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="f83e7-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="f83e7-114">El **Element1_Id** columna se establecerá como la clave principal de la **Element1** tabla.</span><span class="sxs-lookup"><span data-stu-id="f83e7-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="f83e7-115">El **ChildElement1** tabla tendrá tres columnas: **attr1**, **attr2** y **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="f83e7-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="f83e7-116">El **ColumnMapping** propiedad para el **attr1** y **attr2** columnas se establecerá en **MappingType.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="f83e7-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="f83e7-117">El **ColumnMapping** propiedad de la **Element1_Id** columna se establecerá en **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="f83e7-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="f83e7-118">Un **DataRelation** y **ForeignKeyConstraint** , se creará con el **Element1_Id** columnas de ambas tablas.</span><span class="sxs-lookup"><span data-stu-id="f83e7-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="f83e7-119">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="f83e7-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="f83e7-120">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="f83e7-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="f83e7-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="f83e7-121">Element1_Id</span></span>|<span data-ttu-id="f83e7-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="f83e7-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="f83e7-123">0</span><span class="sxs-lookup"><span data-stu-id="f83e7-123">0</span></span>|<span data-ttu-id="f83e7-124">Text2</span><span class="sxs-lookup"><span data-stu-id="f83e7-124">Text2</span></span>|  
  
 <span data-ttu-id="f83e7-125">**Tabla:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="f83e7-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="f83e7-126">attr1</span><span class="sxs-lookup"><span data-stu-id="f83e7-126">attr1</span></span>|<span data-ttu-id="f83e7-127">attr2</span><span class="sxs-lookup"><span data-stu-id="f83e7-127">attr2</span></span>|<span data-ttu-id="f83e7-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="f83e7-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="f83e7-129">value1</span><span class="sxs-lookup"><span data-stu-id="f83e7-129">value1</span></span>|<span data-ttu-id="f83e7-130">value2</span><span class="sxs-lookup"><span data-stu-id="f83e7-130">value2</span></span>|<span data-ttu-id="f83e7-131">0</span><span class="sxs-lookup"><span data-stu-id="f83e7-131">0</span></span>|  
  
 <span data-ttu-id="f83e7-132">**DataRelation:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="f83e7-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="f83e7-133">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="f83e7-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="f83e7-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="f83e7-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="f83e7-135">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="f83e7-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="f83e7-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="f83e7-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="f83e7-137">**Anidado:** True</span><span class="sxs-lookup"><span data-stu-id="f83e7-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="f83e7-138">**ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="f83e7-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="f83e7-139">**Columna:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="f83e7-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="f83e7-140">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="f83e7-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="f83e7-141">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="f83e7-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="f83e7-142">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="f83e7-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="f83e7-143">**AcceptRejectRule:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="f83e7-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f83e7-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="f83e7-144">See also</span></span>
- [<span data-ttu-id="f83e7-145">Inferencia de una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="f83e7-145">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="f83e7-146">Carga de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="f83e7-146">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="f83e7-147">Carga de información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="f83e7-147">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="f83e7-148">Anidado de objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="f83e7-148">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)
- [<span data-ttu-id="f83e7-149">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="f83e7-149">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="f83e7-150">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="f83e7-150">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="f83e7-151">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="f83e7-151">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

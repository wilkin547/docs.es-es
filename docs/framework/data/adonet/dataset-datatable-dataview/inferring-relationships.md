---
title: Inferir relaciones
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 9833966fa5a16bef70a6ae2b9ca618fde0e05fbb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759041"
---
# <a name="inferring-relationships"></a><span data-ttu-id="8a151-102">Inferir relaciones</span><span class="sxs-lookup"><span data-stu-id="8a151-102">Inferring Relationships</span></span>
<span data-ttu-id="8a151-103">Si un elemento que se deduce como una tabla tiene un elemento secundario que también se deduce como una tabla, se creará una <xref:System.Data.DataRelation> entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="8a151-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="8a151-104">Una nueva columna con el nombre de **ParentTableName_Id** se agregará a la tabla creada para el elemento primario y de la tabla creada para el elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="8a151-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="8a151-105">El **ColumnMapping** propiedad de esta columna de identidad se establecerá en **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="8a151-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="8a151-106">La columna será una clave principal de incremento automático para la tabla primaria y se utilizará para la **DataRelation** entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="8a151-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="8a151-107">El tipo de datos de la columna de identidad agregada será **System.Int32**, a diferencia del tipo de datos de todas las demás columnas deducidas, que es **System.String**.</span><span class="sxs-lookup"><span data-stu-id="8a151-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="8a151-108">A <xref:System.Data.ForeignKeyConstraint> con **DeleteRule** = **Cascade** también se creará con la nueva columna de tablas el elemento primario y el secundario.</span><span class="sxs-lookup"><span data-stu-id="8a151-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="8a151-109">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="8a151-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="8a151-110">El proceso de inferencia producirá dos tablas: **Element1** y **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="8a151-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="8a151-111">El **Element1** tabla tiene dos columnas: **Element1_Id** y **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="8a151-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="8a151-112">El **ColumnMapping** propiedad de la **Element1_Id** columna se establecerá en **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="8a151-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="8a151-113">El **ColumnMapping** propiedad de la **ChildElement2** columna se establecerá en **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="8a151-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="8a151-114">El **Element1_Id** columna se establecerá como la clave principal de la **Element1** tabla.</span><span class="sxs-lookup"><span data-stu-id="8a151-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="8a151-115">El **ChildElement1** tabla tendrá tres columnas: **attr1**, **attr2** y **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="8a151-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="8a151-116">El **ColumnMapping** propiedad para la **attr1** y **attr2** columnas se establecerá en **MappingType.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="8a151-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="8a151-117">El **ColumnMapping** propiedad de la **Element1_Id** columna se establecerá en **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="8a151-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="8a151-118">A **DataRelation** y **ForeignKeyConstraint** se creará usando la **Element1_Id** columnas de ambas tablas.</span><span class="sxs-lookup"><span data-stu-id="8a151-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="8a151-119">**Conjunto de datos:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="8a151-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="8a151-120">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="8a151-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="8a151-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="8a151-121">Element1_Id</span></span>|<span data-ttu-id="8a151-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="8a151-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="8a151-123">0</span><span class="sxs-lookup"><span data-stu-id="8a151-123">0</span></span>|<span data-ttu-id="8a151-124">Text2</span><span class="sxs-lookup"><span data-stu-id="8a151-124">Text2</span></span>|  
  
 <span data-ttu-id="8a151-125">**Tabla:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="8a151-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="8a151-126">attr1</span><span class="sxs-lookup"><span data-stu-id="8a151-126">attr1</span></span>|<span data-ttu-id="8a151-127">attr2</span><span class="sxs-lookup"><span data-stu-id="8a151-127">attr2</span></span>|<span data-ttu-id="8a151-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="8a151-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="8a151-129">value1</span><span class="sxs-lookup"><span data-stu-id="8a151-129">value1</span></span>|<span data-ttu-id="8a151-130">value2</span><span class="sxs-lookup"><span data-stu-id="8a151-130">value2</span></span>|<span data-ttu-id="8a151-131">0</span><span class="sxs-lookup"><span data-stu-id="8a151-131">0</span></span>|  
  
 <span data-ttu-id="8a151-132">**DataRelation:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="8a151-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="8a151-133">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="8a151-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="8a151-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="8a151-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="8a151-135">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="8a151-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="8a151-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="8a151-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="8a151-137">**Anidadas:** True</span><span class="sxs-lookup"><span data-stu-id="8a151-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="8a151-138">**ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="8a151-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="8a151-139">**Columna:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="8a151-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="8a151-140">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="8a151-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="8a151-141">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="8a151-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="8a151-142">**DeleteRule:** en cascada</span><span class="sxs-lookup"><span data-stu-id="8a151-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="8a151-143">**AcceptRejectRule:** ninguno</span><span class="sxs-lookup"><span data-stu-id="8a151-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a151-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a151-144">See Also</span></span>  
 [<span data-ttu-id="8a151-145">Inferencia de una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="8a151-145">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="8a151-146">Carga de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="8a151-146">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="8a151-147">Carga de información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="8a151-147">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="8a151-148">Anidado de objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="8a151-148">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [<span data-ttu-id="8a151-149">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="8a151-149">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="8a151-150">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="8a151-150">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="8a151-151">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="8a151-151">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

---
title: Inferir relaciones
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: ee691eee95c34afdb6374cdd7448d4b44ece3055
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177571"
---
# <a name="inferring-relationships"></a><span data-ttu-id="d145c-102">Inferir relaciones</span><span class="sxs-lookup"><span data-stu-id="d145c-102">Inferring Relationships</span></span>

<span data-ttu-id="d145c-103">Si un elemento que se deduce como una tabla tiene un elemento secundario que también se deduce como una tabla, se creará una <xref:System.Data.DataRelation> entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="d145c-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="d145c-104">Se agregará una nueva columna con el nombre **ParentTableName_Id** a la tabla creada para el elemento primario y a la tabla creada para el elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="d145c-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="d145c-105">La propiedad **ColumnMapping** de esta columna de identidad se establecerá en **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="d145c-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="d145c-106">La columna será una clave principal de incremento automático para la tabla primaria y se utilizará para la **DataRelation** entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="d145c-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="d145c-107">El tipo de datos de la columna de identidad agregada será **System. Int32**, a diferencia del tipo de datos de todas las demás columnas inferidos, que es **System. String**.</span><span class="sxs-lookup"><span data-stu-id="d145c-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="d145c-108"><xref:System.Data.ForeignKeyConstraint>También se **DeleteRule**  =  creará una con la**cascada** de DeleteRule utilizando la nueva columna en las tablas primaria y secundaria.</span><span class="sxs-lookup"><span data-stu-id="d145c-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="d145c-109">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="d145c-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="d145c-110">El proceso de inferencia producirá dos tablas: **Element1** y **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="d145c-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="d145c-111">La tabla **Element1** tendrá dos columnas: **Element1_Id** y **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="d145c-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="d145c-112">La propiedad **ColumnMapping** de la columna **Element1_Id** se establecerá en **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="d145c-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="d145c-113">La propiedad **ColumnMapping** de la columna **ChildElement2** se establecerá en **MappingType. Element**.</span><span class="sxs-lookup"><span data-stu-id="d145c-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="d145c-114">La columna de **Element1_Id** se establecerá como la clave principal de la tabla **Element1** .</span><span class="sxs-lookup"><span data-stu-id="d145c-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="d145c-115">La tabla **ChildElement1** tendrá tres columnas: **attr1**, **attr2** y **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="d145c-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="d145c-116">La propiedad **ColumnMapping** de las columnas **attr1** y **Attr2** se establecerá en **MappingType. Attribute**.</span><span class="sxs-lookup"><span data-stu-id="d145c-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="d145c-117">La propiedad **ColumnMapping** de la columna **Element1_Id** se establecerá en **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="d145c-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="d145c-118">Se creará una **DataRelation** y **ForeignKeyConstraint** utilizando el **Element1_Id** columnas de ambas tablas.</span><span class="sxs-lookup"><span data-stu-id="d145c-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="d145c-119">**Conjunto** de los: DocumentElement</span><span class="sxs-lookup"><span data-stu-id="d145c-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="d145c-120">**Tabla:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="d145c-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="d145c-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="d145c-121">Element1_Id</span></span>|<span data-ttu-id="d145c-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="d145c-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="d145c-123">0</span><span class="sxs-lookup"><span data-stu-id="d145c-123">0</span></span>|<span data-ttu-id="d145c-124">Text2</span><span class="sxs-lookup"><span data-stu-id="d145c-124">Text2</span></span>|  
  
 <span data-ttu-id="d145c-125">**Tabla:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="d145c-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="d145c-126">attr1</span><span class="sxs-lookup"><span data-stu-id="d145c-126">attr1</span></span>|<span data-ttu-id="d145c-127">attr2</span><span class="sxs-lookup"><span data-stu-id="d145c-127">attr2</span></span>|<span data-ttu-id="d145c-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="d145c-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="d145c-129">value1</span><span class="sxs-lookup"><span data-stu-id="d145c-129">value1</span></span>|<span data-ttu-id="d145c-130">value2</span><span class="sxs-lookup"><span data-stu-id="d145c-130">value2</span></span>|<span data-ttu-id="d145c-131">0</span><span class="sxs-lookup"><span data-stu-id="d145c-131">0</span></span>|  
  
 <span data-ttu-id="d145c-132">**DataRelation:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="d145c-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="d145c-133">**ParentTable:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="d145c-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="d145c-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="d145c-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="d145c-135">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="d145c-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="d145c-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="d145c-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="d145c-137">**Anidado:** Reales</span><span class="sxs-lookup"><span data-stu-id="d145c-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="d145c-138">**ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="d145c-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="d145c-139">**Columna:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="d145c-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="d145c-140">**ParentTable:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="d145c-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="d145c-141">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="d145c-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="d145c-142">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="d145c-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="d145c-143">**AcceptRejectRule:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="d145c-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d145c-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d145c-144">See also</span></span>

- [<span data-ttu-id="d145c-145">Inferir una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="d145c-145">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="d145c-146">Cargar un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="d145c-146">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="d145c-147">Cargar información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="d145c-147">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="d145c-148">Anidar objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="d145c-148">Nesting DataRelations</span></span>](nesting-datarelations.md)
- [<span data-ttu-id="d145c-149">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="d145c-149">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="d145c-150">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="d145c-150">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="d145c-151">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d145c-151">ADO.NET Overview</span></span>](../ado-net-overview.md)

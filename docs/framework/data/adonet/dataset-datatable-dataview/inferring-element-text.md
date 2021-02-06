---
description: 'Más información sobre: inferir texto de elemento'
title: Inferir texto de elemento
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: 5d0d9b1b3bb6164cd3cf26b429a4c7d658ee4128
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652216"
---
# <a name="inferring-element-text"></a><span data-ttu-id="12afd-103">Inferir texto de elemento</span><span class="sxs-lookup"><span data-stu-id="12afd-103">Inferring Element Text</span></span>

<span data-ttu-id="12afd-104">Si un elemento contiene texto y no tiene ningún elemento secundario que se infiera como tabla (como elementos con atributos o elementos repetidos), se agregará una nueva columna con el nombre **TableName_Text** a la tabla que se infiere para el elemento.</span><span class="sxs-lookup"><span data-stu-id="12afd-104">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="12afd-105">El texto contenido en el elemento se agregará a una fila de la tabla y se almacenará en la nueva columna.</span><span class="sxs-lookup"><span data-stu-id="12afd-105">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="12afd-106">La propiedad **ColumnMapping** de la nueva columna se establecerá en **MappingType. SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="12afd-106">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="12afd-107">Por ejemplo, tomemos el siguiente código XML.</span><span class="sxs-lookup"><span data-stu-id="12afd-107">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="12afd-108">El proceso de inferencia producirá una tabla denominada **Element1** con dos columnas: **attr1** y **Element1_Text**.</span><span class="sxs-lookup"><span data-stu-id="12afd-108">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="12afd-109">La propiedad **ColumnMapping** de la columna **attr1** se establecerá en **MappingType. Attribute**.</span><span class="sxs-lookup"><span data-stu-id="12afd-109">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="12afd-110">La propiedad **ColumnMapping** de la columna **Element1_Text** se establecerá en **MappingType. SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="12afd-110">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="12afd-111">**Conjunto** de los: DocumentElement</span><span class="sxs-lookup"><span data-stu-id="12afd-111">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="12afd-112">**Tabla:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="12afd-112">**Table:** Element1</span></span>  
  
|<span data-ttu-id="12afd-113">attr1</span><span class="sxs-lookup"><span data-stu-id="12afd-113">attr1</span></span>|<span data-ttu-id="12afd-114">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="12afd-114">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="12afd-115">value1</span><span class="sxs-lookup"><span data-stu-id="12afd-115">value1</span></span>|<span data-ttu-id="12afd-116">Text1</span><span class="sxs-lookup"><span data-stu-id="12afd-116">Text1</span></span>|  
  
 <span data-ttu-id="12afd-117">Si un elemento contiene texto, pero también tiene elementos secundarios que contienen texto, no se agregará una columna a la tabla para almacenar el texto contenido en el elemento.</span><span class="sxs-lookup"><span data-stu-id="12afd-117">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="12afd-118">El texto contenido en el elemento se pasará por alto, mientras que el texto de los elementos secundarios se incluirá en una fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="12afd-118">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="12afd-119">Por ejemplo, tomemos el siguiente código XML.</span><span class="sxs-lookup"><span data-stu-id="12afd-119">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="12afd-120">El proceso de inferencia producirá una tabla denominada **Element1** con una columna denominada **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="12afd-120">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="12afd-121">El texto del elemento **ChildElement1** se incluirá en una fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="12afd-121">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="12afd-122">El otro texto se pasará por alto.</span><span class="sxs-lookup"><span data-stu-id="12afd-122">The other text will be ignored.</span></span> <span data-ttu-id="12afd-123">La propiedad **ColumnMapping** de la columna **ChildElement1** se establecerá en **MappingType. Element**.</span><span class="sxs-lookup"><span data-stu-id="12afd-123">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="12afd-124">**Conjunto** de los: DocumentElement</span><span class="sxs-lookup"><span data-stu-id="12afd-124">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="12afd-125">**Tabla:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="12afd-125">**Table:** Element1</span></span>  
  
|<span data-ttu-id="12afd-126">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="12afd-126">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="12afd-127">Text2</span><span class="sxs-lookup"><span data-stu-id="12afd-127">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12afd-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="12afd-128">See also</span></span>

- [<span data-ttu-id="12afd-129">Inferir una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="12afd-129">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="12afd-130">Cargar un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="12afd-130">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="12afd-131">Cargar información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="12afd-131">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="12afd-132">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="12afd-132">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="12afd-133">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="12afd-133">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="12afd-134">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="12afd-134">ADO.NET Overview</span></span>](../ado-net-overview.md)

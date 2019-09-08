---
title: Inferir texto de elemento
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: 3fdd110a14ddfd6065ed552171a8d76ef64e2fb5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784542"
---
# <a name="inferring-element-text"></a><span data-ttu-id="9ab83-102">Inferir texto de elemento</span><span class="sxs-lookup"><span data-stu-id="9ab83-102">Inferring Element Text</span></span>
<span data-ttu-id="9ab83-103">Si un elemento contiene texto y no tiene ningún elemento secundario que se infiera como tabla (como elementos con atributos o elementos repetidos), se agregará una nueva columna con el nombre **TableName_Text** a la tabla que se infiere para el elemento.</span><span class="sxs-lookup"><span data-stu-id="9ab83-103">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="9ab83-104">El texto contenido en el elemento se agregará a una fila de la tabla y se almacenará en la nueva columna.</span><span class="sxs-lookup"><span data-stu-id="9ab83-104">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="9ab83-105">La propiedad **ColumnMapping** de la nueva columna se establecerá en **MappingType. SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="9ab83-105">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="9ab83-106">Por ejemplo, tomemos el siguiente código XML.</span><span class="sxs-lookup"><span data-stu-id="9ab83-106">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="9ab83-107">El proceso de inferencia producirá una tabla denominada **Element1** con dos columnas: **attr1** y **Element1_Text**.</span><span class="sxs-lookup"><span data-stu-id="9ab83-107">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="9ab83-108">La propiedad **ColumnMapping** de la columna **attr1** se establecerá en **MappingType. Attribute**.</span><span class="sxs-lookup"><span data-stu-id="9ab83-108">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="9ab83-109">La propiedad **ColumnMapping** de la columna **Element1_Text** se establecerá en **MappingType. SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="9ab83-109">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="9ab83-110">**Authors1** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="9ab83-110">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="9ab83-111">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="9ab83-111">**Table:** Element1</span></span>  
  
|<span data-ttu-id="9ab83-112">attr1</span><span class="sxs-lookup"><span data-stu-id="9ab83-112">attr1</span></span>|<span data-ttu-id="9ab83-113">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="9ab83-113">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="9ab83-114">value1</span><span class="sxs-lookup"><span data-stu-id="9ab83-114">value1</span></span>|<span data-ttu-id="9ab83-115">Text1</span><span class="sxs-lookup"><span data-stu-id="9ab83-115">Text1</span></span>|  
  
 <span data-ttu-id="9ab83-116">Si un elemento contiene texto, pero también tiene elementos secundarios que contienen texto, no se agregará una columna a la tabla para almacenar el texto contenido en el elemento.</span><span class="sxs-lookup"><span data-stu-id="9ab83-116">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="9ab83-117">El texto contenido en el elemento se pasará por alto, mientras que el texto de los elementos secundarios se incluirá en una fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9ab83-117">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="9ab83-118">Por ejemplo, tomemos el siguiente código XML.</span><span class="sxs-lookup"><span data-stu-id="9ab83-118">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="9ab83-119">El proceso de inferencia producirá una tabla denominada **Element1** con una columna denominada **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="9ab83-119">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="9ab83-120">El texto del elemento **ChildElement1** se incluirá en una fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9ab83-120">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="9ab83-121">El otro texto se pasará por alto.</span><span class="sxs-lookup"><span data-stu-id="9ab83-121">The other text will be ignored.</span></span> <span data-ttu-id="9ab83-122">La propiedad **ColumnMapping** de la columna **ChildElement1** se establecerá en **MappingType. Element**.</span><span class="sxs-lookup"><span data-stu-id="9ab83-122">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="9ab83-123">**Authors1** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="9ab83-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="9ab83-124">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="9ab83-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="9ab83-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="9ab83-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="9ab83-126">Text2</span><span class="sxs-lookup"><span data-stu-id="9ab83-126">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ab83-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ab83-127">See also</span></span>

- [<span data-ttu-id="9ab83-128">Inferencia de una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="9ab83-128">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="9ab83-129">Carga de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="9ab83-129">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="9ab83-130">Carga de información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="9ab83-130">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="9ab83-131">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="9ab83-131">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="9ab83-132">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="9ab83-132">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="9ab83-133">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9ab83-133">ADO.NET Overview</span></span>](../ado-net-overview.md)

---
title: Inferir tablas
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 52ffd3fe90eb491dd01acf8538276cc828fdb309
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784485"
---
# <a name="inferring-tables"></a><span data-ttu-id="a151d-102">Inferir tablas</span><span class="sxs-lookup"><span data-stu-id="a151d-102">Inferring Tables</span></span>
<span data-ttu-id="a151d-103">Al deducir un esquema para un <xref:System.Data.DataSet> desde un documento XML, ADO.NET determina en primer lugar qué elementos XML representan tablas.</span><span class="sxs-lookup"><span data-stu-id="a151d-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="a151d-104">Las siguientes estructuras XML dan como resultado una tabla para el esquema del **conjunto** de elementos:</span><span class="sxs-lookup"><span data-stu-id="a151d-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="a151d-105">Elementos con atributos</span><span class="sxs-lookup"><span data-stu-id="a151d-105">Elements with attributes</span></span>  
  
- <span data-ttu-id="a151d-106">Elementos con elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a151d-106">Elements with child elements</span></span>  
  
- <span data-ttu-id="a151d-107">Elementos que se repiten</span><span class="sxs-lookup"><span data-stu-id="a151d-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="a151d-108">Elementos con atributos</span><span class="sxs-lookup"><span data-stu-id="a151d-108">Elements with Attributes</span></span>  
 <span data-ttu-id="a151d-109">Los elementos para los que se han especificado atributos se deducen como tablas.</span><span class="sxs-lookup"><span data-stu-id="a151d-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="a151d-110">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="a151d-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a151d-111">El proceso de inferencia produce una tabla denominada "Element1".</span><span class="sxs-lookup"><span data-stu-id="a151d-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="a151d-112">**Authors1** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a151d-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a151d-113">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="a151d-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a151d-114">attr1</span><span class="sxs-lookup"><span data-stu-id="a151d-114">attr1</span></span>|<span data-ttu-id="a151d-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="a151d-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="a151d-116">value1</span><span class="sxs-lookup"><span data-stu-id="a151d-116">value1</span></span>||  
|<span data-ttu-id="a151d-117">value2</span><span class="sxs-lookup"><span data-stu-id="a151d-117">value2</span></span>|<span data-ttu-id="a151d-118">Text1</span><span class="sxs-lookup"><span data-stu-id="a151d-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="a151d-119">Elementos con elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a151d-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="a151d-120">Los elementos que tienen elementos secundarios se deducen como tablas.</span><span class="sxs-lookup"><span data-stu-id="a151d-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="a151d-121">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="a151d-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a151d-122">El proceso de inferencia produce una tabla denominada "Element1".</span><span class="sxs-lookup"><span data-stu-id="a151d-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="a151d-123">**Authors1** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a151d-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a151d-124">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="a151d-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a151d-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="a151d-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="a151d-126">Text1</span><span class="sxs-lookup"><span data-stu-id="a151d-126">Text1</span></span>|  
  
 <span data-ttu-id="a151d-127">El elemento de documento, o raíz, se deduce como una tabla si tiene atributos o elementos secundarios que se deducen como columnas.</span><span class="sxs-lookup"><span data-stu-id="a151d-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="a151d-128">Si el elemento de documento no tiene ningún atributo y ningún elemento secundario que se deduzca como columnas, el elemento se deduce como un **conjunto**de elementos.</span><span class="sxs-lookup"><span data-stu-id="a151d-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="a151d-129">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="a151d-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a151d-130">El proceso de inferencia produce una tabla denominada "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="a151d-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="a151d-131">**Authors1** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="a151d-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="a151d-132">**Tabla:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a151d-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="a151d-133">Element1</span><span class="sxs-lookup"><span data-stu-id="a151d-133">Element1</span></span>|<span data-ttu-id="a151d-134">Element2</span><span class="sxs-lookup"><span data-stu-id="a151d-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="a151d-135">Text1</span><span class="sxs-lookup"><span data-stu-id="a151d-135">Text1</span></span>|<span data-ttu-id="a151d-136">Text2</span><span class="sxs-lookup"><span data-stu-id="a151d-136">Text2</span></span>|  
  
 <span data-ttu-id="a151d-137">Por otra parte, considere el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="a151d-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a151d-138">El proceso de inferencia produce un **DataSet** denominado "DocumentElement" que contiene una tabla denominada "Element1".</span><span class="sxs-lookup"><span data-stu-id="a151d-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="a151d-139">**Authors1** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a151d-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a151d-140">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="a151d-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a151d-141">attr1</span><span class="sxs-lookup"><span data-stu-id="a151d-141">attr1</span></span>|<span data-ttu-id="a151d-142">attr2</span><span class="sxs-lookup"><span data-stu-id="a151d-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="a151d-143">value1</span><span class="sxs-lookup"><span data-stu-id="a151d-143">value1</span></span>|<span data-ttu-id="a151d-144">value2</span><span class="sxs-lookup"><span data-stu-id="a151d-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="a151d-145">Elementos que se repiten</span><span class="sxs-lookup"><span data-stu-id="a151d-145">Repeating Elements</span></span>  
 <span data-ttu-id="a151d-146">Los elementos que se repiten se deducen como una única tabla.</span><span class="sxs-lookup"><span data-stu-id="a151d-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="a151d-147">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="a151d-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a151d-148">El proceso de inferencia produce una tabla denominada "Element1".</span><span class="sxs-lookup"><span data-stu-id="a151d-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="a151d-149">**Authors1** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a151d-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a151d-150">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="a151d-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a151d-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="a151d-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="a151d-152">Text1</span><span class="sxs-lookup"><span data-stu-id="a151d-152">Text1</span></span>|  
|<span data-ttu-id="a151d-153">Text2</span><span class="sxs-lookup"><span data-stu-id="a151d-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a151d-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="a151d-154">See also</span></span>

- [<span data-ttu-id="a151d-155">Inferencia de una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="a151d-155">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="a151d-156">Carga de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="a151d-156">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="a151d-157">Carga de información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="a151d-157">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="a151d-158">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="a151d-158">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="a151d-159">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="a151d-159">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="a151d-160">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a151d-160">ADO.NET Overview</span></span>](../ado-net-overview.md)

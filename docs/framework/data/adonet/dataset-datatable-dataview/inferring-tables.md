---
description: Más información acerca de cómo deducir tablas
title: Inferir tablas
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 00a24cbfc44aea4279b0a115214ec26d3eac59ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652164"
---
# <a name="inferring-tables"></a><span data-ttu-id="b1a40-103">Inferir tablas</span><span class="sxs-lookup"><span data-stu-id="b1a40-103">Inferring Tables</span></span>

<span data-ttu-id="b1a40-104">Al deducir un esquema para un <xref:System.Data.DataSet> desde un documento XML, ADO.NET determina en primer lugar qué elementos XML representan tablas.</span><span class="sxs-lookup"><span data-stu-id="b1a40-104">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="b1a40-105">Las siguientes estructuras XML dan como resultado una tabla para el esquema del **conjunto** de elementos:</span><span class="sxs-lookup"><span data-stu-id="b1a40-105">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="b1a40-106">Elementos con atributos</span><span class="sxs-lookup"><span data-stu-id="b1a40-106">Elements with attributes</span></span>  
  
- <span data-ttu-id="b1a40-107">Elementos con elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b1a40-107">Elements with child elements</span></span>  
  
- <span data-ttu-id="b1a40-108">Elementos que se repiten</span><span class="sxs-lookup"><span data-stu-id="b1a40-108">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="b1a40-109">Elementos con atributos</span><span class="sxs-lookup"><span data-stu-id="b1a40-109">Elements with Attributes</span></span>  

 <span data-ttu-id="b1a40-110">Los elementos para los que se han especificado atributos se deducen como tablas.</span><span class="sxs-lookup"><span data-stu-id="b1a40-110">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="b1a40-111">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="b1a40-111">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="b1a40-112">El proceso de inferencia produce una tabla denominada "Element1".</span><span class="sxs-lookup"><span data-stu-id="b1a40-112">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="b1a40-113">**Conjunto** de los: DocumentElement</span><span class="sxs-lookup"><span data-stu-id="b1a40-113">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="b1a40-114">**Tabla:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="b1a40-114">**Table:** Element1</span></span>  
  
|<span data-ttu-id="b1a40-115">attr1</span><span class="sxs-lookup"><span data-stu-id="b1a40-115">attr1</span></span>|<span data-ttu-id="b1a40-116">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="b1a40-116">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="b1a40-117">value1</span><span class="sxs-lookup"><span data-stu-id="b1a40-117">value1</span></span>||  
|<span data-ttu-id="b1a40-118">value2</span><span class="sxs-lookup"><span data-stu-id="b1a40-118">value2</span></span>|<span data-ttu-id="b1a40-119">Text1</span><span class="sxs-lookup"><span data-stu-id="b1a40-119">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="b1a40-120">Elementos con elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b1a40-120">Elements with Child Elements</span></span>  

 <span data-ttu-id="b1a40-121">Los elementos que tienen elementos secundarios se deducen como tablas.</span><span class="sxs-lookup"><span data-stu-id="b1a40-121">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="b1a40-122">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="b1a40-122">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="b1a40-123">El proceso de inferencia produce una tabla denominada "Element1".</span><span class="sxs-lookup"><span data-stu-id="b1a40-123">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="b1a40-124">**Conjunto** de los: DocumentElement</span><span class="sxs-lookup"><span data-stu-id="b1a40-124">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="b1a40-125">**Tabla:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="b1a40-125">**Table:** Element1</span></span>  
  
|<span data-ttu-id="b1a40-126">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="b1a40-126">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="b1a40-127">Text1</span><span class="sxs-lookup"><span data-stu-id="b1a40-127">Text1</span></span>|  
  
 <span data-ttu-id="b1a40-128">El elemento de documento, o raíz, se deduce como una tabla si tiene atributos o elementos secundarios que se deducen como columnas.</span><span class="sxs-lookup"><span data-stu-id="b1a40-128">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="b1a40-129">Si el elemento de documento no tiene ningún atributo y ningún elemento secundario que se deduzca como columnas, el elemento se deduce como un **conjunto** de elementos.</span><span class="sxs-lookup"><span data-stu-id="b1a40-129">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="b1a40-130">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="b1a40-130">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="b1a40-131">El proceso de inferencia produce una tabla denominada "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="b1a40-131">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="b1a40-132">**Conjunto** de los: NewDataSet</span><span class="sxs-lookup"><span data-stu-id="b1a40-132">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="b1a40-133">**Tabla:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="b1a40-133">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="b1a40-134">Element1</span><span class="sxs-lookup"><span data-stu-id="b1a40-134">Element1</span></span>|<span data-ttu-id="b1a40-135">Element2</span><span class="sxs-lookup"><span data-stu-id="b1a40-135">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="b1a40-136">Text1</span><span class="sxs-lookup"><span data-stu-id="b1a40-136">Text1</span></span>|<span data-ttu-id="b1a40-137">Text2</span><span class="sxs-lookup"><span data-stu-id="b1a40-137">Text2</span></span>|  
  
 <span data-ttu-id="b1a40-138">Por otra parte, considere el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="b1a40-138">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="b1a40-139">El proceso de inferencia produce un **DataSet** denominado "DocumentElement" que contiene una tabla denominada "Element1".</span><span class="sxs-lookup"><span data-stu-id="b1a40-139">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="b1a40-140">**Conjunto** de los: DocumentElement</span><span class="sxs-lookup"><span data-stu-id="b1a40-140">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="b1a40-141">**Tabla:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="b1a40-141">**Table:** Element1</span></span>  
  
|<span data-ttu-id="b1a40-142">attr1</span><span class="sxs-lookup"><span data-stu-id="b1a40-142">attr1</span></span>|<span data-ttu-id="b1a40-143">attr2</span><span class="sxs-lookup"><span data-stu-id="b1a40-143">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="b1a40-144">value1</span><span class="sxs-lookup"><span data-stu-id="b1a40-144">value1</span></span>|<span data-ttu-id="b1a40-145">value2</span><span class="sxs-lookup"><span data-stu-id="b1a40-145">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="b1a40-146">Elementos que se repiten</span><span class="sxs-lookup"><span data-stu-id="b1a40-146">Repeating Elements</span></span>  

 <span data-ttu-id="b1a40-147">Los elementos que se repiten se deducen como una única tabla.</span><span class="sxs-lookup"><span data-stu-id="b1a40-147">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="b1a40-148">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="b1a40-148">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="b1a40-149">El proceso de inferencia produce una tabla denominada "Element1".</span><span class="sxs-lookup"><span data-stu-id="b1a40-149">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="b1a40-150">**Conjunto** de los: DocumentElement</span><span class="sxs-lookup"><span data-stu-id="b1a40-150">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="b1a40-151">**Tabla:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="b1a40-151">**Table:** Element1</span></span>  
  
|<span data-ttu-id="b1a40-152">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="b1a40-152">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="b1a40-153">Text1</span><span class="sxs-lookup"><span data-stu-id="b1a40-153">Text1</span></span>|  
|<span data-ttu-id="b1a40-154">Text2</span><span class="sxs-lookup"><span data-stu-id="b1a40-154">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1a40-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1a40-155">See also</span></span>

- [<span data-ttu-id="b1a40-156">Inferir una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="b1a40-156">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="b1a40-157">Cargar un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="b1a40-157">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="b1a40-158">Cargar información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="b1a40-158">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="b1a40-159">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="b1a40-159">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="b1a40-160">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="b1a40-160">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="b1a40-161">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b1a40-161">ADO.NET Overview</span></span>](../ado-net-overview.md)

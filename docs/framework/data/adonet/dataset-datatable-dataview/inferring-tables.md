---
title: Inferir tablas
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 2c2a93d413f301dc3006b701e4bc7979a3fa7a1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034260"
---
# <a name="inferring-tables"></a><span data-ttu-id="95a21-102">Inferir tablas</span><span class="sxs-lookup"><span data-stu-id="95a21-102">Inferring Tables</span></span>
<span data-ttu-id="95a21-103">Al deducir un esquema para un <xref:System.Data.DataSet> desde un documento XML, ADO.NET determina en primer lugar qué elementos XML representan tablas.</span><span class="sxs-lookup"><span data-stu-id="95a21-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="95a21-104">Las siguientes estructuras XML como resultado una tabla para la **DataSet** esquema:</span><span class="sxs-lookup"><span data-stu-id="95a21-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="95a21-105">Elementos con atributos</span><span class="sxs-lookup"><span data-stu-id="95a21-105">Elements with attributes</span></span>  
  
- <span data-ttu-id="95a21-106">Elementos con elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="95a21-106">Elements with child elements</span></span>  
  
- <span data-ttu-id="95a21-107">Elementos que se repiten</span><span class="sxs-lookup"><span data-stu-id="95a21-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="95a21-108">Elementos con atributos</span><span class="sxs-lookup"><span data-stu-id="95a21-108">Elements with Attributes</span></span>  
 <span data-ttu-id="95a21-109">Los elementos para los que se han especificado atributos se deducen como tablas.</span><span class="sxs-lookup"><span data-stu-id="95a21-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="95a21-110">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="95a21-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="95a21-111">El proceso de inferencia produce una tabla denominada "Element1".</span><span class="sxs-lookup"><span data-stu-id="95a21-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="95a21-112">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="95a21-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="95a21-113">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="95a21-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="95a21-114">attr1</span><span class="sxs-lookup"><span data-stu-id="95a21-114">attr1</span></span>|<span data-ttu-id="95a21-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="95a21-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="95a21-116">value1</span><span class="sxs-lookup"><span data-stu-id="95a21-116">value1</span></span>||  
|<span data-ttu-id="95a21-117">value2</span><span class="sxs-lookup"><span data-stu-id="95a21-117">value2</span></span>|<span data-ttu-id="95a21-118">Text1</span><span class="sxs-lookup"><span data-stu-id="95a21-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="95a21-119">Elementos con elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="95a21-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="95a21-120">Los elementos que tienen elementos secundarios se deducen como tablas.</span><span class="sxs-lookup"><span data-stu-id="95a21-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="95a21-121">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="95a21-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="95a21-122">El proceso de inferencia produce una tabla denominada "Element1".</span><span class="sxs-lookup"><span data-stu-id="95a21-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="95a21-123">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="95a21-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="95a21-124">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="95a21-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="95a21-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="95a21-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="95a21-126">Text1</span><span class="sxs-lookup"><span data-stu-id="95a21-126">Text1</span></span>|  
  
 <span data-ttu-id="95a21-127">El elemento de documento, o raíz, se deduce como una tabla si tiene atributos o elementos secundarios que se deducen como columnas.</span><span class="sxs-lookup"><span data-stu-id="95a21-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="95a21-128">Si el elemento de documento no tiene atributos y ningún elemento secundario que se deduzca como columnas, el elemento se deduce como una **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="95a21-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="95a21-129">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="95a21-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="95a21-130">El proceso de inferencia produce una tabla denominada "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="95a21-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="95a21-131">**DataSet:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="95a21-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="95a21-132">**Tabla:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="95a21-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="95a21-133">Element1</span><span class="sxs-lookup"><span data-stu-id="95a21-133">Element1</span></span>|<span data-ttu-id="95a21-134">Element2</span><span class="sxs-lookup"><span data-stu-id="95a21-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="95a21-135">Text1</span><span class="sxs-lookup"><span data-stu-id="95a21-135">Text1</span></span>|<span data-ttu-id="95a21-136">Text2</span><span class="sxs-lookup"><span data-stu-id="95a21-136">Text2</span></span>|  
  
 <span data-ttu-id="95a21-137">Por otra parte, considere el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="95a21-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="95a21-138">El proceso de inferencia produce un **DataSet** denominada "DocumentElement" que contiene una tabla denominada "Element1".</span><span class="sxs-lookup"><span data-stu-id="95a21-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="95a21-139">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="95a21-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="95a21-140">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="95a21-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="95a21-141">attr1</span><span class="sxs-lookup"><span data-stu-id="95a21-141">attr1</span></span>|<span data-ttu-id="95a21-142">attr2</span><span class="sxs-lookup"><span data-stu-id="95a21-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="95a21-143">value1</span><span class="sxs-lookup"><span data-stu-id="95a21-143">value1</span></span>|<span data-ttu-id="95a21-144">value2</span><span class="sxs-lookup"><span data-stu-id="95a21-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="95a21-145">Elementos que se repiten</span><span class="sxs-lookup"><span data-stu-id="95a21-145">Repeating Elements</span></span>  
 <span data-ttu-id="95a21-146">Los elementos que se repiten se deducen como una única tabla.</span><span class="sxs-lookup"><span data-stu-id="95a21-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="95a21-147">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="95a21-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="95a21-148">El proceso de inferencia produce una tabla denominada "Element1".</span><span class="sxs-lookup"><span data-stu-id="95a21-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="95a21-149">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="95a21-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="95a21-150">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="95a21-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="95a21-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="95a21-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="95a21-152">Text1</span><span class="sxs-lookup"><span data-stu-id="95a21-152">Text1</span></span>|  
|<span data-ttu-id="95a21-153">Text2</span><span class="sxs-lookup"><span data-stu-id="95a21-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95a21-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="95a21-154">See also</span></span>

- [<span data-ttu-id="95a21-155">Inferencia de una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="95a21-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="95a21-156">Carga de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="95a21-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="95a21-157">Carga de información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="95a21-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="95a21-158">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="95a21-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="95a21-159">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="95a21-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="95a21-160">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="95a21-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

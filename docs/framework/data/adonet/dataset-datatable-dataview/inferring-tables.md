---
title: Inferir tablas
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 4a3d7b239dbc405cf2acae967b5be401dc772e38
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177558"
---
# <a name="inferring-tables"></a><span data-ttu-id="337bf-102">Inferir tablas</span><span class="sxs-lookup"><span data-stu-id="337bf-102">Inferring Tables</span></span>

<span data-ttu-id="337bf-103">Al deducir un esquema para un <xref:System.Data.DataSet> desde un documento XML, ADO.NET determina en primer lugar qué elementos XML representan tablas.</span><span class="sxs-lookup"><span data-stu-id="337bf-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="337bf-104">Las siguientes estructuras XML dan como resultado una tabla para el esquema del **conjunto** de elementos:</span><span class="sxs-lookup"><span data-stu-id="337bf-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="337bf-105">Elementos con atributos</span><span class="sxs-lookup"><span data-stu-id="337bf-105">Elements with attributes</span></span>  
  
- <span data-ttu-id="337bf-106">Elementos con elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="337bf-106">Elements with child elements</span></span>  
  
- <span data-ttu-id="337bf-107">Elementos que se repiten</span><span class="sxs-lookup"><span data-stu-id="337bf-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="337bf-108">Elementos con atributos</span><span class="sxs-lookup"><span data-stu-id="337bf-108">Elements with Attributes</span></span>  

 <span data-ttu-id="337bf-109">Los elementos para los que se han especificado atributos se deducen como tablas.</span><span class="sxs-lookup"><span data-stu-id="337bf-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="337bf-110">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="337bf-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="337bf-111">El proceso de inferencia produce una tabla denominada "Element1".</span><span class="sxs-lookup"><span data-stu-id="337bf-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="337bf-112">**Conjunto** de los: DocumentElement</span><span class="sxs-lookup"><span data-stu-id="337bf-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="337bf-113">**Tabla:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="337bf-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="337bf-114">attr1</span><span class="sxs-lookup"><span data-stu-id="337bf-114">attr1</span></span>|<span data-ttu-id="337bf-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="337bf-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="337bf-116">value1</span><span class="sxs-lookup"><span data-stu-id="337bf-116">value1</span></span>||  
|<span data-ttu-id="337bf-117">value2</span><span class="sxs-lookup"><span data-stu-id="337bf-117">value2</span></span>|<span data-ttu-id="337bf-118">Text1</span><span class="sxs-lookup"><span data-stu-id="337bf-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="337bf-119">Elementos con elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="337bf-119">Elements with Child Elements</span></span>  

 <span data-ttu-id="337bf-120">Los elementos que tienen elementos secundarios se deducen como tablas.</span><span class="sxs-lookup"><span data-stu-id="337bf-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="337bf-121">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="337bf-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="337bf-122">El proceso de inferencia produce una tabla denominada "Element1".</span><span class="sxs-lookup"><span data-stu-id="337bf-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="337bf-123">**Conjunto** de los: DocumentElement</span><span class="sxs-lookup"><span data-stu-id="337bf-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="337bf-124">**Tabla:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="337bf-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="337bf-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="337bf-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="337bf-126">Text1</span><span class="sxs-lookup"><span data-stu-id="337bf-126">Text1</span></span>|  
  
 <span data-ttu-id="337bf-127">El elemento de documento, o raíz, se deduce como una tabla si tiene atributos o elementos secundarios que se deducen como columnas.</span><span class="sxs-lookup"><span data-stu-id="337bf-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="337bf-128">Si el elemento de documento no tiene ningún atributo y ningún elemento secundario que se deduzca como columnas, el elemento se deduce como un **conjunto**de elementos.</span><span class="sxs-lookup"><span data-stu-id="337bf-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="337bf-129">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="337bf-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="337bf-130">El proceso de inferencia produce una tabla denominada "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="337bf-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="337bf-131">**Conjunto** de los: NewDataSet</span><span class="sxs-lookup"><span data-stu-id="337bf-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="337bf-132">**Tabla:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="337bf-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="337bf-133">Element1</span><span class="sxs-lookup"><span data-stu-id="337bf-133">Element1</span></span>|<span data-ttu-id="337bf-134">Element2</span><span class="sxs-lookup"><span data-stu-id="337bf-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="337bf-135">Text1</span><span class="sxs-lookup"><span data-stu-id="337bf-135">Text1</span></span>|<span data-ttu-id="337bf-136">Text2</span><span class="sxs-lookup"><span data-stu-id="337bf-136">Text2</span></span>|  
  
 <span data-ttu-id="337bf-137">Por otra parte, considere el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="337bf-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="337bf-138">El proceso de inferencia produce un **DataSet** denominado "DocumentElement" que contiene una tabla denominada "Element1".</span><span class="sxs-lookup"><span data-stu-id="337bf-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="337bf-139">**Conjunto** de los: DocumentElement</span><span class="sxs-lookup"><span data-stu-id="337bf-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="337bf-140">**Tabla:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="337bf-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="337bf-141">attr1</span><span class="sxs-lookup"><span data-stu-id="337bf-141">attr1</span></span>|<span data-ttu-id="337bf-142">attr2</span><span class="sxs-lookup"><span data-stu-id="337bf-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="337bf-143">value1</span><span class="sxs-lookup"><span data-stu-id="337bf-143">value1</span></span>|<span data-ttu-id="337bf-144">value2</span><span class="sxs-lookup"><span data-stu-id="337bf-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="337bf-145">Elementos que se repiten</span><span class="sxs-lookup"><span data-stu-id="337bf-145">Repeating Elements</span></span>  

 <span data-ttu-id="337bf-146">Los elementos que se repiten se deducen como una única tabla.</span><span class="sxs-lookup"><span data-stu-id="337bf-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="337bf-147">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="337bf-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="337bf-148">El proceso de inferencia produce una tabla denominada "Element1".</span><span class="sxs-lookup"><span data-stu-id="337bf-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="337bf-149">**Conjunto** de los: DocumentElement</span><span class="sxs-lookup"><span data-stu-id="337bf-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="337bf-150">**Tabla:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="337bf-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="337bf-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="337bf-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="337bf-152">Text1</span><span class="sxs-lookup"><span data-stu-id="337bf-152">Text1</span></span>|  
|<span data-ttu-id="337bf-153">Text2</span><span class="sxs-lookup"><span data-stu-id="337bf-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="337bf-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="337bf-154">See also</span></span>

- [<span data-ttu-id="337bf-155">Inferir una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="337bf-155">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="337bf-156">Cargar un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="337bf-156">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="337bf-157">Cargar información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="337bf-157">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="337bf-158">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="337bf-158">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="337bf-159">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="337bf-159">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="337bf-160">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="337bf-160">ADO.NET Overview</span></span>](../ado-net-overview.md)

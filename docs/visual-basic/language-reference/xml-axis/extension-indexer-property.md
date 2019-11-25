---
title: Propiedad de indizador de extensión
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: 5f91dc8a6b1a0d82daa4891cf826c16e2716839f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352693"
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="dafa0-102">Propiedad de indizador de extensión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dafa0-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="dafa0-103">Proporciona acceso a los elementos individuales de una recopilación.</span><span class="sxs-lookup"><span data-stu-id="dafa0-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dafa0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dafa0-104">Syntax</span></span>  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="dafa0-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="dafa0-105">Parts</span></span>  
  
|<span data-ttu-id="dafa0-106">Término</span><span class="sxs-lookup"><span data-stu-id="dafa0-106">Term</span></span>|<span data-ttu-id="dafa0-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="dafa0-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="dafa0-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="dafa0-108">Required.</span></span> <span data-ttu-id="dafa0-109">A queryable collection.</span><span class="sxs-lookup"><span data-stu-id="dafa0-109">A queryable collection.</span></span> <span data-ttu-id="dafa0-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="dafa0-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="dafa0-111">(</span><span class="sxs-lookup"><span data-stu-id="dafa0-111">(</span></span>|<span data-ttu-id="dafa0-112">Requerido.</span><span class="sxs-lookup"><span data-stu-id="dafa0-112">Required.</span></span> <span data-ttu-id="dafa0-113">Denotes the start of the indexer property.</span><span class="sxs-lookup"><span data-stu-id="dafa0-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="dafa0-114">Requerido.</span><span class="sxs-lookup"><span data-stu-id="dafa0-114">Required.</span></span> <span data-ttu-id="dafa0-115">An integer expression that specifies the zero-based position of an element of the collection.</span><span class="sxs-lookup"><span data-stu-id="dafa0-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="dafa0-116">)</span><span class="sxs-lookup"><span data-stu-id="dafa0-116">)</span></span>|<span data-ttu-id="dafa0-117">Requerido.</span><span class="sxs-lookup"><span data-stu-id="dafa0-117">Required.</span></span> <span data-ttu-id="dafa0-118">Denotes the end of the indexer property.</span><span class="sxs-lookup"><span data-stu-id="dafa0-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="dafa0-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dafa0-119">Return Value</span></span>  
 <span data-ttu-id="dafa0-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span><span class="sxs-lookup"><span data-stu-id="dafa0-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dafa0-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dafa0-121">Remarks</span></span>  
 <span data-ttu-id="dafa0-122">You can use the extension indexer property to access individual elements in a collection.</span><span class="sxs-lookup"><span data-stu-id="dafa0-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="dafa0-123">This indexer property is typically used on the output of XML axis properties.</span><span class="sxs-lookup"><span data-stu-id="dafa0-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="dafa0-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span><span class="sxs-lookup"><span data-stu-id="dafa0-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="dafa0-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span><span class="sxs-lookup"><span data-stu-id="dafa0-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="dafa0-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span><span class="sxs-lookup"><span data-stu-id="dafa0-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="dafa0-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span><span class="sxs-lookup"><span data-stu-id="dafa0-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="dafa0-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span><span class="sxs-lookup"><span data-stu-id="dafa0-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="dafa0-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span><span class="sxs-lookup"><span data-stu-id="dafa0-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="dafa0-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="dafa0-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dafa0-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dafa0-131">Example</span></span>  
 <span data-ttu-id="dafa0-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span><span class="sxs-lookup"><span data-stu-id="dafa0-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="dafa0-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span><span class="sxs-lookup"><span data-stu-id="dafa0-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 <span data-ttu-id="dafa0-134">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="dafa0-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="dafa0-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="dafa0-135">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="dafa0-136">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="dafa0-136">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="dafa0-137">Literales XML</span><span class="sxs-lookup"><span data-stu-id="dafa0-137">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="dafa0-138">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dafa0-138">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="dafa0-139">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="dafa0-139">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)

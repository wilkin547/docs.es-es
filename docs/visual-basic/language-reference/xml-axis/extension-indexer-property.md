---
title: "Propiedad de indizador de extensión (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 99d14b6e54a59ffc904a9e786c22498d23ee8ab6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="2597c-102">Propiedad de indizador de extensión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2597c-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="2597c-103">Proporciona acceso a los elementos individuales de una recopilación.</span><span class="sxs-lookup"><span data-stu-id="2597c-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2597c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2597c-104">Syntax</span></span>  
  
```  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="2597c-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="2597c-105">Parts</span></span>  
  
|<span data-ttu-id="2597c-106">Término</span><span class="sxs-lookup"><span data-stu-id="2597c-106">Term</span></span>|<span data-ttu-id="2597c-107">Definición</span><span class="sxs-lookup"><span data-stu-id="2597c-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="2597c-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2597c-108">Required.</span></span> <span data-ttu-id="2597c-109">Una colección consultable.</span><span class="sxs-lookup"><span data-stu-id="2597c-109">A queryable collection.</span></span> <span data-ttu-id="2597c-110">Es decir, una colección que implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="2597c-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="2597c-111">(</span><span class="sxs-lookup"><span data-stu-id="2597c-111">(</span></span>|<span data-ttu-id="2597c-112">Requerido.</span><span class="sxs-lookup"><span data-stu-id="2597c-112">Required.</span></span> <span data-ttu-id="2597c-113">Denota el inicio de la propiedad de indizador.</span><span class="sxs-lookup"><span data-stu-id="2597c-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="2597c-114">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2597c-114">Required.</span></span> <span data-ttu-id="2597c-115">Expresión entera que especifica la posición de base cero de un elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="2597c-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="2597c-116">)</span><span class="sxs-lookup"><span data-stu-id="2597c-116">)</span></span>|<span data-ttu-id="2597c-117">Requerido.</span><span class="sxs-lookup"><span data-stu-id="2597c-117">Required.</span></span> <span data-ttu-id="2597c-118">Denota el final de la propiedad de indizador.</span><span class="sxs-lookup"><span data-stu-id="2597c-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="2597c-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2597c-119">Return Value</span></span>  
 <span data-ttu-id="2597c-120">El objeto desde la ubicación especificada en la colección, o `Nothing` si el índice está fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="2597c-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2597c-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2597c-121">Remarks</span></span>  
 <span data-ttu-id="2597c-122">Puede utilizar la propiedad de indizador de extensión para obtener acceso a los elementos individuales de una colección.</span><span class="sxs-lookup"><span data-stu-id="2597c-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="2597c-123">Esta propiedad de indizador se suele usar en la salida de las propiedades de eje XML.</span><span class="sxs-lookup"><span data-stu-id="2597c-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="2597c-124">El elemento secundario XML y propiedades de eje descendiente XML devuelven colecciones de <xref:System.Xml.Linq.XElement> objetos o un valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="2597c-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="2597c-125">El [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador convierte las propiedades de indizador de extensión en llamadas a la `ElementAtOrDefault` método.</span><span class="sxs-lookup"><span data-stu-id="2597c-125">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="2597c-126">A diferencia de un indizador de matriz, el `ElementAtOrDefault` método `Nothing` si el índice está fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="2597c-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="2597c-127">Este comportamiento es útil cuando no se puede determinar fácilmente el número de elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="2597c-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="2597c-128">Esta propiedad de indizador es similar a una propiedad de extensión para las colecciones que implementan <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>: se utiliza sólo si la colección no tiene un indizador o una propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2597c-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="2597c-129">Para obtener acceso al valor del primer elemento de una colección de <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute> objetos, puede utilizar el código XML `Value` propiedad.</span><span class="sxs-lookup"><span data-stu-id="2597c-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="2597c-130">Para obtener más información, consulte [propiedad Value de XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="2597c-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2597c-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2597c-131">Example</span></span>  
 <span data-ttu-id="2597c-132">En el ejemplo siguiente se muestra cómo utilizar el indizador de extensión para tener acceso al segundo nodo secundario en una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="2597c-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="2597c-133">Se tiene acceso a la colección utilizando la propiedad de eje secundario, que obtiene todos los elementos secundarios llamados `phone` en la `contact` objeto.</span><span class="sxs-lookup"><span data-stu-id="2597c-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 <span data-ttu-id="2597c-134">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="2597c-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="2597c-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="2597c-135">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="2597c-136">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="2597c-136">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="2597c-137">Literales XML</span><span class="sxs-lookup"><span data-stu-id="2597c-137">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="2597c-138">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2597c-138">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="2597c-139">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="2597c-139">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)

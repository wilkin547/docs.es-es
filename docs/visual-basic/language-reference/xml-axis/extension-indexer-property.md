---
title: Propiedad de indizador de extensión (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: ab9eacc3fb3796139d8ed8382146a4a6c2b28a97
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483715"
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="2d6d0-102">Propiedad de indizador de extensión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d6d0-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="2d6d0-103">Proporciona acceso a los elementos individuales de una recopilación.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d6d0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d6d0-104">Syntax</span></span>  
  
```  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="2d6d0-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="2d6d0-105">Parts</span></span>  
  
|<span data-ttu-id="2d6d0-106">Término</span><span class="sxs-lookup"><span data-stu-id="2d6d0-106">Term</span></span>|<span data-ttu-id="2d6d0-107">Definición</span><span class="sxs-lookup"><span data-stu-id="2d6d0-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="2d6d0-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-108">Required.</span></span> <span data-ttu-id="2d6d0-109">Una colección consultable.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-109">A queryable collection.</span></span> <span data-ttu-id="2d6d0-110">Es decir, una colección que implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="2d6d0-111">(</span><span class="sxs-lookup"><span data-stu-id="2d6d0-111">(</span></span>|<span data-ttu-id="2d6d0-112">Requerido.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-112">Required.</span></span> <span data-ttu-id="2d6d0-113">Denota el inicio de la propiedad de indizador.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="2d6d0-114">Requerido.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-114">Required.</span></span> <span data-ttu-id="2d6d0-115">Expresión entera que especifica la posición de base cero de un elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="2d6d0-116">)</span><span class="sxs-lookup"><span data-stu-id="2d6d0-116">)</span></span>|<span data-ttu-id="2d6d0-117">Requerido.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-117">Required.</span></span> <span data-ttu-id="2d6d0-118">Denota el final de la propiedad de indizador.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="2d6d0-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2d6d0-119">Return Value</span></span>  
 <span data-ttu-id="2d6d0-120">El objeto de la ubicación especificada en la colección, o `Nothing` si el índice está fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d6d0-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d6d0-121">Remarks</span></span>  
 <span data-ttu-id="2d6d0-122">Puede usar la propiedad de indizador de extensión para tener acceso a elementos individuales de una colección.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="2d6d0-123">Esta propiedad de indizador se usa normalmente en la salida de las propiedades de eje XML.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="2d6d0-124">El elemento secundario XML y propiedades de eje descendiente XML devuelven colecciones de <xref:System.Xml.Linq.XElement> objetos o un valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="2d6d0-125">El compilador de Visual Basic convierte las propiedades del indizador de extensión para las llamadas a la `ElementAtOrDefault` método.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="2d6d0-126">A diferencia de un indizador de matriz, el `ElementAtOrDefault` devuelve del método `Nothing` si el índice está fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="2d6d0-127">Este comportamiento es útil cuando no se puede determinar fácilmente el número de elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="2d6d0-128">Esta propiedad de indizador es como una propiedad de extensión para las colecciones que implementan <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>: se usa solo si la colección no tiene un indizador o una propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="2d6d0-129">Para obtener acceso al valor del primer elemento en una colección de <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute> objetos, puede utilizar el código XML `Value` propiedad.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="2d6d0-130">Para obtener más información, consulte [propiedad Value de XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="2d6d0-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d6d0-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d6d0-131">Example</span></span>  
 <span data-ttu-id="2d6d0-132">El ejemplo siguiente muestra cómo usar el indizador de extensión para tener acceso el segundo nodo secundario en una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="2d6d0-133">Se tiene acceso a la colección mediante el uso de la propiedad de eje secundario, que obtiene todos los elementos secundarios denominados `phone` en el `contact` objeto.</span><span class="sxs-lookup"><span data-stu-id="2d6d0-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 <span data-ttu-id="2d6d0-134">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="2d6d0-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="2d6d0-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d6d0-135">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="2d6d0-136">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="2d6d0-136">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)  
 [<span data-ttu-id="2d6d0-137">Literales XML</span><span class="sxs-lookup"><span data-stu-id="2d6d0-137">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="2d6d0-138">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2d6d0-138">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="2d6d0-139">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="2d6d0-139">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)

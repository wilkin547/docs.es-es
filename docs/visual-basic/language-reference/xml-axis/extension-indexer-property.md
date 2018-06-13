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
ms.openlocfilehash: a7718a4aa85a000d0c83e8c9556a448ceaf13c82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603475"
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="1ed73-102">Propiedad de indizador de extensión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ed73-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="1ed73-103">Proporciona acceso a los elementos individuales de una recopilación.</span><span class="sxs-lookup"><span data-stu-id="1ed73-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ed73-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ed73-104">Syntax</span></span>  
  
```  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="1ed73-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="1ed73-105">Parts</span></span>  
  
|<span data-ttu-id="1ed73-106">Término</span><span class="sxs-lookup"><span data-stu-id="1ed73-106">Term</span></span>|<span data-ttu-id="1ed73-107">Definición</span><span class="sxs-lookup"><span data-stu-id="1ed73-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="1ed73-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="1ed73-108">Required.</span></span> <span data-ttu-id="1ed73-109">Una colección consultable.</span><span class="sxs-lookup"><span data-stu-id="1ed73-109">A queryable collection.</span></span> <span data-ttu-id="1ed73-110">Es decir, una colección que implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="1ed73-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="1ed73-111">(</span><span class="sxs-lookup"><span data-stu-id="1ed73-111">(</span></span>|<span data-ttu-id="1ed73-112">Requerido.</span><span class="sxs-lookup"><span data-stu-id="1ed73-112">Required.</span></span> <span data-ttu-id="1ed73-113">Denota el inicio de la propiedad de indizador.</span><span class="sxs-lookup"><span data-stu-id="1ed73-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="1ed73-114">Requerido.</span><span class="sxs-lookup"><span data-stu-id="1ed73-114">Required.</span></span> <span data-ttu-id="1ed73-115">Expresión entera que especifica la posición de base cero de un elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="1ed73-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="1ed73-116">)</span><span class="sxs-lookup"><span data-stu-id="1ed73-116">)</span></span>|<span data-ttu-id="1ed73-117">Requerido.</span><span class="sxs-lookup"><span data-stu-id="1ed73-117">Required.</span></span> <span data-ttu-id="1ed73-118">Denota el final de la propiedad de indizador.</span><span class="sxs-lookup"><span data-stu-id="1ed73-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="1ed73-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1ed73-119">Return Value</span></span>  
 <span data-ttu-id="1ed73-120">El objeto desde la ubicación especificada en la colección, o `Nothing` si el índice está fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="1ed73-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ed73-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ed73-121">Remarks</span></span>  
 <span data-ttu-id="1ed73-122">Puede utilizar la propiedad de indizador de extensión para obtener acceso a los elementos individuales de una colección.</span><span class="sxs-lookup"><span data-stu-id="1ed73-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="1ed73-123">Esta propiedad de indizador se suele usar en la salida de las propiedades de eje XML.</span><span class="sxs-lookup"><span data-stu-id="1ed73-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="1ed73-124">El elemento secundario XML y propiedades de eje descendiente XML devuelven colecciones de <xref:System.Xml.Linq.XElement> objetos o un valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="1ed73-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="1ed73-125">El compilador de Visual Basic convierte las propiedades de indizador de extensión para las llamadas a la `ElementAtOrDefault` método.</span><span class="sxs-lookup"><span data-stu-id="1ed73-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="1ed73-126">A diferencia de un indizador de matriz, el `ElementAtOrDefault` método `Nothing` si el índice está fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="1ed73-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="1ed73-127">Este comportamiento es útil cuando no se puede determinar fácilmente el número de elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="1ed73-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="1ed73-128">Esta propiedad de indizador es similar a una propiedad de extensión para las colecciones que implementan <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>: se utiliza sólo si la colección no tiene un indizador o una propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1ed73-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="1ed73-129">Para obtener acceso al valor del primer elemento de una colección de <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute> objetos, puede utilizar el código XML `Value` propiedad.</span><span class="sxs-lookup"><span data-stu-id="1ed73-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="1ed73-130">Para obtener más información, consulte [propiedad Value de XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="1ed73-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ed73-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ed73-131">Example</span></span>  
 <span data-ttu-id="1ed73-132">En el ejemplo siguiente se muestra cómo utilizar el indizador de extensión para tener acceso al segundo nodo secundario en una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="1ed73-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="1ed73-133">Se tiene acceso a la colección utilizando la propiedad de eje secundario, que obtiene todos los elementos secundarios llamados `phone` en la `contact` objeto.</span><span class="sxs-lookup"><span data-stu-id="1ed73-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 <span data-ttu-id="1ed73-134">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="1ed73-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="1ed73-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ed73-135">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="1ed73-136">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="1ed73-136">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="1ed73-137">Literales XML</span><span class="sxs-lookup"><span data-stu-id="1ed73-137">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="1ed73-138">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1ed73-138">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="1ed73-139">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="1ed73-139">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)

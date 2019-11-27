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
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="4aef2-102">Propiedad de indizador de extensión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4aef2-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="4aef2-103">Proporciona acceso a los elementos individuales de una recopilación.</span><span class="sxs-lookup"><span data-stu-id="4aef2-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aef2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4aef2-104">Syntax</span></span>  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="4aef2-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="4aef2-105">Parts</span></span>  
  
|<span data-ttu-id="4aef2-106">Término</span><span class="sxs-lookup"><span data-stu-id="4aef2-106">Term</span></span>|<span data-ttu-id="4aef2-107">Definición</span><span class="sxs-lookup"><span data-stu-id="4aef2-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="4aef2-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="4aef2-108">Required.</span></span> <span data-ttu-id="4aef2-109">Colección consultable.</span><span class="sxs-lookup"><span data-stu-id="4aef2-109">A queryable collection.</span></span> <span data-ttu-id="4aef2-110">Es decir, una colección que implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="4aef2-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="4aef2-111">(</span><span class="sxs-lookup"><span data-stu-id="4aef2-111">(</span></span>|<span data-ttu-id="4aef2-112">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="4aef2-112">Required.</span></span> <span data-ttu-id="4aef2-113">Denota el inicio de la propiedad de indizador.</span><span class="sxs-lookup"><span data-stu-id="4aef2-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="4aef2-114">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="4aef2-114">Required.</span></span> <span data-ttu-id="4aef2-115">Expresión de tipo entero que especifica la posición de base cero de un elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="4aef2-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="4aef2-116">)</span><span class="sxs-lookup"><span data-stu-id="4aef2-116">)</span></span>|<span data-ttu-id="4aef2-117">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="4aef2-117">Required.</span></span> <span data-ttu-id="4aef2-118">Denota el final de la propiedad de indizador.</span><span class="sxs-lookup"><span data-stu-id="4aef2-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="4aef2-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4aef2-119">Return Value</span></span>  
 <span data-ttu-id="4aef2-120">Objeto de la ubicación especificada en la colección, o `Nothing` si el índice está fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="4aef2-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4aef2-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4aef2-121">Remarks</span></span>  
 <span data-ttu-id="4aef2-122">Puede usar la propiedad de indizador de extensión para tener acceso a los elementos individuales de una colección.</span><span class="sxs-lookup"><span data-stu-id="4aef2-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="4aef2-123">Esta propiedad de indizador se utiliza normalmente en la salida de las propiedades del eje XML.</span><span class="sxs-lookup"><span data-stu-id="4aef2-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="4aef2-124">Las propiedades XML secundario y del eje descendiente XML devuelven colecciones de objetos <xref:System.Xml.Linq.XElement> o un valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="4aef2-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="4aef2-125">El compilador Visual Basic convierte las propiedades de indizador de extensión en llamadas al método `ElementAtOrDefault`.</span><span class="sxs-lookup"><span data-stu-id="4aef2-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="4aef2-126">A diferencia de un indizador de matriz, el método `ElementAtOrDefault` devuelve `Nothing` si el índice está fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="4aef2-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="4aef2-127">Este comportamiento es útil cuando no se puede determinar fácilmente el número de elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="4aef2-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="4aef2-128">Esta propiedad de indizador es como una propiedad de extensión para las colecciones que implementan <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>: solo se usa si la colección no tiene un indizador o una propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4aef2-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="4aef2-129">Para tener acceso al valor del primer elemento de una colección de objetos <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute>, puede usar la propiedad `Value` XML.</span><span class="sxs-lookup"><span data-stu-id="4aef2-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="4aef2-130">Para obtener más información, vea [propiedad valor XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="4aef2-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4aef2-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4aef2-131">Example</span></span>  
 <span data-ttu-id="4aef2-132">En el ejemplo siguiente se muestra cómo usar el indizador de extensión para tener acceso al segundo nodo secundario de una colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="4aef2-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="4aef2-133">Se tiene acceso a la colección mediante la propiedad del eje secundario, que obtiene todos los elementos secundarios denominados `phone` en el objeto `contact`.</span><span class="sxs-lookup"><span data-stu-id="4aef2-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 <span data-ttu-id="4aef2-134">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="4aef2-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="4aef2-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="4aef2-135">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="4aef2-136">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="4aef2-136">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="4aef2-137">Literales XML</span><span class="sxs-lookup"><span data-stu-id="4aef2-137">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="4aef2-138">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4aef2-138">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="4aef2-139">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="4aef2-139">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)

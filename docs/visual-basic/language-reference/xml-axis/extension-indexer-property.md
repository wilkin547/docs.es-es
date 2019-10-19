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
ms.openlocfilehash: 660cebadc78d260350f2849f7f4926f9cef7c8d2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582185"
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="920e0-102">Propiedad de indizador de extensión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="920e0-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="920e0-103">Proporciona acceso a los elementos individuales de una recopilación.</span><span class="sxs-lookup"><span data-stu-id="920e0-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="920e0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="920e0-104">Syntax</span></span>  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="920e0-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="920e0-105">Parts</span></span>  
  
|<span data-ttu-id="920e0-106">Término</span><span class="sxs-lookup"><span data-stu-id="920e0-106">Term</span></span>|<span data-ttu-id="920e0-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="920e0-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="920e0-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="920e0-108">Required.</span></span> <span data-ttu-id="920e0-109">Colección consultable.</span><span class="sxs-lookup"><span data-stu-id="920e0-109">A queryable collection.</span></span> <span data-ttu-id="920e0-110">Es decir, una colección que implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="920e0-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="920e0-111">(</span><span class="sxs-lookup"><span data-stu-id="920e0-111">(</span></span>|<span data-ttu-id="920e0-112">Requerido.</span><span class="sxs-lookup"><span data-stu-id="920e0-112">Required.</span></span> <span data-ttu-id="920e0-113">Denota el inicio de la propiedad de indizador.</span><span class="sxs-lookup"><span data-stu-id="920e0-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="920e0-114">Requerido.</span><span class="sxs-lookup"><span data-stu-id="920e0-114">Required.</span></span> <span data-ttu-id="920e0-115">Expresión de tipo entero que especifica la posición de base cero de un elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="920e0-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="920e0-116">)</span><span class="sxs-lookup"><span data-stu-id="920e0-116">)</span></span>|<span data-ttu-id="920e0-117">Requerido.</span><span class="sxs-lookup"><span data-stu-id="920e0-117">Required.</span></span> <span data-ttu-id="920e0-118">Denota el final de la propiedad de indizador.</span><span class="sxs-lookup"><span data-stu-id="920e0-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="920e0-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="920e0-119">Return Value</span></span>  
 <span data-ttu-id="920e0-120">Objeto de la ubicación especificada en la colección, o `Nothing` si el índice está fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="920e0-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="920e0-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="920e0-121">Remarks</span></span>  
 <span data-ttu-id="920e0-122">Puede usar la propiedad de indizador de extensión para tener acceso a los elementos individuales de una colección.</span><span class="sxs-lookup"><span data-stu-id="920e0-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="920e0-123">Esta propiedad de indizador se utiliza normalmente en la salida de las propiedades del eje XML.</span><span class="sxs-lookup"><span data-stu-id="920e0-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="920e0-124">Las propiedades XML secundario y del eje descendiente XML devuelven colecciones de objetos <xref:System.Xml.Linq.XElement> o un valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="920e0-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="920e0-125">El compilador Visual Basic convierte las propiedades de indizador de extensión en llamadas al método `ElementAtOrDefault`.</span><span class="sxs-lookup"><span data-stu-id="920e0-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="920e0-126">A diferencia de un indizador de matriz, el método `ElementAtOrDefault` devuelve `Nothing` si el índice está fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="920e0-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="920e0-127">Este comportamiento es útil cuando no se puede determinar fácilmente el número de elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="920e0-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="920e0-128">Esta propiedad de indizador es como una propiedad de extensión para las colecciones que implementan <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>: solo se usa si la colección no tiene un indizador o una propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="920e0-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="920e0-129">Para tener acceso al valor del primer elemento de una colección de objetos <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute>, puede usar la propiedad `Value` XML.</span><span class="sxs-lookup"><span data-stu-id="920e0-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="920e0-130">Para obtener más información, vea [propiedad valor XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="920e0-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="920e0-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="920e0-131">Example</span></span>  
 <span data-ttu-id="920e0-132">En el ejemplo siguiente se muestra cómo usar el indizador de extensión para tener acceso al segundo nodo secundario de una colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="920e0-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="920e0-133">Se tiene acceso a la colección mediante la propiedad del eje secundario, que obtiene todos los elementos secundarios denominados `phone` en el objeto `contact`.</span><span class="sxs-lookup"><span data-stu-id="920e0-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 <span data-ttu-id="920e0-134">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="920e0-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="920e0-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="920e0-135">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="920e0-136">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="920e0-136">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="920e0-137">Literales XML</span><span class="sxs-lookup"><span data-stu-id="920e0-137">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="920e0-138">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="920e0-138">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="920e0-139">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="920e0-139">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)

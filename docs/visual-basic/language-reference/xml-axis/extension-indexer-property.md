---
description: 'Más información sobre: propiedad de indizador de extensión (Visual Basic)'
title: Propiedad de indexador de extensión
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: ec165836f739db9a74ea266ebba32be5bb42cca6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700330"
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="1b924-103">Propiedad de indizador de extensión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b924-103">Extension Indexer Property (Visual Basic)</span></span>

<span data-ttu-id="1b924-104">Proporciona acceso a los elementos individuales de una recopilación.</span><span class="sxs-lookup"><span data-stu-id="1b924-104">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b924-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b924-105">Syntax</span></span>  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="1b924-106">Partes</span><span class="sxs-lookup"><span data-stu-id="1b924-106">Parts</span></span>  
  
|<span data-ttu-id="1b924-107">Término</span><span class="sxs-lookup"><span data-stu-id="1b924-107">Term</span></span>|<span data-ttu-id="1b924-108">Definición</span><span class="sxs-lookup"><span data-stu-id="1b924-108">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="1b924-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1b924-109">Required.</span></span> <span data-ttu-id="1b924-110">Colección consultable.</span><span class="sxs-lookup"><span data-stu-id="1b924-110">A queryable collection.</span></span> <span data-ttu-id="1b924-111">Es decir, una colección que implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601> .</span><span class="sxs-lookup"><span data-stu-id="1b924-111">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="1b924-112">(</span><span class="sxs-lookup"><span data-stu-id="1b924-112">(</span></span>|<span data-ttu-id="1b924-113">Necesario.</span><span class="sxs-lookup"><span data-stu-id="1b924-113">Required.</span></span> <span data-ttu-id="1b924-114">Denota el inicio de la propiedad de indizador.</span><span class="sxs-lookup"><span data-stu-id="1b924-114">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="1b924-115">Necesario.</span><span class="sxs-lookup"><span data-stu-id="1b924-115">Required.</span></span> <span data-ttu-id="1b924-116">Expresión de tipo entero que especifica la posición de base cero de un elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="1b924-116">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="1b924-117">)</span><span class="sxs-lookup"><span data-stu-id="1b924-117">)</span></span>|<span data-ttu-id="1b924-118">Necesario.</span><span class="sxs-lookup"><span data-stu-id="1b924-118">Required.</span></span> <span data-ttu-id="1b924-119">Denota el final de la propiedad de indizador.</span><span class="sxs-lookup"><span data-stu-id="1b924-119">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="1b924-120">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1b924-120">Return Value</span></span>  

 <span data-ttu-id="1b924-121">Objeto de la ubicación especificada en la colección o `Nothing` si el índice está fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="1b924-121">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b924-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1b924-122">Remarks</span></span>  

 <span data-ttu-id="1b924-123">Puede usar la propiedad de indizador de extensión para tener acceso a los elementos individuales de una colección.</span><span class="sxs-lookup"><span data-stu-id="1b924-123">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="1b924-124">Esta propiedad de indizador se utiliza normalmente en la salida de las propiedades del eje XML.</span><span class="sxs-lookup"><span data-stu-id="1b924-124">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="1b924-125">Las propiedades XML secundario y del eje descendiente XML devuelven colecciones de <xref:System.Xml.Linq.XElement> objetos o un valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="1b924-125">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="1b924-126">El compilador Visual Basic convierte las propiedades de indizador de extensión en llamadas al `ElementAtOrDefault` método.</span><span class="sxs-lookup"><span data-stu-id="1b924-126">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="1b924-127">A diferencia de un indizador de matriz, el `ElementAtOrDefault` método devuelve `Nothing` si el índice está fuera del intervalo.</span><span class="sxs-lookup"><span data-stu-id="1b924-127">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="1b924-128">Este comportamiento es útil cuando no se puede determinar fácilmente el número de elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="1b924-128">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="1b924-129">Esta propiedad de indizador es como una propiedad de extensión para las colecciones que implementan <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601> : solo se usa si la colección no tiene un indizador o una propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1b924-129">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="1b924-130">Para tener acceso al valor del primer elemento de una colección de <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XAttribute> objetos o, puede usar la propiedad XML `Value` .</span><span class="sxs-lookup"><span data-stu-id="1b924-130">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="1b924-131">Para obtener más información, vea [propiedad valor XML](xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="1b924-131">For more information, see [XML Value Property](xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b924-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b924-132">Example</span></span>  

 <span data-ttu-id="1b924-133">En el ejemplo siguiente se muestra cómo usar el indizador de extensión para tener acceso al segundo nodo secundario de una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="1b924-133">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="1b924-134">Se tiene acceso a la colección mediante la propiedad del eje secundario, que obtiene todos los elementos secundarios denominados `phone` en el `contact` objeto.</span><span class="sxs-lookup"><span data-stu-id="1b924-134">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 <span data-ttu-id="1b924-135">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="1b924-135">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="1b924-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b924-136">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="1b924-137">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="1b924-137">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="1b924-138">Literales XML</span><span class="sxs-lookup"><span data-stu-id="1b924-138">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="1b924-139">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1b924-139">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="1b924-140">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="1b924-140">XML Value Property</span></span>](xml-value-property.md)

---
title: Value (Propiedad XML) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 9edf95c7cedced55ab2441baf51b7c2052e4654c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942986"
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="e2d8b-102">Value (Propiedad XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2d8b-102">XML Value Property (Visual Basic)</span></span>
<span data-ttu-id="e2d8b-103">Proporciona acceso al valor del primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-103">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2d8b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2d8b-104">Syntax</span></span>  
  
```  
object.Value  
```  
  
## <a name="parts"></a><span data-ttu-id="e2d8b-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="e2d8b-105">Parts</span></span>  
  
|<span data-ttu-id="e2d8b-106">Término</span><span class="sxs-lookup"><span data-stu-id="e2d8b-106">Term</span></span>|<span data-ttu-id="e2d8b-107">Definición</span><span class="sxs-lookup"><span data-stu-id="e2d8b-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="e2d8b-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-108">Required.</span></span> <span data-ttu-id="e2d8b-109">Una colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-109">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="e2d8b-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e2d8b-110">Return Value</span></span>  
 <span data-ttu-id="e2d8b-111">Que contiene el valor del primer elemento de la colección o `Nothing` si la colección está vacía. `String`</span><span class="sxs-lookup"><span data-stu-id="e2d8b-111">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2d8b-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2d8b-112">Remarks</span></span>  
 <span data-ttu-id="e2d8b-113">La <xref:System.Xml.Linq.XElement.Value%2A> propiedad facilita el acceso al valor del primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-113">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="e2d8b-114">Esta propiedad comprueba primero si la colección contiene al menos un objeto.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-114">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="e2d8b-115">Si la colección está vacía, esta propiedad devuelve `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-115">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="e2d8b-116">De lo contrario, esta propiedad devuelve el valor <xref:System.Xml.Linq.XElement.Value%2A> de la propiedad del primer elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-116">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2d8b-117">Cuando se tiene acceso al valor de un atributo XML mediante el\@identificador ' ', el valor del atributo se devuelve `String` como y no es necesario especificar explícitamente la <xref:System.Xml.Linq.XAttribute.Value%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-117">When you access the value of an XML attribute using the '\@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="e2d8b-118">Para tener acceso a otros elementos de una colección, puede usar la propiedad de indizador de extensión XML.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-118">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="e2d8b-119">Para más información, consulte [extensión](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)de la propiedad Indexer.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-119">For more information, see [Extension Indexer Property](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="e2d8b-120">Herencia</span><span class="sxs-lookup"><span data-stu-id="e2d8b-120">Inheritance</span></span>  
 <span data-ttu-id="e2d8b-121">La mayoría de los usuarios no tendrá <xref:System.Collections.Generic.IEnumerable%601>que implementar y, por tanto, puede omitir esta sección.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-121">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>  
  
 <span data-ttu-id="e2d8b-122">La <xref:System.Xml.Linq.XElement.Value%2A> propiedad es una propiedad de extensión para los tipos `IEnumerable(Of XElement)`que implementan.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-122">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="e2d8b-123">El enlace de esta propiedad de extensión es como el enlace de métodos de extensión: Si un tipo implementa una de las interfaces y define una propiedad con el nombre "Value", esa propiedad tiene prioridad sobre la propiedad de extensión.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-123">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="e2d8b-124">En otras palabras, esta <xref:System.Xml.Linq.XElement.Value%2A> propiedad se puede invalidar definiendo una nueva propiedad en una clase que `IEnumerable(Of XElement)`implementa.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-124">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2d8b-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2d8b-125">Example</span></span>  
 <span data-ttu-id="e2d8b-126">En el ejemplo siguiente se muestra cómo utilizar <xref:System.Xml.Linq.XElement.Value%2A> la propiedad para tener acceso al primer nodo de una <xref:System.Xml.Linq.XElement> colección de objetos.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-126">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="e2d8b-127">En el ejemplo se usa la propiedad del eje secundario para obtener la colección de todos `phone` los nodos secundarios denominados que están en el `contact` objeto.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-127">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]  
  
 <span data-ttu-id="e2d8b-128">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="e2d8b-128">This code displays the following text:</span></span>  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="e2d8b-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2d8b-129">Example</span></span>  
 <span data-ttu-id="e2d8b-130">En el ejemplo siguiente se muestra cómo obtener el valor de un atributo XML de una colección <xref:System.Xml.Linq.XAttribute> de objetos.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-130">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="e2d8b-131">En el ejemplo se usa la propiedad de eje de atributo para mostrar `type` el valor del atributo para `phone` todos los elementos.</span><span class="sxs-lookup"><span data-stu-id="e2d8b-131">The example uses the attribute axis property to display the value of the `type` attribute for all of the `phone` elements.</span></span>  
  
 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]  
  
 <span data-ttu-id="e2d8b-132">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="e2d8b-132">This code displays the following text:</span></span>  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a><span data-ttu-id="e2d8b-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2d8b-133">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="e2d8b-134">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="e2d8b-134">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="e2d8b-135">Literales XML</span><span class="sxs-lookup"><span data-stu-id="e2d8b-135">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="e2d8b-136">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2d8b-136">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="e2d8b-137">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="e2d8b-137">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="e2d8b-138">Propiedad de indexador de extensión</span><span class="sxs-lookup"><span data-stu-id="e2d8b-138">Extension Indexer Property</span></span>](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)
- [<span data-ttu-id="e2d8b-139">Propiedad del eje secundario XML</span><span class="sxs-lookup"><span data-stu-id="e2d8b-139">XML Child Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="e2d8b-140">Propiedad del eje de atributo XML</span><span class="sxs-lookup"><span data-stu-id="e2d8b-140">XML Attribute Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)

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
ms.openlocfilehash: 927158f940d9b96cd06873c7d3e710be91b887e9
ms.sourcegitcommit: 9e18e4a18284ae9e54c515e30d019c0bbff9cd37
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2018
ms.locfileid: "37071624"
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="15aa5-102">Value (Propiedad XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15aa5-102">XML Value Property (Visual Basic)</span></span>
<span data-ttu-id="15aa5-103">Proporciona acceso al valor del primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="15aa5-103">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15aa5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15aa5-104">Syntax</span></span>  
  
```  
object.Value  
```  
  
## <a name="parts"></a><span data-ttu-id="15aa5-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="15aa5-105">Parts</span></span>  
  
|<span data-ttu-id="15aa5-106">Término</span><span class="sxs-lookup"><span data-stu-id="15aa5-106">Term</span></span>|<span data-ttu-id="15aa5-107">Definición</span><span class="sxs-lookup"><span data-stu-id="15aa5-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="15aa5-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="15aa5-108">Required.</span></span> <span data-ttu-id="15aa5-109">Una colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="15aa5-109">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="15aa5-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="15aa5-110">Return Value</span></span>  
 <span data-ttu-id="15aa5-111">A `String` que contiene el valor del primer elemento de la colección, o `Nothing` si la colección está vacía.</span><span class="sxs-lookup"><span data-stu-id="15aa5-111">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15aa5-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15aa5-112">Remarks</span></span>  
 <span data-ttu-id="15aa5-113">El <xref:System.Xml.Linq.XElement.Value%2A> propiedad facilita el acceso al valor del primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="15aa5-113">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="15aa5-114">Esta propiedad comprueba primero si la colección contiene al menos un objeto.</span><span class="sxs-lookup"><span data-stu-id="15aa5-114">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="15aa5-115">Si la colección está vacía, esta propiedad devuelve `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="15aa5-115">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="15aa5-116">En caso contrario, esta propiedad devuelve el valor de la <xref:System.Xml.Linq.XElement.Value%2A> propiedad del primer elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="15aa5-116">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15aa5-117">Al acceder al valor de un atributo XML mediante el '\@' identificador, se devuelve el valor del atributo como un `String` y no es necesario especificar explícitamente la <xref:System.Xml.Linq.XAttribute.Value%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="15aa5-117">When you access the value of an XML attribute using the '\@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="15aa5-118">Para obtener acceso a otros elementos de una colección, puede utilizar la propiedad de indizador de extensión XML.</span><span class="sxs-lookup"><span data-stu-id="15aa5-118">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="15aa5-119">Para obtener más información, consulte [propiedad de indizador de extensión](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span><span class="sxs-lookup"><span data-stu-id="15aa5-119">For more information, see [Extension Indexer Property](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="15aa5-120">Herencia</span><span class="sxs-lookup"><span data-stu-id="15aa5-120">Inheritance</span></span>  
 <span data-ttu-id="15aa5-121">La mayoría de los usuarios no tendrán que implementar <xref:System.Collections.Generic.IEnumerable%601>y, por tanto, puede omitir esta sección.</span><span class="sxs-lookup"><span data-stu-id="15aa5-121">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>  
  
 <span data-ttu-id="15aa5-122">El <xref:System.Xml.Linq.XElement.Value%2A> es una propiedad de extensión para los tipos que implementan `IEnumerable(Of XElement)`.</span><span class="sxs-lookup"><span data-stu-id="15aa5-122">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="15aa5-123">El enlace de esta propiedad de extensión es como el enlace de los métodos de extensión: si un tipo implementa una de las interfaces y define una propiedad que tiene el nombre "Value", esa propiedad tiene prioridad sobre la propiedad de extensión.</span><span class="sxs-lookup"><span data-stu-id="15aa5-123">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="15aa5-124">En otras palabras, esto <xref:System.Xml.Linq.XElement.Value%2A> propiedad se puede invalidar definiendo una nueva propiedad en una clase que implementa `IEnumerable(Of XElement)`.</span><span class="sxs-lookup"><span data-stu-id="15aa5-124">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15aa5-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15aa5-125">Example</span></span>  
 <span data-ttu-id="15aa5-126">En el ejemplo siguiente se muestra cómo utilizar el <xref:System.Xml.Linq.XElement.Value%2A> propiedad que se va a obtener acceso al primer nodo en una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="15aa5-126">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="15aa5-127">En el ejemplo se utiliza la propiedad de eje secundario para obtener la colección de todos los nodos secundarios denominados `phone` que se encuentran en la `contact` objeto.</span><span class="sxs-lookup"><span data-stu-id="15aa5-127">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_1.vb)]  
  
 <span data-ttu-id="15aa5-128">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="15aa5-128">This code displays the following text:</span></span>  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="15aa5-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15aa5-129">Example</span></span>  
 <span data-ttu-id="15aa5-130">En el ejemplo siguiente se muestra cómo obtener el valor de un atributo XML de una colección de <xref:System.Xml.Linq.XAttribute> objetos.</span><span class="sxs-lookup"><span data-stu-id="15aa5-130">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="15aa5-131">En el ejemplo se utiliza la propiedad de eje de atributo para mostrar el valor de la `type` atributo para todos los `phone` elementos.</span><span class="sxs-lookup"><span data-stu-id="15aa5-131">The example uses the attribute axis property to display the value of the `type` attribute for all of the `phone` elements.</span></span>  
  
 [!code-vb[VbXMLSamples#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_2.vb)]  
  
 <span data-ttu-id="15aa5-132">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="15aa5-132">This code displays the following text:</span></span>  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a><span data-ttu-id="15aa5-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="15aa5-133">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [<span data-ttu-id="15aa5-134">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="15aa5-134">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="15aa5-135">Literales XML</span><span class="sxs-lookup"><span data-stu-id="15aa5-135">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="15aa5-136">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15aa5-136">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="15aa5-137">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="15aa5-137">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [<span data-ttu-id="15aa5-138">Propiedad de indexador de extensión</span><span class="sxs-lookup"><span data-stu-id="15aa5-138">Extension Indexer Property</span></span>](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)  
 [<span data-ttu-id="15aa5-139">Propiedad del eje secundario XML</span><span class="sxs-lookup"><span data-stu-id="15aa5-139">XML Child Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [<span data-ttu-id="15aa5-140">Propiedad del eje de atributo XML</span><span class="sxs-lookup"><span data-stu-id="15aa5-140">XML Attribute Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)

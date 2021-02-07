---
description: 'Más información acerca de: propiedad Value de XML (Visual Basic)'
title: Propiedad de valor XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 49762c1fcc0059472a5be11726aa344a001807ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768771"
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="1bbbf-103">Value (Propiedad XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1bbbf-103">XML Value Property (Visual Basic)</span></span>

<span data-ttu-id="1bbbf-104">Proporciona acceso al valor del primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-104">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>

## <a name="syntax"></a><span data-ttu-id="1bbbf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bbbf-105">Syntax</span></span>

```vb
object.Value
```

## <a name="parts"></a><span data-ttu-id="1bbbf-106">Partes</span><span class="sxs-lookup"><span data-stu-id="1bbbf-106">Parts</span></span>

|<span data-ttu-id="1bbbf-107">Término</span><span class="sxs-lookup"><span data-stu-id="1bbbf-107">Term</span></span>|<span data-ttu-id="1bbbf-108">Definición</span><span class="sxs-lookup"><span data-stu-id="1bbbf-108">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="1bbbf-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-109">Required.</span></span> <span data-ttu-id="1bbbf-110">Una colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-110">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  

## <a name="return-value"></a><span data-ttu-id="1bbbf-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1bbbf-111">Return Value</span></span>

 <span data-ttu-id="1bbbf-112">`String`Que contiene el valor del primer elemento de la colección o `Nothing` si la colección está vacía.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-112">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>

## <a name="remarks"></a><span data-ttu-id="1bbbf-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1bbbf-113">Remarks</span></span>

 <span data-ttu-id="1bbbf-114">La <xref:System.Xml.Linq.XElement.Value%2A> propiedad facilita el acceso al valor del primer elemento de una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-114">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="1bbbf-115">Esta propiedad comprueba primero si la colección contiene al menos un objeto.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-115">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="1bbbf-116">Si la colección está vacía, esta propiedad devuelve `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="1bbbf-116">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="1bbbf-117">De lo contrario, esta propiedad devuelve el valor de la <xref:System.Xml.Linq.XElement.Value%2A> propiedad del primer elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-117">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>

> [!NOTE]
> <span data-ttu-id="1bbbf-118">Cuando se tiene acceso al valor de un atributo XML mediante el \@ identificador ' ', el valor del atributo se devuelve como `String` y no es necesario especificar explícitamente la <xref:System.Xml.Linq.XAttribute.Value%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-118">When you access the value of an XML attribute using the '\@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>

 <span data-ttu-id="1bbbf-119">Para tener acceso a otros elementos de una colección, puede usar la propiedad de indizador de extensión XML.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-119">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="1bbbf-120">Para más información, consulte [extensión de la propiedad Indexer](extension-indexer-property.md).</span><span class="sxs-lookup"><span data-stu-id="1bbbf-120">For more information, see [Extension Indexer Property](extension-indexer-property.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="1bbbf-121">Herencia</span><span class="sxs-lookup"><span data-stu-id="1bbbf-121">Inheritance</span></span>

 <span data-ttu-id="1bbbf-122">La mayoría de los usuarios no tendrá que implementar <xref:System.Collections.Generic.IEnumerable%601> y, por tanto, puede omitir esta sección.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-122">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>

 <span data-ttu-id="1bbbf-123">La <xref:System.Xml.Linq.XElement.Value%2A> propiedad es una propiedad de extensión para los tipos que implementan `IEnumerable(Of XElement)` .</span><span class="sxs-lookup"><span data-stu-id="1bbbf-123">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="1bbbf-124">El enlace de esta propiedad de extensión es como el enlace de métodos de extensión: Si un tipo implementa una de las interfaces y define una propiedad con el nombre "Value", esa propiedad tiene prioridad sobre la propiedad de extensión.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-124">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="1bbbf-125">En otras palabras, esta <xref:System.Xml.Linq.XElement.Value%2A> propiedad se puede invalidar definiendo una nueva propiedad en una clase que implementa `IEnumerable(Of XElement)` .</span><span class="sxs-lookup"><span data-stu-id="1bbbf-125">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>

## <a name="example"></a><span data-ttu-id="1bbbf-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1bbbf-126">Example</span></span>

 <span data-ttu-id="1bbbf-127">En el ejemplo siguiente se muestra cómo utilizar la <xref:System.Xml.Linq.XElement.Value%2A> propiedad para tener acceso al primer nodo de una colección de <xref:System.Xml.Linq.XElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-127">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="1bbbf-128">En el ejemplo se usa la propiedad del eje secundario para obtener la colección de todos los nodos secundarios denominados `phone` que están en el `contact` objeto.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-128">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>

 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]

 <span data-ttu-id="1bbbf-129">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="1bbbf-129">This code displays the following text:</span></span>

 `Phone number: 206-555-0144`

## <a name="example"></a><span data-ttu-id="1bbbf-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1bbbf-130">Example</span></span>

 <span data-ttu-id="1bbbf-131">En el ejemplo siguiente se muestra cómo obtener el valor de un atributo XML de una colección de <xref:System.Xml.Linq.XAttribute> objetos.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-131">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="1bbbf-132">En el ejemplo se usa la propiedad de eje de atributo para mostrar el valor del `type` atributo para todos los `phone` elementos.</span><span class="sxs-lookup"><span data-stu-id="1bbbf-132">The example uses the attribute axis property to display the value of the `type` attribute for all of the `phone` elements.</span></span>

 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]

 <span data-ttu-id="1bbbf-133">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="1bbbf-133">This code displays the following text:</span></span>

 ```console
 home
 work
```

## <a name="see-also"></a><span data-ttu-id="1bbbf-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bbbf-134">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="1bbbf-135">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="1bbbf-135">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="1bbbf-136">Literales XML</span><span class="sxs-lookup"><span data-stu-id="1bbbf-136">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="1bbbf-137">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1bbbf-137">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="1bbbf-138">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="1bbbf-138">Extension Methods</span></span>](../../programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="1bbbf-139">Propiedad de indexador de extensión</span><span class="sxs-lookup"><span data-stu-id="1bbbf-139">Extension Indexer Property</span></span>](extension-indexer-property.md)
- [<span data-ttu-id="1bbbf-140">XML Child Axis Property</span><span class="sxs-lookup"><span data-stu-id="1bbbf-140">XML Child Axis Property</span></span>](xml-child-axis-property.md)
- [<span data-ttu-id="1bbbf-141">XML Attribute Axis Property</span><span class="sxs-lookup"><span data-stu-id="1bbbf-141">XML Attribute Axis Property</span></span>](xml-attribute-axis-property.md)

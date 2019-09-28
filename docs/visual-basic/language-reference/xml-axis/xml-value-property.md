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
ms.openlocfilehash: 46f81e39686da30270cd67edeb4c9f2d43e048b3
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592012"
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="5185c-102">Value (Propiedad XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5185c-102">XML Value Property (Visual Basic)</span></span>

<span data-ttu-id="5185c-103">Proporciona acceso al valor del primer elemento de una colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="5185c-103">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>

## <a name="syntax"></a><span data-ttu-id="5185c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5185c-104">Syntax</span></span>

```vb
object.Value
```

## <a name="parts"></a><span data-ttu-id="5185c-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="5185c-105">Parts</span></span>

|<span data-ttu-id="5185c-106">Término</span><span class="sxs-lookup"><span data-stu-id="5185c-106">Term</span></span>|<span data-ttu-id="5185c-107">Definición</span><span class="sxs-lookup"><span data-stu-id="5185c-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="5185c-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="5185c-108">Required.</span></span> <span data-ttu-id="5185c-109">Una colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="5185c-109">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  

## <a name="return-value"></a><span data-ttu-id="5185c-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5185c-110">Return Value</span></span>

 <span data-ttu-id="5185c-111">@No__t-0 que contiene el valor del primer elemento de la colección o `Nothing` si la colección está vacía.</span><span class="sxs-lookup"><span data-stu-id="5185c-111">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>

## <a name="remarks"></a><span data-ttu-id="5185c-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5185c-112">Remarks</span></span>

 <span data-ttu-id="5185c-113">La propiedad <xref:System.Xml.Linq.XElement.Value%2A> facilita el acceso al valor del primer elemento de una colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="5185c-113">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="5185c-114">Esta propiedad comprueba primero si la colección contiene al menos un objeto.</span><span class="sxs-lookup"><span data-stu-id="5185c-114">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="5185c-115">Si la colección está vacía, esta propiedad devuelve `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="5185c-115">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="5185c-116">De lo contrario, esta propiedad devuelve el valor de la propiedad <xref:System.Xml.Linq.XElement.Value%2A> del primer elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="5185c-116">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>

> [!NOTE]
> <span data-ttu-id="5185c-117">Cuando se tiene acceso al valor de un atributo XML mediante el identificador ' \@ ', el valor del atributo se devuelve como `String` y no es necesario especificar explícitamente la propiedad <xref:System.Xml.Linq.XAttribute.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="5185c-117">When you access the value of an XML attribute using the '\@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>

 <span data-ttu-id="5185c-118">Para tener acceso a otros elementos de una colección, puede usar la propiedad de indizador de extensión XML.</span><span class="sxs-lookup"><span data-stu-id="5185c-118">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="5185c-119">Para más información, consulte [extensión de la propiedad Indexer](extension-indexer-property.md).</span><span class="sxs-lookup"><span data-stu-id="5185c-119">For more information, see [Extension Indexer Property](extension-indexer-property.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="5185c-120">Herencia</span><span class="sxs-lookup"><span data-stu-id="5185c-120">Inheritance</span></span>

 <span data-ttu-id="5185c-121">La mayoría de los usuarios no tendrá que implementar <xref:System.Collections.Generic.IEnumerable%601> y, por tanto, puede omitir esta sección.</span><span class="sxs-lookup"><span data-stu-id="5185c-121">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>

 <span data-ttu-id="5185c-122">La propiedad <xref:System.Xml.Linq.XElement.Value%2A> es una propiedad de extensión para los tipos que implementan `IEnumerable(Of XElement)`.</span><span class="sxs-lookup"><span data-stu-id="5185c-122">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="5185c-123">El enlace de esta propiedad de extensión es como el enlace de métodos de extensión: Si un tipo implementa una de las interfaces y define una propiedad con el nombre "Value", esa propiedad tiene prioridad sobre la propiedad de extensión.</span><span class="sxs-lookup"><span data-stu-id="5185c-123">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="5185c-124">En otras palabras, esta propiedad <xref:System.Xml.Linq.XElement.Value%2A> se puede invalidar si se define una nueva propiedad en una clase que implementa `IEnumerable(Of XElement)`.</span><span class="sxs-lookup"><span data-stu-id="5185c-124">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>

## <a name="example"></a><span data-ttu-id="5185c-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5185c-125">Example</span></span>

 <span data-ttu-id="5185c-126">En el ejemplo siguiente se muestra cómo usar la propiedad <xref:System.Xml.Linq.XElement.Value%2A> para tener acceso al primer nodo de una colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="5185c-126">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="5185c-127">En el ejemplo se usa la propiedad del eje secundario para obtener la colección de todos los nodos secundarios denominados `phone` que se encuentran en el objeto `contact`.</span><span class="sxs-lookup"><span data-stu-id="5185c-127">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>

 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]

 <span data-ttu-id="5185c-128">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="5185c-128">This code displays the following text:</span></span>

 `Phone number: 206-555-0144`

## <a name="example"></a><span data-ttu-id="5185c-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5185c-129">Example</span></span>

 <span data-ttu-id="5185c-130">En el ejemplo siguiente se muestra cómo obtener el valor de un atributo XML de una colección de objetos <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5185c-130">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="5185c-131">En el ejemplo se usa la propiedad de eje de atributo para mostrar el valor del atributo `type` de todos los elementos `phone`.</span><span class="sxs-lookup"><span data-stu-id="5185c-131">The example uses the attribute axis property to display the value of the `type` attribute for all of the `phone` elements.</span></span>

 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]

 <span data-ttu-id="5185c-132">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="5185c-132">This code displays the following text:</span></span>

 ```console
 home
 work
```

## <a name="see-also"></a><span data-ttu-id="5185c-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="5185c-133">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="5185c-134">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="5185c-134">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="5185c-135">Literales XML</span><span class="sxs-lookup"><span data-stu-id="5185c-135">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="5185c-136">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5185c-136">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="5185c-137">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="5185c-137">Extension Methods</span></span>](../../programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="5185c-138">Propiedad de indexador de extensión</span><span class="sxs-lookup"><span data-stu-id="5185c-138">Extension Indexer Property</span></span>](extension-indexer-property.md)
- [<span data-ttu-id="5185c-139">Propiedad del eje secundario XML</span><span class="sxs-lookup"><span data-stu-id="5185c-139">XML Child Axis Property</span></span>](xml-child-axis-property.md)
- [<span data-ttu-id="5185c-140">Propiedad del eje de atributo XML</span><span class="sxs-lookup"><span data-stu-id="5185c-140">XML Attribute Axis Property</span></span>](xml-attribute-axis-property.md)

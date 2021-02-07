---
description: 'Más información acerca de: propiedad de eje descendiente XML (Visual Basic)'
title: XML Descendant Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Basic]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: c356d4d6f9a84755e9df171b26060fc6bfc4ead6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768784"
---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="ea4f4-103">Propiedad de eje descendiente XML Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea4f4-103">XML Descendant Axis Property (Visual Basic)</span></span>

<span data-ttu-id="ea4f4-104">Proporciona acceso a los descendientes de los elementos siguientes: un <xref:System.Xml.Linq.XElement> objeto, un <xref:System.Xml.Linq.XDocument> objeto, una colección de <xref:System.Xml.Linq.XElement> objetos o una colección de <xref:System.Xml.Linq.XDocument> objetos.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-104">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

## <a name="syntax"></a><span data-ttu-id="ea4f4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea4f4-105">Syntax</span></span>

```vb
object...<descendant>
```

## <a name="parts"></a><span data-ttu-id="ea4f4-106">Partes</span><span class="sxs-lookup"><span data-stu-id="ea4f4-106">Parts</span></span>

<span data-ttu-id="ea4f4-107">`object` Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-107">`object` Required.</span></span> <span data-ttu-id="ea4f4-108">Un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-108">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

<span data-ttu-id="ea4f4-109">`...<` Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-109">`...<` Required.</span></span> <span data-ttu-id="ea4f4-110">Denota el inicio de una propiedad de eje descendiente.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-110">Denotes the start of a descendant axis property.</span></span>

<span data-ttu-id="ea4f4-111">`descendant` Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-111">`descendant` Required.</span></span> <span data-ttu-id="ea4f4-112">Nombre de los nodos descendientes a los que se va a tener acceso, con el formato [ `prefix:]name` .</span><span class="sxs-lookup"><span data-stu-id="ea4f4-112">Name of the descendant nodes to access, of the form [`prefix:]name`.</span></span>

|<span data-ttu-id="ea4f4-113">Parte</span><span class="sxs-lookup"><span data-stu-id="ea4f4-113">Part</span></span>|<span data-ttu-id="ea4f4-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea4f4-114">Description</span></span>|
|----------|-----------------|
|`prefix`|<span data-ttu-id="ea4f4-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-115">Optional.</span></span> <span data-ttu-id="ea4f4-116">Prefijo de espacio de nombres XML para el nodo descendiente.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-116">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="ea4f4-117">Debe ser un espacio de nombres XML global que se define mediante una `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-117">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|
|`name`|<span data-ttu-id="ea4f4-118">Necesario.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-118">Required.</span></span> <span data-ttu-id="ea4f4-119">Nombre local del nodo descendiente.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-119">Local name of the descendant node.</span></span> <span data-ttu-id="ea4f4-120">Vea [nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="ea4f4-120">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|

<span data-ttu-id="ea4f4-121">`>` Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-121">`>` Required.</span></span> <span data-ttu-id="ea4f4-122">Denota el final de una propiedad de eje descendiente.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-122">Denotes the end of a descendant axis property.</span></span>

## <a name="return-value"></a><span data-ttu-id="ea4f4-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ea4f4-123">Return Value</span></span>

<span data-ttu-id="ea4f4-124">Una colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>

## <a name="remarks"></a><span data-ttu-id="ea4f4-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ea4f4-125">Remarks</span></span>

<span data-ttu-id="ea4f4-126">Puede usar una propiedad de eje descendiente XML para tener acceso a los nodos descendientes por nombre desde un <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> objeto o, o desde una colección de <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> objetos o.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-126">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="ea4f4-127">Utilice la `Value` propiedad XML para tener acceso al valor del primer nodo descendiente de la colección devuelta.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-127">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="ea4f4-128">Para obtener más información, vea [propiedad valor XML](xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="ea4f4-128">For more information, see [XML Value Property](xml-value-property.md).</span></span>

<span data-ttu-id="ea4f4-129">El compilador Visual Basic convierte las propiedades de los ejes descendientes en llamadas al <xref:System.Xml.Linq.XContainer.Descendants%2A> método.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-129">The Visual Basic compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="ea4f4-130">Espacios de nombres XML</span><span class="sxs-lookup"><span data-stu-id="ea4f4-130">XML Namespaces</span></span>

<span data-ttu-id="ea4f4-131">El nombre de una propiedad de eje descendiente solo puede utilizar espacios de nombres XML declarados globalmente con la `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-131">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="ea4f4-132">No puede utilizar espacios de nombres XML declarados localmente dentro de literales de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-132">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="ea4f4-133">Para obtener más información, vea [instrucción Imports (espacio de nombres XML)](../statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="ea4f4-133">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>

## <a name="example"></a><span data-ttu-id="ea4f4-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea4f4-134">Example</span></span>

<span data-ttu-id="ea4f4-135">En el ejemplo siguiente se muestra cómo obtener acceso al valor del primer nodo descendiente denominado `name` y los valores de todos los nodos descendientes denominados `phone` del `contacts` objeto.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-135">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

<span data-ttu-id="ea4f4-136">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="ea4f4-136">This code displays the following text:</span></span>

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a><span data-ttu-id="ea4f4-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea4f4-137">Example</span></span>

<span data-ttu-id="ea4f4-138">En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="ea4f4-138">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="ea4f4-139">A continuación, usa el prefijo del espacio de nombres para crear un literal XML y tener acceso al valor del primer nodo secundario con el nombre completo `ns:name` .</span><span class="sxs-lookup"><span data-stu-id="ea4f4-139">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

<span data-ttu-id="ea4f4-140">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="ea4f4-140">This code displays the following text:</span></span>

`Name: Patrick Hines`

## <a name="see-also"></a><span data-ttu-id="ea4f4-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea4f4-141">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="ea4f4-142">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="ea4f4-142">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="ea4f4-143">Literales XML</span><span class="sxs-lookup"><span data-stu-id="ea4f4-143">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="ea4f4-144">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ea4f4-144">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="ea4f4-145">Nombres de atributos y elementos XML declarados</span><span class="sxs-lookup"><span data-stu-id="ea4f4-145">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)

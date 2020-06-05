---
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
ms.openlocfilehash: 52544619171dbc7034baeb5feb61395d81096387
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400258"
---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="d3d7e-102">Propiedad de eje descendiente XML Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3d7e-102">XML Descendant Axis Property (Visual Basic)</span></span>

<span data-ttu-id="d3d7e-103">Proporciona acceso a los descendientes de los elementos siguientes: un <xref:System.Xml.Linq.XElement> objeto, un <xref:System.Xml.Linq.XDocument> objeto, una colección de <xref:System.Xml.Linq.XElement> objetos o una colección de <xref:System.Xml.Linq.XDocument> objetos.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

## <a name="syntax"></a><span data-ttu-id="d3d7e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3d7e-104">Syntax</span></span>

```vb
object...<descendant>
```

## <a name="parts"></a><span data-ttu-id="d3d7e-105">Partes</span><span class="sxs-lookup"><span data-stu-id="d3d7e-105">Parts</span></span>

<span data-ttu-id="d3d7e-106">`object` Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-106">`object` Required.</span></span> <span data-ttu-id="d3d7e-107">Un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

<span data-ttu-id="d3d7e-108">`...<` Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-108">`...<` Required.</span></span> <span data-ttu-id="d3d7e-109">Denota el inicio de una propiedad de eje descendiente.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-109">Denotes the start of a descendant axis property.</span></span>

<span data-ttu-id="d3d7e-110">`descendant` Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-110">`descendant` Required.</span></span> <span data-ttu-id="d3d7e-111">Nombre de los nodos descendientes a los que se va a tener acceso, con el formato [ `prefix:]name` .</span><span class="sxs-lookup"><span data-stu-id="d3d7e-111">Name of the descendant nodes to access, of the form [`prefix:]name`.</span></span>

|<span data-ttu-id="d3d7e-112">Parte</span><span class="sxs-lookup"><span data-stu-id="d3d7e-112">Part</span></span>|<span data-ttu-id="d3d7e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3d7e-113">Description</span></span>|
|----------|-----------------|
|`prefix`|<span data-ttu-id="d3d7e-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-114">Optional.</span></span> <span data-ttu-id="d3d7e-115">Prefijo de espacio de nombres XML para el nodo descendiente.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-115">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="d3d7e-116">Debe ser un espacio de nombres XML global que se define mediante una `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-116">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|
|`name`|<span data-ttu-id="d3d7e-117">Necesario.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-117">Required.</span></span> <span data-ttu-id="d3d7e-118">Nombre local del nodo descendiente.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-118">Local name of the descendant node.</span></span> <span data-ttu-id="d3d7e-119">Vea [nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="d3d7e-119">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|

<span data-ttu-id="d3d7e-120">`>` Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-120">`>` Required.</span></span> <span data-ttu-id="d3d7e-121">Denota el final de una propiedad de eje descendiente.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-121">Denotes the end of a descendant axis property.</span></span>

## <a name="return-value"></a><span data-ttu-id="d3d7e-122">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d3d7e-122">Return Value</span></span>

<span data-ttu-id="d3d7e-123">Colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-123">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>

## <a name="remarks"></a><span data-ttu-id="d3d7e-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d3d7e-124">Remarks</span></span>

<span data-ttu-id="d3d7e-125">Puede usar una propiedad de eje descendiente XML para tener acceso a los nodos descendientes por nombre desde un <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> objeto o, o desde una colección de <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> objetos o.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-125">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="d3d7e-126">Utilice la `Value` propiedad XML para tener acceso al valor del primer nodo descendiente de la colección devuelta.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-126">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="d3d7e-127">Para obtener más información, vea [propiedad valor XML](xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="d3d7e-127">For more information, see [XML Value Property](xml-value-property.md).</span></span>

<span data-ttu-id="d3d7e-128">El compilador Visual Basic convierte las propiedades de los ejes descendientes en llamadas al <xref:System.Xml.Linq.XContainer.Descendants%2A> método.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-128">The Visual Basic compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="d3d7e-129">Espacios de nombres XML</span><span class="sxs-lookup"><span data-stu-id="d3d7e-129">XML Namespaces</span></span>

<span data-ttu-id="d3d7e-130">El nombre de una propiedad de eje descendiente solo puede utilizar espacios de nombres XML declarados globalmente con la `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-130">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="d3d7e-131">No puede utilizar espacios de nombres XML declarados localmente dentro de literales de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-131">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="d3d7e-132">Para obtener más información, vea [instrucción Imports (espacio de nombres XML)](../statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="d3d7e-132">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>

## <a name="example"></a><span data-ttu-id="d3d7e-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d3d7e-133">Example</span></span>

<span data-ttu-id="d3d7e-134">En el ejemplo siguiente se muestra cómo obtener acceso al valor del primer nodo descendiente denominado `name` y los valores de todos los nodos descendientes denominados `phone` del `contacts` objeto.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-134">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

<span data-ttu-id="d3d7e-135">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="d3d7e-135">This code displays the following text:</span></span>

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a><span data-ttu-id="d3d7e-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d3d7e-136">Example</span></span>

<span data-ttu-id="d3d7e-137">En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="d3d7e-137">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="d3d7e-138">A continuación, usa el prefijo del espacio de nombres para crear un literal XML y tener acceso al valor del primer nodo secundario con el nombre completo `ns:name` .</span><span class="sxs-lookup"><span data-stu-id="d3d7e-138">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

<span data-ttu-id="d3d7e-139">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="d3d7e-139">This code displays the following text:</span></span>

`Name: Patrick Hines`

## <a name="see-also"></a><span data-ttu-id="d3d7e-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3d7e-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="d3d7e-141">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="d3d7e-141">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="d3d7e-142">Literales XML</span><span class="sxs-lookup"><span data-stu-id="d3d7e-142">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="d3d7e-143">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d3d7e-143">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="d3d7e-144">Nombres de atributos y elementos XML declarados</span><span class="sxs-lookup"><span data-stu-id="d3d7e-144">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)

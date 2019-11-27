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
ms.openlocfilehash: b2bf524214fa8ecca215d50c198b23d127e3b400
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349444"
---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="2977a-102">Propiedad de eje descendiente XML Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2977a-102">XML Descendant Axis Property (Visual Basic)</span></span>

<span data-ttu-id="2977a-103">Proporciona acceso a los descendientes de los elementos siguientes: un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="2977a-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

## <a name="syntax"></a><span data-ttu-id="2977a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2977a-104">Syntax</span></span>

```vb
object...<descendant>
```

## <a name="parts"></a><span data-ttu-id="2977a-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="2977a-105">Parts</span></span>

<span data-ttu-id="2977a-106">`object` Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2977a-106">`object` Required.</span></span> <span data-ttu-id="2977a-107">Un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="2977a-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

<span data-ttu-id="2977a-108">`...<` Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2977a-108">`...<` Required.</span></span> <span data-ttu-id="2977a-109">Denota el inicio de una propiedad de eje descendiente.</span><span class="sxs-lookup"><span data-stu-id="2977a-109">Denotes the start of a descendant axis property.</span></span>

<span data-ttu-id="2977a-110">`descendant` Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2977a-110">`descendant` Required.</span></span> <span data-ttu-id="2977a-111">Nombre de los nodos descendientes a los que se va a tener acceso, con el formato [`prefix:]name`.</span><span class="sxs-lookup"><span data-stu-id="2977a-111">Name of the descendant nodes to access, of the form [`prefix:]name`.</span></span>

|<span data-ttu-id="2977a-112">Parte</span><span class="sxs-lookup"><span data-stu-id="2977a-112">Part</span></span>|<span data-ttu-id="2977a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="2977a-113">Description</span></span>|
|----------|-----------------|
|`prefix`|<span data-ttu-id="2977a-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="2977a-114">Optional.</span></span> <span data-ttu-id="2977a-115">Prefijo de espacio de nombres XML para el nodo descendiente.</span><span class="sxs-lookup"><span data-stu-id="2977a-115">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="2977a-116">Debe ser un espacio de nombres XML global que se define mediante una instrucción `Imports`.</span><span class="sxs-lookup"><span data-stu-id="2977a-116">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|
|`name`|<span data-ttu-id="2977a-117">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2977a-117">Required.</span></span> <span data-ttu-id="2977a-118">Nombre local del nodo descendiente.</span><span class="sxs-lookup"><span data-stu-id="2977a-118">Local name of the descendant node.</span></span> <span data-ttu-id="2977a-119">Vea [nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="2977a-119">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|

<span data-ttu-id="2977a-120">`>` Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2977a-120">`>` Required.</span></span> <span data-ttu-id="2977a-121">Denota el final de una propiedad de eje descendiente.</span><span class="sxs-lookup"><span data-stu-id="2977a-121">Denotes the end of a descendant axis property.</span></span>

## <a name="return-value"></a><span data-ttu-id="2977a-122">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2977a-122">Return Value</span></span>

<span data-ttu-id="2977a-123">Una colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="2977a-123">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>

## <a name="remarks"></a><span data-ttu-id="2977a-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2977a-124">Remarks</span></span>

<span data-ttu-id="2977a-125">Puede usar una propiedad de eje descendiente XML para tener acceso a los nodos descendientes por nombre de un objeto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>, o de una colección de objetos <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="2977a-125">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="2977a-126">Utilice la propiedad `Value` XML para tener acceso al valor del primer nodo descendiente de la colección devuelta.</span><span class="sxs-lookup"><span data-stu-id="2977a-126">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="2977a-127">Para obtener más información, vea [propiedad valor XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="2977a-127">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>

<span data-ttu-id="2977a-128">El compilador Visual Basic convierte las propiedades de los ejes descendientes en llamadas al método <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="2977a-128">The Visual Basic compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="2977a-129">Espacios de nombres XML</span><span class="sxs-lookup"><span data-stu-id="2977a-129">XML Namespaces</span></span>

<span data-ttu-id="2977a-130">El nombre de una propiedad de eje descendiente solo puede utilizar espacios de nombres XML declarados globalmente con la instrucción `Imports`.</span><span class="sxs-lookup"><span data-stu-id="2977a-130">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="2977a-131">No puede utilizar espacios de nombres XML declarados localmente dentro de literales de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="2977a-131">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="2977a-132">Para obtener más información, vea [instrucción Imports (espacio de nombres XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="2977a-132">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>

## <a name="example"></a><span data-ttu-id="2977a-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2977a-133">Example</span></span>

<span data-ttu-id="2977a-134">En el ejemplo siguiente se muestra cómo obtener acceso al valor del primer nodo descendiente denominado `name` y los valores de todos los nodos descendientes denominados `phone` del objeto `contacts`.</span><span class="sxs-lookup"><span data-stu-id="2977a-134">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

<span data-ttu-id="2977a-135">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="2977a-135">This code displays the following text:</span></span>

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a><span data-ttu-id="2977a-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2977a-136">Example</span></span>

<span data-ttu-id="2977a-137">En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="2977a-137">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="2977a-138">A continuación, usa el prefijo del espacio de nombres para crear un literal XML y tener acceso al valor del primer nodo secundario con el nombre completo `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="2977a-138">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

<span data-ttu-id="2977a-139">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="2977a-139">This code displays the following text:</span></span>

`Name: Patrick Hines`

## <a name="see-also"></a><span data-ttu-id="2977a-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="2977a-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="2977a-141">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="2977a-141">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="2977a-142">Literales XML</span><span class="sxs-lookup"><span data-stu-id="2977a-142">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="2977a-143">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2977a-143">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="2977a-144">Nombres de atributos y elementos XML declarados</span><span class="sxs-lookup"><span data-stu-id="2977a-144">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)

---
title: Propiedad de eje descendiente XML Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Baisc]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: 3b8d13e606f28896cae88162d572470e49af3739
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730287"
---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="09d7c-102">Propiedad de eje descendiente XML Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09d7c-102">XML Descendant Axis Property (Visual Basic)</span></span>
<span data-ttu-id="09d7c-103">Proporciona acceso a los descendientes de los siguientes valores: una <xref:System.Xml.Linq.XElement> objeto, un <xref:System.Xml.Linq.XDocument> (objeto), una colección de <xref:System.Xml.Linq.XElement> objetos o una colección de <xref:System.Xml.Linq.XDocument> objetos.</span><span class="sxs-lookup"><span data-stu-id="09d7c-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09d7c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09d7c-104">Syntax</span></span>  
  
```  
object...<descendant>  
```  
  
## <a name="parts"></a><span data-ttu-id="09d7c-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="09d7c-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="09d7c-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="09d7c-106">Required.</span></span> <span data-ttu-id="09d7c-107">Un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="09d7c-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
 <span data-ttu-id="09d7c-108">...<</span><span class="sxs-lookup"><span data-stu-id="09d7c-108">...<</span></span>  
 <span data-ttu-id="09d7c-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="09d7c-109">Required.</span></span> <span data-ttu-id="09d7c-110">Denota el inicio de una propiedad de eje descendiente.</span><span class="sxs-lookup"><span data-stu-id="09d7c-110">Denotes the start of a descendant axis property.</span></span>  
  
 `descendant`  
 <span data-ttu-id="09d7c-111">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="09d7c-111">Required.</span></span> <span data-ttu-id="09d7c-112">Nombre de los nodos descendientes para tener acceso a la forma [`prefix``:`]`name`.</span><span class="sxs-lookup"><span data-stu-id="09d7c-112">Name of the descendant nodes to access, of the form [`prefix``:`]`name`.</span></span>  
  
|<span data-ttu-id="09d7c-113">Parte</span><span class="sxs-lookup"><span data-stu-id="09d7c-113">Part</span></span>|<span data-ttu-id="09d7c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="09d7c-114">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="09d7c-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="09d7c-115">Optional.</span></span> <span data-ttu-id="09d7c-116">Prefijo de espacio de nombres XML para el nodo descendiente.</span><span class="sxs-lookup"><span data-stu-id="09d7c-116">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="09d7c-117">Debe ser un espacio de nombres XML global que se define utilizando un `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="09d7c-117">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="09d7c-118">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="09d7c-118">Required.</span></span> <span data-ttu-id="09d7c-119">Nombre local del nodo descendiente.</span><span class="sxs-lookup"><span data-stu-id="09d7c-119">Local name of the descendant node.</span></span> <span data-ttu-id="09d7c-120">Consulte [nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="09d7c-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="09d7c-121">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="09d7c-121">Required.</span></span> <span data-ttu-id="09d7c-122">Denota el final de una propiedad de eje descendiente.</span><span class="sxs-lookup"><span data-stu-id="09d7c-122">Denotes the end of a descendant axis property.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09d7c-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="09d7c-123">Return Value</span></span>  
 <span data-ttu-id="09d7c-124">Una colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="09d7c-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09d7c-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="09d7c-125">Remarks</span></span>  
 <span data-ttu-id="09d7c-126">Puede usar una propiedad de eje descendiente XML para tener acceso a los nodos descendientes por nombre desde un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> objeto, o de una colección de <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> objetos.</span><span class="sxs-lookup"><span data-stu-id="09d7c-126">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="09d7c-127">Use el código XML `Value` propiedad para tener acceso al valor del primer nodo descendiente de la colección devuelta.</span><span class="sxs-lookup"><span data-stu-id="09d7c-127">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="09d7c-128">Para obtener más información, consulte [propiedad Value de XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="09d7c-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="09d7c-129">El compilador de Visual Basic convierte las propiedades de eje descendiente en llamadas a la <xref:System.Xml.Linq.XContainer.Descendants%2A> método.</span><span class="sxs-lookup"><span data-stu-id="09d7c-129">The Visual Basic compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="09d7c-130">Espacios de nombres XML</span><span class="sxs-lookup"><span data-stu-id="09d7c-130">XML Namespaces</span></span>  
 <span data-ttu-id="09d7c-131">El nombre de una propiedad de eje descendiente puede usar solo espacios de nombres XML declarados globalmente con la `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="09d7c-131">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="09d7c-132">No puede utilizar espacios de nombres XML declarados localmente dentro de literales de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="09d7c-132">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="09d7c-133">Para obtener más información, consulte [instrucción Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="09d7c-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="09d7c-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09d7c-134">Example</span></span>  
 <span data-ttu-id="09d7c-135">El ejemplo siguiente muestra cómo tener acceso al valor del primer nodo descendiente denominado `name` y los valores de todos los nodos descendientes denominados `phone` desde el `contacts` objeto.</span><span class="sxs-lookup"><span data-stu-id="09d7c-135">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]  
  
 <span data-ttu-id="09d7c-136">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="09d7c-136">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="09d7c-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09d7c-137">Example</span></span>  
 <span data-ttu-id="09d7c-138">En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="09d7c-138">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="09d7c-139">A continuación, usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al valor del primer nodo secundario con el nombre completo `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="09d7c-139">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]  
  
 <span data-ttu-id="09d7c-140">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="09d7c-140">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="09d7c-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="09d7c-141">See also</span></span>
- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="09d7c-142">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="09d7c-142">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="09d7c-143">Literales XML</span><span class="sxs-lookup"><span data-stu-id="09d7c-143">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="09d7c-144">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="09d7c-144">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="09d7c-145">Nombres de atributos y elementos XML declarados</span><span class="sxs-lookup"><span data-stu-id="09d7c-145">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)

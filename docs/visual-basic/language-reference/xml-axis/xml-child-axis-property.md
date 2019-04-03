---
title: Propiedades de eje secundario XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyChildAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
ms.openlocfilehash: 8f8283e7ed09e657a20addab0b203b3d99420d3a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838820"
---
# <a name="xml-child-axis-property-visual-basic"></a><span data-ttu-id="99035-102">Propiedades de eje secundario XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99035-102">XML Child Axis Property (Visual Basic)</span></span>
<span data-ttu-id="99035-103">Proporciona el acceso a los elementos secundarios de uno de los siguientes: un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="99035-103">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99035-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99035-104">Syntax</span></span>  
  
```  
object.<child>  
```  
  
## <a name="parts"></a><span data-ttu-id="99035-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="99035-105">Parts</span></span>  
  
|<span data-ttu-id="99035-106">Término</span><span class="sxs-lookup"><span data-stu-id="99035-106">Term</span></span>|<span data-ttu-id="99035-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="99035-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="99035-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="99035-108">Required.</span></span> <span data-ttu-id="99035-109">Un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="99035-109">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>|  
|<span data-ttu-id="99035-110">.<</span><span class="sxs-lookup"><span data-stu-id="99035-110">.<</span></span>|<span data-ttu-id="99035-111">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="99035-111">Required.</span></span> <span data-ttu-id="99035-112">Denota el inicio de una propiedad de eje secundario.</span><span class="sxs-lookup"><span data-stu-id="99035-112">Denotes the start of a child axis property.</span></span>|  
|`child`|<span data-ttu-id="99035-113">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="99035-113">Required.</span></span> <span data-ttu-id="99035-114">Nombre de los nodos secundarios para obtener acceso a la forma [`prefix:]name`.</span><span class="sxs-lookup"><span data-stu-id="99035-114">Name of the child nodes to access, of the form [`prefix:]name`.</span></span><br /><br /> <span data-ttu-id="99035-115">-   `Prefix` -Opcional.</span><span class="sxs-lookup"><span data-stu-id="99035-115">-   `Prefix` - Optional.</span></span> <span data-ttu-id="99035-116">Prefijo de espacio de nombres XML para el nodo secundario.</span><span class="sxs-lookup"><span data-stu-id="99035-116">XML namespace prefix for the child node.</span></span> <span data-ttu-id="99035-117">Debe ser un espacio de nombres XML global definido con una instrucción `Imports`.</span><span class="sxs-lookup"><span data-stu-id="99035-117">Must be a global XML namespace defined with an `Imports` statement.</span></span><br /><span data-ttu-id="99035-118">-   `Name` -Required.</span><span class="sxs-lookup"><span data-stu-id="99035-118">-   `Name` - Required.</span></span> <span data-ttu-id="99035-119">Nombre del nodo secundario local.</span><span class="sxs-lookup"><span data-stu-id="99035-119">Local child node name.</span></span> <span data-ttu-id="99035-120">Consulte [nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="99035-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
|>|<span data-ttu-id="99035-121">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="99035-121">Required.</span></span> <span data-ttu-id="99035-122">Denota el final de una propiedad de eje secundario.</span><span class="sxs-lookup"><span data-stu-id="99035-122">Denotes the end of a child axis property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="99035-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="99035-123">Return Value</span></span>  
 <span data-ttu-id="99035-124">Una colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="99035-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99035-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="99035-125">Remarks</span></span>  
 <span data-ttu-id="99035-126">Puede usar una propiedad de eje secundario XML para tener acceso a los nodos secundarios por nombre desde un objeto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>, o desde una colección de objetos <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="99035-126">You can use an XML child axis property to access child nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="99035-127">Utilice la propiedad XML `Value` para tener acceso al valor del primer nodo secundario de la colección devuelta.</span><span class="sxs-lookup"><span data-stu-id="99035-127">Use the XML `Value` property to access the value of the first child node in the returned collection.</span></span> <span data-ttu-id="99035-128">Para obtener más información, consulte [propiedad Value de XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="99035-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="99035-129">El compilador de Visual Basic convierte las propiedades del eje secundario en llamadas a la <xref:System.Xml.Linq.XContainer.Elements%2A> método.</span><span class="sxs-lookup"><span data-stu-id="99035-129">The Visual Basic compiler converts child axis properties to calls to the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="99035-130">Espacios de nombres XML</span><span class="sxs-lookup"><span data-stu-id="99035-130">XML Namespaces</span></span>  
 <span data-ttu-id="99035-131">El nombre de una propiedad de eje secundario puede usar únicamente prefijos de espacios de nombres XML declarados globalmente con la instrucción `Imports`.</span><span class="sxs-lookup"><span data-stu-id="99035-131">The name in a child axis property can use only XML namespace prefixes declared globally with the `Imports` statement.</span></span> <span data-ttu-id="99035-132">No puede utilizar prefijos de espacio de nombres XML declarados localmente dentro de literales de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="99035-132">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="99035-133">Para obtener más información, consulte [instrucción Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="99035-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="99035-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99035-134">Example</span></span>  
 <span data-ttu-id="99035-135">En el ejemplo siguiente se muestra cómo obtener acceso a los nodos secundarios llamados `phone` desde el objeto `contact`.</span><span class="sxs-lookup"><span data-stu-id="99035-135">The following example shows how to access the child nodes named `phone` from the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#17)]  
  
 <span data-ttu-id="99035-136">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="99035-136">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="99035-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99035-137">Example</span></span>  
 <span data-ttu-id="99035-138">En el ejemplo siguiente se muestra cómo tener acceso a los nodos secundarios denominados `phone` desde la colección devuelta por la propiedad `contact` del eje secundario del objeto `contacts`.</span><span class="sxs-lookup"><span data-stu-id="99035-138">The following example shows how to access the child nodes named `phone` from the collection returned by the `contact` child axis property of the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#18)]  
  
 <span data-ttu-id="99035-139">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="99035-139">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="99035-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99035-140">Example</span></span>  
 <span data-ttu-id="99035-141">En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="99035-141">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="99035-142">A continuación, se usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario con el nombre completo `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="99035-142">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 <span data-ttu-id="99035-143">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="99035-143">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="99035-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="99035-144">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="99035-145">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="99035-145">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="99035-146">Literales XML</span><span class="sxs-lookup"><span data-stu-id="99035-146">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="99035-147">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="99035-147">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="99035-148">Nombres de atributos y elementos XML declarados</span><span class="sxs-lookup"><span data-stu-id="99035-148">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)

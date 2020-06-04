---
title: XML Child Axis Property
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
ms.openlocfilehash: 90dc22d12be5566fa1ee40f6b0e48eff8088e67b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400271"
---
# <a name="xml-child-axis-property-visual-basic"></a><span data-ttu-id="8ae64-102">Propiedades de eje secundario XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ae64-102">XML Child Axis Property (Visual Basic)</span></span>
<span data-ttu-id="8ae64-103">Proporciona el acceso a los elementos secundarios de uno de los siguientes: un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="8ae64-103">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ae64-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ae64-104">Syntax</span></span>  
  
```vb  
object.<child>  
```  
  
## <a name="parts"></a><span data-ttu-id="8ae64-105">Partes</span><span class="sxs-lookup"><span data-stu-id="8ae64-105">Parts</span></span>  
  
|<span data-ttu-id="8ae64-106">Término</span><span class="sxs-lookup"><span data-stu-id="8ae64-106">Term</span></span>|<span data-ttu-id="8ae64-107">Definición</span><span class="sxs-lookup"><span data-stu-id="8ae64-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="8ae64-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8ae64-108">Required.</span></span> <span data-ttu-id="8ae64-109">Un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="8ae64-109">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>|  
|<span data-ttu-id="8ae64-110">. <</span><span class="sxs-lookup"><span data-stu-id="8ae64-110">.<</span></span>|<span data-ttu-id="8ae64-111">Necesario.</span><span class="sxs-lookup"><span data-stu-id="8ae64-111">Required.</span></span> <span data-ttu-id="8ae64-112">Denota el inicio de una propiedad de eje secundario.</span><span class="sxs-lookup"><span data-stu-id="8ae64-112">Denotes the start of a child axis property.</span></span>|  
|`child`|<span data-ttu-id="8ae64-113">Necesario.</span><span class="sxs-lookup"><span data-stu-id="8ae64-113">Required.</span></span> <span data-ttu-id="8ae64-114">Nombre de los nodos secundarios a los que se va a tener acceso, del formulario `[prefix:]name` .</span><span class="sxs-lookup"><span data-stu-id="8ae64-114">Name of the child nodes to access, of the form `[prefix:]name`.</span></span><br /><br /> <span data-ttu-id="8ae64-115">-   `Prefix`Opta.</span><span class="sxs-lookup"><span data-stu-id="8ae64-115">-   `Prefix` - Optional.</span></span> <span data-ttu-id="8ae64-116">Prefijo de espacio de nombres XML para el nodo secundario.</span><span class="sxs-lookup"><span data-stu-id="8ae64-116">XML namespace prefix for the child node.</span></span> <span data-ttu-id="8ae64-117">Debe ser un espacio de nombres XML global definido con una instrucción `Imports`.</span><span class="sxs-lookup"><span data-stu-id="8ae64-117">Must be a global XML namespace defined with an `Imports` statement.</span></span><br /><span data-ttu-id="8ae64-118">-   `Name`Desee.</span><span class="sxs-lookup"><span data-stu-id="8ae64-118">-   `Name` - Required.</span></span> <span data-ttu-id="8ae64-119">Nombre del nodo secundario local.</span><span class="sxs-lookup"><span data-stu-id="8ae64-119">Local child node name.</span></span> <span data-ttu-id="8ae64-120">Vea [nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="8ae64-120">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
|>|<span data-ttu-id="8ae64-121">Necesario.</span><span class="sxs-lookup"><span data-stu-id="8ae64-121">Required.</span></span> <span data-ttu-id="8ae64-122">Denota el final de una propiedad de eje secundario.</span><span class="sxs-lookup"><span data-stu-id="8ae64-122">Denotes the end of a child axis property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="8ae64-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8ae64-123">Return Value</span></span>  
 <span data-ttu-id="8ae64-124">Colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="8ae64-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ae64-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8ae64-125">Remarks</span></span>  
 <span data-ttu-id="8ae64-126">Puede usar una propiedad de eje secundario XML para tener acceso a los nodos secundarios por nombre desde un objeto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>, o desde una colección de objetos <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="8ae64-126">You can use an XML child axis property to access child nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="8ae64-127">Utilice la propiedad XML `Value` para tener acceso al valor del primer nodo secundario de la colección devuelta.</span><span class="sxs-lookup"><span data-stu-id="8ae64-127">Use the XML `Value` property to access the value of the first child node in the returned collection.</span></span> <span data-ttu-id="8ae64-128">Para obtener más información, vea [propiedad valor XML](xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="8ae64-128">For more information, see [XML Value Property](xml-value-property.md).</span></span>  
  
 <span data-ttu-id="8ae64-129">El compilador Visual Basic convierte las propiedades del eje secundario en llamadas al <xref:System.Xml.Linq.XContainer.Elements%2A> método.</span><span class="sxs-lookup"><span data-stu-id="8ae64-129">The Visual Basic compiler converts child axis properties to calls to the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="8ae64-130">Espacios de nombres XML</span><span class="sxs-lookup"><span data-stu-id="8ae64-130">XML Namespaces</span></span>  
 <span data-ttu-id="8ae64-131">El nombre de una propiedad de eje secundario puede usar únicamente prefijos de espacios de nombres XML declarados globalmente con la instrucción `Imports`.</span><span class="sxs-lookup"><span data-stu-id="8ae64-131">The name in a child axis property can use only XML namespace prefixes declared globally with the `Imports` statement.</span></span> <span data-ttu-id="8ae64-132">No puede utilizar prefijos de espacio de nombres XML declarados localmente dentro de literales de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="8ae64-132">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="8ae64-133">Para obtener más información, vea [instrucción Imports (espacio de nombres XML)](../statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="8ae64-133">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ae64-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ae64-134">Example</span></span>  
 <span data-ttu-id="8ae64-135">En el ejemplo siguiente se muestra cómo obtener acceso a los nodos secundarios llamados `phone` desde el objeto `contact`.</span><span class="sxs-lookup"><span data-stu-id="8ae64-135">The following example shows how to access the child nodes named `phone` from the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#17)]  
  
 <span data-ttu-id="8ae64-136">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="8ae64-136">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="8ae64-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ae64-137">Example</span></span>  
 <span data-ttu-id="8ae64-138">En el ejemplo siguiente se muestra cómo tener acceso a los nodos secundarios denominados `phone` desde la colección devuelta por la propiedad `contact` del eje secundario del objeto `contacts`.</span><span class="sxs-lookup"><span data-stu-id="8ae64-138">The following example shows how to access the child nodes named `phone` from the collection returned by the `contact` child axis property of the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#18)]  
  
 <span data-ttu-id="8ae64-139">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="8ae64-139">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="8ae64-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ae64-140">Example</span></span>  
 <span data-ttu-id="8ae64-141">En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="8ae64-141">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="8ae64-142">A continuación, se usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario con el nombre completo `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="8ae64-142">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 <span data-ttu-id="8ae64-143">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="8ae64-143">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="8ae64-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ae64-144">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="8ae64-145">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="8ae64-145">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="8ae64-146">Literales XML</span><span class="sxs-lookup"><span data-stu-id="8ae64-146">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="8ae64-147">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8ae64-147">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="8ae64-148">Nombres de atributos y elementos XML declarados</span><span class="sxs-lookup"><span data-stu-id="8ae64-148">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)

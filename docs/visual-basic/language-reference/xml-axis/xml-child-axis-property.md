---
description: 'Más información acerca de: propiedad de eje secundario XML (Visual Basic)'
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
ms.openlocfilehash: 54920ebd35635f215eb6cb58867be1e4a7acd847
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768797"
---
# <a name="xml-child-axis-property-visual-basic"></a><span data-ttu-id="26d3e-103">Propiedades de eje secundario XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26d3e-103">XML Child Axis Property (Visual Basic)</span></span>

<span data-ttu-id="26d3e-104">Proporciona el acceso a los elementos secundarios de uno de los siguientes: un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="26d3e-104">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26d3e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26d3e-105">Syntax</span></span>  
  
```vb  
object.<child>  
```  
  
## <a name="parts"></a><span data-ttu-id="26d3e-106">Partes</span><span class="sxs-lookup"><span data-stu-id="26d3e-106">Parts</span></span>  
  
|<span data-ttu-id="26d3e-107">Término</span><span class="sxs-lookup"><span data-stu-id="26d3e-107">Term</span></span>|<span data-ttu-id="26d3e-108">Definición</span><span class="sxs-lookup"><span data-stu-id="26d3e-108">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="26d3e-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="26d3e-109">Required.</span></span> <span data-ttu-id="26d3e-110">Un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="26d3e-110">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>|  
|<span data-ttu-id="26d3e-111">. <</span><span class="sxs-lookup"><span data-stu-id="26d3e-111">.<</span></span>|<span data-ttu-id="26d3e-112">Necesario.</span><span class="sxs-lookup"><span data-stu-id="26d3e-112">Required.</span></span> <span data-ttu-id="26d3e-113">Denota el inicio de una propiedad de eje secundario.</span><span class="sxs-lookup"><span data-stu-id="26d3e-113">Denotes the start of a child axis property.</span></span>|  
|`child`|<span data-ttu-id="26d3e-114">Necesario.</span><span class="sxs-lookup"><span data-stu-id="26d3e-114">Required.</span></span> <span data-ttu-id="26d3e-115">Nombre de los nodos secundarios a los que se va a tener acceso, del formulario `[prefix:]name` .</span><span class="sxs-lookup"><span data-stu-id="26d3e-115">Name of the child nodes to access, of the form `[prefix:]name`.</span></span><br /><br /> <span data-ttu-id="26d3e-116">-   `Prefix` Opta.</span><span class="sxs-lookup"><span data-stu-id="26d3e-116">-   `Prefix` - Optional.</span></span> <span data-ttu-id="26d3e-117">Prefijo de espacio de nombres XML para el nodo secundario.</span><span class="sxs-lookup"><span data-stu-id="26d3e-117">XML namespace prefix for the child node.</span></span> <span data-ttu-id="26d3e-118">Debe ser un espacio de nombres XML global definido con una instrucción `Imports`.</span><span class="sxs-lookup"><span data-stu-id="26d3e-118">Must be a global XML namespace defined with an `Imports` statement.</span></span><br /><span data-ttu-id="26d3e-119">-   `Name` Desee.</span><span class="sxs-lookup"><span data-stu-id="26d3e-119">-   `Name` - Required.</span></span> <span data-ttu-id="26d3e-120">Nombre del nodo secundario local.</span><span class="sxs-lookup"><span data-stu-id="26d3e-120">Local child node name.</span></span> <span data-ttu-id="26d3e-121">Vea [nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="26d3e-121">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
|>|<span data-ttu-id="26d3e-122">Necesario.</span><span class="sxs-lookup"><span data-stu-id="26d3e-122">Required.</span></span> <span data-ttu-id="26d3e-123">Denota el final de una propiedad de eje secundario.</span><span class="sxs-lookup"><span data-stu-id="26d3e-123">Denotes the end of a child axis property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="26d3e-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="26d3e-124">Return Value</span></span>  

 <span data-ttu-id="26d3e-125">Una colección de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="26d3e-125">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26d3e-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="26d3e-126">Remarks</span></span>  

 <span data-ttu-id="26d3e-127">Puede usar una propiedad de eje secundario XML para tener acceso a los nodos secundarios por nombre desde un objeto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>, o desde una colección de objetos <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="26d3e-127">You can use an XML child axis property to access child nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="26d3e-128">Utilice la propiedad XML `Value` para tener acceso al valor del primer nodo secundario de la colección devuelta.</span><span class="sxs-lookup"><span data-stu-id="26d3e-128">Use the XML `Value` property to access the value of the first child node in the returned collection.</span></span> <span data-ttu-id="26d3e-129">Para obtener más información, vea [propiedad valor XML](xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="26d3e-129">For more information, see [XML Value Property](xml-value-property.md).</span></span>  
  
 <span data-ttu-id="26d3e-130">El compilador Visual Basic convierte las propiedades del eje secundario en llamadas al <xref:System.Xml.Linq.XContainer.Elements%2A> método.</span><span class="sxs-lookup"><span data-stu-id="26d3e-130">The Visual Basic compiler converts child axis properties to calls to the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="26d3e-131">Espacios de nombres XML</span><span class="sxs-lookup"><span data-stu-id="26d3e-131">XML Namespaces</span></span>  

 <span data-ttu-id="26d3e-132">El nombre de una propiedad de eje secundario puede usar únicamente prefijos de espacios de nombres XML declarados globalmente con la instrucción `Imports`.</span><span class="sxs-lookup"><span data-stu-id="26d3e-132">The name in a child axis property can use only XML namespace prefixes declared globally with the `Imports` statement.</span></span> <span data-ttu-id="26d3e-133">No puede utilizar prefijos de espacio de nombres XML declarados localmente dentro de literales de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="26d3e-133">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="26d3e-134">Para obtener más información, vea [instrucción Imports (espacio de nombres XML)](../statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="26d3e-134">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="26d3e-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26d3e-135">Example</span></span>  

 <span data-ttu-id="26d3e-136">En el ejemplo siguiente se muestra cómo obtener acceso a los nodos secundarios llamados `phone` desde el objeto `contact`.</span><span class="sxs-lookup"><span data-stu-id="26d3e-136">The following example shows how to access the child nodes named `phone` from the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#17)]  
  
 <span data-ttu-id="26d3e-137">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="26d3e-137">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="26d3e-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26d3e-138">Example</span></span>  

 <span data-ttu-id="26d3e-139">En el ejemplo siguiente se muestra cómo tener acceso a los nodos secundarios denominados `phone` desde la colección devuelta por la propiedad `contact` del eje secundario del objeto `contacts`.</span><span class="sxs-lookup"><span data-stu-id="26d3e-139">The following example shows how to access the child nodes named `phone` from the collection returned by the `contact` child axis property of the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#18)]  
  
 <span data-ttu-id="26d3e-140">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="26d3e-140">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="26d3e-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26d3e-141">Example</span></span>  

 <span data-ttu-id="26d3e-142">En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="26d3e-142">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="26d3e-143">A continuación, se usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario con el nombre completo `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="26d3e-143">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 <span data-ttu-id="26d3e-144">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="26d3e-144">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="26d3e-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="26d3e-145">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="26d3e-146">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="26d3e-146">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="26d3e-147">Literales XML</span><span class="sxs-lookup"><span data-stu-id="26d3e-147">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="26d3e-148">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26d3e-148">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="26d3e-149">Nombres de atributos y elementos XML declarados</span><span class="sxs-lookup"><span data-stu-id="26d3e-149">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)

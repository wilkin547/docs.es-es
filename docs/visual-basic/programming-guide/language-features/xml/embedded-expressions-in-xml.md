---
title: Expresiones incrustadas en XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: 0cdb960160457108ddf18c554dae5f5993269833
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332352"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="63bd5-102">Expresiones incrustadas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63bd5-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="63bd5-103">Las expresiones incrustadas le permiten crear literales XML que contienen expresiones que se evalúan en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="63bd5-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="63bd5-104">La sintaxis de una expresión incrustada es `<%=` `expression` `%>`, que es igual que la sintaxis que se usa en ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="63bd5-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in ASP.NET.</span></span>  
  
 <span data-ttu-id="63bd5-105">Por ejemplo, puede crear un literal de elemento XML, combinando expresiones incrustadas con contenido de texto literal.</span><span class="sxs-lookup"><span data-stu-id="63bd5-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 <span data-ttu-id="63bd5-106">Si `isbnNumber` contiene el entero 12345 y `modifiedDate` contiene la fecha 3/5/2006, cuando se ejecuta este código, el valor de `book` es:</span><span class="sxs-lookup"><span data-stu-id="63bd5-106">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="63bd5-107">Ubicación y validación de expresiones incrustadas</span><span class="sxs-lookup"><span data-stu-id="63bd5-107">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="63bd5-108">Las expresiones incrustadas solo pueden aparecer en determinadas ubicaciones dentro de expresiones literales XML.</span><span class="sxs-lookup"><span data-stu-id="63bd5-108">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="63bd5-109">La ubicación de la expresión controla qué tipos puede devolver la expresión y cómo se controla `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="63bd5-109">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="63bd5-110">En la tabla siguiente se describen las ubicaciones permitidas y los tipos de expresiones incrustadas.</span><span class="sxs-lookup"><span data-stu-id="63bd5-110">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="63bd5-111">Ubicación en literal</span><span class="sxs-lookup"><span data-stu-id="63bd5-111">Location in literal</span></span>|<span data-ttu-id="63bd5-112">Tipo de expresión</span><span class="sxs-lookup"><span data-stu-id="63bd5-112">Type of expression</span></span>|<span data-ttu-id="63bd5-113">Control de `Nothing`</span><span class="sxs-lookup"><span data-stu-id="63bd5-113">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="63bd5-114">Nombre del elemento XML</span><span class="sxs-lookup"><span data-stu-id="63bd5-114">XML element name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="63bd5-115">Error</span><span class="sxs-lookup"><span data-stu-id="63bd5-115">Error</span></span>|  
|<span data-ttu-id="63bd5-116">Contenido del elemento XML</span><span class="sxs-lookup"><span data-stu-id="63bd5-116">XML element content</span></span>|<span data-ttu-id="63bd5-117">`Object` o matriz de `Object`</span><span class="sxs-lookup"><span data-stu-id="63bd5-117">`Object` or array of `Object`</span></span>|<span data-ttu-id="63bd5-118">Omitido</span><span class="sxs-lookup"><span data-stu-id="63bd5-118">Ignored</span></span>|  
|<span data-ttu-id="63bd5-119">Nombre del atributo del elemento XML</span><span class="sxs-lookup"><span data-stu-id="63bd5-119">XML element attribute name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="63bd5-120">Error, a menos que el valor del atributo también sea `Nothing`</span><span class="sxs-lookup"><span data-stu-id="63bd5-120">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="63bd5-121">Valor del atributo del elemento XML</span><span class="sxs-lookup"><span data-stu-id="63bd5-121">XML element attribute value</span></span>|`Object`|<span data-ttu-id="63bd5-122">Declaración de atributo omitida</span><span class="sxs-lookup"><span data-stu-id="63bd5-122">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="63bd5-123">Atributo de elemento XML</span><span class="sxs-lookup"><span data-stu-id="63bd5-123">XML element attribute</span></span>|<span data-ttu-id="63bd5-124"><xref:System.Xml.Linq.XAttribute> o una colección de <xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="63bd5-124"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="63bd5-125">Omitido</span><span class="sxs-lookup"><span data-stu-id="63bd5-125">Ignored</span></span>|  
|<span data-ttu-id="63bd5-126">Elemento raíz del documento XML</span><span class="sxs-lookup"><span data-stu-id="63bd5-126">XML document root element</span></span>|<span data-ttu-id="63bd5-127"><xref:System.Xml.Linq.XElement> o una colección de un objeto <xref:System.Xml.Linq.XElement> y un número arbitrario de objetos <xref:System.Xml.Linq.XProcessingInstruction> y <xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="63bd5-127"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="63bd5-128">Omitido</span><span class="sxs-lookup"><span data-stu-id="63bd5-128">Ignored</span></span>|  
  
- <span data-ttu-id="63bd5-129">Ejemplo de una expresión incrustada en un nombre de elemento XML:</span><span class="sxs-lookup"><span data-stu-id="63bd5-129">Example of an embedded expression in an XML element name:</span></span>  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- <span data-ttu-id="63bd5-130">Ejemplo de una expresión incrustada en el contenido de un elemento XML:</span><span class="sxs-lookup"><span data-stu-id="63bd5-130">Example of an embedded expression in the content of an XML element:</span></span>  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- <span data-ttu-id="63bd5-131">Ejemplo de una expresión incrustada en un nombre de atributo de elemento XML:</span><span class="sxs-lookup"><span data-stu-id="63bd5-131">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- <span data-ttu-id="63bd5-132">Ejemplo de una expresión incrustada en un valor de atributo de elemento XML:</span><span class="sxs-lookup"><span data-stu-id="63bd5-132">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- <span data-ttu-id="63bd5-133">Ejemplo de una expresión incrustada en un atributo de elemento XML:</span><span class="sxs-lookup"><span data-stu-id="63bd5-133">Example of an embedded expression in an XML element attribute:</span></span>  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- <span data-ttu-id="63bd5-134">Ejemplo de una expresión incrustada en un elemento raíz de un documento XML:</span><span class="sxs-lookup"><span data-stu-id="63bd5-134">Example of an embedded expression in an XML document root element:</span></span>  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 <span data-ttu-id="63bd5-135">Si habilita `Option Strict`, el compilador comprueba que el tipo de cada expresión insertada se amplía al tipo requerido.</span><span class="sxs-lookup"><span data-stu-id="63bd5-135">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="63bd5-136">La única excepción es para el elemento raíz de un documento XML, que se comprueba cuando se ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="63bd5-136">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="63bd5-137">Si compila sin `Option Strict`, puede incrustar expresiones de tipo `Object` y se comprueba su tipo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="63bd5-137">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="63bd5-138">En ubicaciones donde el contenido es opcional, se omiten las expresiones incrustadas que contienen `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="63bd5-138">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="63bd5-139">Esto significa que no es necesario comprobar que el contenido de los elementos, los valores de atributo y los elementos de la matriz no se `Nothing` antes de utilizar un literal XML.</span><span class="sxs-lookup"><span data-stu-id="63bd5-139">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="63bd5-140">Los valores obligatorios, como los nombres de elementos y atributos, no se pueden `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="63bd5-140">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="63bd5-141">Para obtener más información sobre el uso de una expresión incrustada en un tipo determinado de literal, vea [literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="63bd5-141">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="63bd5-142">Reglas de ámbito</span><span class="sxs-lookup"><span data-stu-id="63bd5-142">Scoping Rules</span></span>  
 <span data-ttu-id="63bd5-143">El compilador convierte cada literal XML en una llamada de constructor para el tipo de literal adecuado.</span><span class="sxs-lookup"><span data-stu-id="63bd5-143">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="63bd5-144">El contenido literal y las expresiones incrustadas en un literal XML se pasan como argumentos al constructor.</span><span class="sxs-lookup"><span data-stu-id="63bd5-144">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="63bd5-145">Esto significa que todos los elementos de programación Visual Basic disponibles para un literal XML también están disponibles para sus expresiones incrustadas.</span><span class="sxs-lookup"><span data-stu-id="63bd5-145">This means that all Visual Basic programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="63bd5-146">Dentro de un literal XML, puede tener acceso a los prefijos de espacio de nombres XML declarados con la instrucción `Imports`.</span><span class="sxs-lookup"><span data-stu-id="63bd5-146">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="63bd5-147">Puede declarar un nuevo prefijo de espacio de nombres XML, u ocultar un prefijo de espacio de nombres XML existente, en un elemento mediante el atributo `xmlns`.</span><span class="sxs-lookup"><span data-stu-id="63bd5-147">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="63bd5-148">El nuevo espacio de nombres está disponible para los nodos secundarios de ese elemento, pero no para los literales XML de las expresiones incrustadas.</span><span class="sxs-lookup"><span data-stu-id="63bd5-148">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="63bd5-149">Al declarar un prefijo de espacio de nombres XML mediante el atributo de espacio de nombres `xmlns`, el valor de atributo debe ser una cadena constante.</span><span class="sxs-lookup"><span data-stu-id="63bd5-149">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="63bd5-150">En este sentido, el uso del atributo `xmlns` es como usar la instrucción `Imports` para declarar un espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="63bd5-150">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="63bd5-151">No se puede usar una expresión insertada para especificar el valor del espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="63bd5-151">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63bd5-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="63bd5-152">See also</span></span>

- [<span data-ttu-id="63bd5-153">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63bd5-153">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="63bd5-154">Literal de documento XML</span><span class="sxs-lookup"><span data-stu-id="63bd5-154">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="63bd5-155">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="63bd5-155">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="63bd5-156">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="63bd5-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="63bd5-157">Imports (instrucción), espacio de nombres y tipo .NET</span><span class="sxs-lookup"><span data-stu-id="63bd5-157">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="63bd5-158">Introducción a literales XML</span><span class="sxs-lookup"><span data-stu-id="63bd5-158">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)

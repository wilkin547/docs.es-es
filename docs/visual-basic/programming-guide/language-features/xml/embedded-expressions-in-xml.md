---
description: 'Más información sobre: expresiones incrustadas en XML (Visual Basic)'
title: Expresiones insertadas en XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: 52cf8341cb0a55abad230543bbc6367aea071142
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433192"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="bcdb8-103">Expresiones incrustadas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bcdb8-103">Embedded Expressions in XML (Visual Basic)</span></span>

<span data-ttu-id="bcdb8-104">Las expresiones incrustadas le permiten crear literales XML que contienen expresiones que se evalúan en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-104">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="bcdb8-105">La sintaxis de una expresión incrustada es `<%=` `expression` `%>` , que es la misma que la sintaxis que se usa en ASP.net.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-105">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in ASP.NET.</span></span>  
  
 <span data-ttu-id="bcdb8-106">Por ejemplo, puede crear un literal de elemento XML, combinando expresiones incrustadas con contenido de texto literal.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-106">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 <span data-ttu-id="bcdb8-107">Si `isbnNumber` contiene el entero 12345 y `modifiedDate` contiene la fecha 3/5/2006, cuando se ejecuta este código, el valor de `book` es:</span><span class="sxs-lookup"><span data-stu-id="bcdb8-107">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="bcdb8-108">Ubicación y validación de expresiones incrustadas</span><span class="sxs-lookup"><span data-stu-id="bcdb8-108">Embedded Expression Location and Validation</span></span>  

 <span data-ttu-id="bcdb8-109">Las expresiones incrustadas solo pueden aparecer en determinadas ubicaciones dentro de expresiones literales XML.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-109">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="bcdb8-110">La ubicación de la expresión controla qué tipos puede devolver la expresión y cómo `Nothing` se controla.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-110">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="bcdb8-111">En la tabla siguiente se describen las ubicaciones permitidas y los tipos de expresiones incrustadas.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-111">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="bcdb8-112">Ubicación en literal</span><span class="sxs-lookup"><span data-stu-id="bcdb8-112">Location in literal</span></span>|<span data-ttu-id="bcdb8-113">Tipo de expresión</span><span class="sxs-lookup"><span data-stu-id="bcdb8-113">Type of expression</span></span>|<span data-ttu-id="bcdb8-114">Control de `Nothing`</span><span class="sxs-lookup"><span data-stu-id="bcdb8-114">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="bcdb8-115">Nombre del elemento XML</span><span class="sxs-lookup"><span data-stu-id="bcdb8-115">XML element name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="bcdb8-116">Error</span><span class="sxs-lookup"><span data-stu-id="bcdb8-116">Error</span></span>|  
|<span data-ttu-id="bcdb8-117">Contenido del elemento XML</span><span class="sxs-lookup"><span data-stu-id="bcdb8-117">XML element content</span></span>|<span data-ttu-id="bcdb8-118">`Object` o matriz de `Object`</span><span class="sxs-lookup"><span data-stu-id="bcdb8-118">`Object` or array of `Object`</span></span>|<span data-ttu-id="bcdb8-119">Omitido</span><span class="sxs-lookup"><span data-stu-id="bcdb8-119">Ignored</span></span>|  
|<span data-ttu-id="bcdb8-120">Nombre del atributo del elemento XML</span><span class="sxs-lookup"><span data-stu-id="bcdb8-120">XML element attribute name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="bcdb8-121">Error, a menos que el valor del atributo también sea `Nothing`</span><span class="sxs-lookup"><span data-stu-id="bcdb8-121">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="bcdb8-122">Valor del atributo del elemento XML</span><span class="sxs-lookup"><span data-stu-id="bcdb8-122">XML element attribute value</span></span>|`Object`|<span data-ttu-id="bcdb8-123">Declaración de atributo omitida</span><span class="sxs-lookup"><span data-stu-id="bcdb8-123">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="bcdb8-124">Atributo de elemento XML</span><span class="sxs-lookup"><span data-stu-id="bcdb8-124">XML element attribute</span></span>|<span data-ttu-id="bcdb8-125"><xref:System.Xml.Linq.XAttribute> o una colección de <xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="bcdb8-125"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="bcdb8-126">Omitido</span><span class="sxs-lookup"><span data-stu-id="bcdb8-126">Ignored</span></span>|  
|<span data-ttu-id="bcdb8-127">Elemento raíz del documento XML</span><span class="sxs-lookup"><span data-stu-id="bcdb8-127">XML document root element</span></span>|<span data-ttu-id="bcdb8-128"><xref:System.Xml.Linq.XElement> o una colección de un <xref:System.Xml.Linq.XElement> objeto y un número arbitrario de <xref:System.Xml.Linq.XProcessingInstruction> <xref:System.Xml.Linq.XComment> objetos y</span><span class="sxs-lookup"><span data-stu-id="bcdb8-128"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="bcdb8-129">Omitido</span><span class="sxs-lookup"><span data-stu-id="bcdb8-129">Ignored</span></span>|  
  
- <span data-ttu-id="bcdb8-130">Ejemplo de una expresión incrustada en un nombre de elemento XML:</span><span class="sxs-lookup"><span data-stu-id="bcdb8-130">Example of an embedded expression in an XML element name:</span></span>  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- <span data-ttu-id="bcdb8-131">Ejemplo de una expresión incrustada en el contenido de un elemento XML:</span><span class="sxs-lookup"><span data-stu-id="bcdb8-131">Example of an embedded expression in the content of an XML element:</span></span>  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- <span data-ttu-id="bcdb8-132">Ejemplo de una expresión incrustada en un nombre de atributo de elemento XML:</span><span class="sxs-lookup"><span data-stu-id="bcdb8-132">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- <span data-ttu-id="bcdb8-133">Ejemplo de una expresión incrustada en un valor de atributo de elemento XML:</span><span class="sxs-lookup"><span data-stu-id="bcdb8-133">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- <span data-ttu-id="bcdb8-134">Ejemplo de una expresión incrustada en un atributo de elemento XML:</span><span class="sxs-lookup"><span data-stu-id="bcdb8-134">Example of an embedded expression in an XML element attribute:</span></span>  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- <span data-ttu-id="bcdb8-135">Ejemplo de una expresión incrustada en un elemento raíz de un documento XML:</span><span class="sxs-lookup"><span data-stu-id="bcdb8-135">Example of an embedded expression in an XML document root element:</span></span>  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 <span data-ttu-id="bcdb8-136">Si habilita `Option Strict` , el compilador comprueba que el tipo de cada expresión insertada se amplía al tipo requerido.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-136">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="bcdb8-137">La única excepción es para el elemento raíz de un documento XML, que se comprueba cuando se ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-137">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="bcdb8-138">Si compila sin `Option Strict` , puede incrustar expresiones de tipo `Object` y su tipo se comprueba en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-138">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="bcdb8-139">En ubicaciones donde el contenido es opcional, se omiten las expresiones incrustadas que contienen `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="bcdb8-139">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="bcdb8-140">Esto significa que no es necesario comprobar que el contenido de los elementos, los valores de atributo y los elementos de matriz no son `Nothing` antes de usar un literal XML.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-140">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="bcdb8-141">Los valores obligatorios, como los nombres de elementos y atributos, no pueden ser `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="bcdb8-141">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="bcdb8-142">Para obtener más información sobre el uso de una expresión incrustada en un tipo determinado de literal, vea [literal de documento XML](../../../language-reference/xml-literals/xml-document-literal.md), [literal de elemento XML](../../../language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="bcdb8-142">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="bcdb8-143">Reglas de ámbito</span><span class="sxs-lookup"><span data-stu-id="bcdb8-143">Scoping Rules</span></span>  

 <span data-ttu-id="bcdb8-144">El compilador convierte cada literal XML en una llamada de constructor para el tipo de literal adecuado.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-144">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="bcdb8-145">El contenido literal y las expresiones incrustadas en un literal XML se pasan como argumentos al constructor.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-145">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="bcdb8-146">Esto significa que todos los elementos de programación Visual Basic disponibles para un literal XML también están disponibles para sus expresiones incrustadas.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-146">This means that all Visual Basic programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="bcdb8-147">Dentro de un literal XML, puede tener acceso a los prefijos de espacio de nombres XML declarados con la `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-147">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="bcdb8-148">Puede declarar un nuevo prefijo de espacio de nombres XML, u ocultar un prefijo de espacio de nombres XML existente, en un elemento mediante el `xmlns` atributo.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-148">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="bcdb8-149">El nuevo espacio de nombres está disponible para los nodos secundarios de ese elemento, pero no para los literales XML de las expresiones incrustadas.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-149">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bcdb8-150">Al declarar un prefijo de espacio de nombres XML mediante el `xmlns` atributo de espacio de nombres, el valor de atributo debe ser una cadena constante.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-150">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="bcdb8-151">En este sentido, el uso del `xmlns` atributo es como usar la `Imports` instrucción para declarar un espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-151">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="bcdb8-152">No se puede usar una expresión insertada para especificar el valor del espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="bcdb8-152">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcdb8-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bcdb8-153">See also</span></span>

- [<span data-ttu-id="bcdb8-154">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bcdb8-154">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="bcdb8-155">Literal de documento XML</span><span class="sxs-lookup"><span data-stu-id="bcdb8-155">XML Document Literal</span></span>](../../../language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="bcdb8-156">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="bcdb8-156">XML Element Literal</span></span>](../../../language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="bcdb8-157">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bcdb8-157">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="bcdb8-158">Instrucción Imports (Tipo y espacio de nombres de .NET)</span><span class="sxs-lookup"><span data-stu-id="bcdb8-158">Imports Statement (.NET Namespace and Type)</span></span>](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="bcdb8-159">Introducción a literales XML</span><span class="sxs-lookup"><span data-stu-id="bcdb8-159">XML Literals Overview</span></span>](xml-literals-overview.md)

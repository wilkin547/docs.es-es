---
title: Literal de elemento XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: d6a91de4e279816bafd29f46bb4f5422cbd934ff
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400194"
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="b1bbf-102">Literal de elemento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1bbf-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="b1bbf-103">Literal que representa un <xref:System.Xml.Linq.XElement> objeto.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="syntax"></a><span data-ttu-id="b1bbf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1bbf-104">Syntax</span></span>

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a><span data-ttu-id="b1bbf-105">Partes</span><span class="sxs-lookup"><span data-stu-id="b1bbf-105">Parts</span></span>

- `<`

  <span data-ttu-id="b1bbf-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-106">Required.</span></span> <span data-ttu-id="b1bbf-107">Abre la etiqueta del elemento de inicio.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-107">Opens the starting element tag.</span></span>

- `name`

  <span data-ttu-id="b1bbf-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-108">Required.</span></span> <span data-ttu-id="b1bbf-109">Nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-109">Name of the element.</span></span> <span data-ttu-id="b1bbf-110">El formato es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b1bbf-110">The format is one of the following:</span></span>

  - <span data-ttu-id="b1bbf-111">Texto literal del nombre del elemento, con el formato `[ePrefix:]eName` , donde:</span><span class="sxs-lookup"><span data-stu-id="b1bbf-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>

    |<span data-ttu-id="b1bbf-112">Parte</span><span class="sxs-lookup"><span data-stu-id="b1bbf-112">Part</span></span>|<span data-ttu-id="b1bbf-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b1bbf-113">Description</span></span>|
    |---|---|
    |`ePrefix`|<span data-ttu-id="b1bbf-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-114">Optional.</span></span> <span data-ttu-id="b1bbf-115">Prefijo de espacio de nombres XML para el elemento.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="b1bbf-116">Debe ser un espacio de nombres XML global que se define con una `Imports` instrucción en el archivo o en el nivel de proyecto, o un espacio de nombres XML local que se define en este elemento o en un elemento primario.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`eName`|<span data-ttu-id="b1bbf-117">Necesario.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-117">Required.</span></span> <span data-ttu-id="b1bbf-118">Nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-118">Name of the element.</span></span> <span data-ttu-id="b1bbf-119">El formato es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b1bbf-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="b1bbf-120">: Texto literal.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-120">- Literal text.</span></span> <span data-ttu-id="b1bbf-121">Vea [nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="b1bbf-121">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="b1bbf-122">-Expresión insertada con el formato `<%= eNameExp %>` .</span><span class="sxs-lookup"><span data-stu-id="b1bbf-122">- Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="b1bbf-123">El tipo de `eNameExp` debe ser `String` o un tipo que se pueda convertir implícitamente en <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="b1bbf-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|

  - <span data-ttu-id="b1bbf-124">Expresión insertada con el formato `<%= nameExp %>` .</span><span class="sxs-lookup"><span data-stu-id="b1bbf-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="b1bbf-125">El tipo de `nameExp` debe ser `String` o un tipo que se pueda convertir implícitamente a <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="b1bbf-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="b1bbf-126">No se permite una expresión incrustada en una etiqueta de cierre de un elemento.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-126">An embedded expression is not allowed in a closing tag of an element.</span></span>

- `attributeList`

  <span data-ttu-id="b1bbf-127">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-127">Optional.</span></span> <span data-ttu-id="b1bbf-128">Lista de atributos declarados en el literal.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-128">List of attributes declared in the literal.</span></span>

  `attribute [ attribute ... ]`

  <span data-ttu-id="b1bbf-129">Cada `attribute` una de ellas tiene una de las siguientes sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b1bbf-129">Each `attribute` has one of the following syntaxes:</span></span>

  - <span data-ttu-id="b1bbf-130">Asignación de atributos, con el formato `[aPrefix:]aName=aValue` , donde:</span><span class="sxs-lookup"><span data-stu-id="b1bbf-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>

    |<span data-ttu-id="b1bbf-131">Parte</span><span class="sxs-lookup"><span data-stu-id="b1bbf-131">Part</span></span>|<span data-ttu-id="b1bbf-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="b1bbf-132">Description</span></span>|
    |---|---|
    |`aPrefix`|<span data-ttu-id="b1bbf-133">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-133">Optional.</span></span> <span data-ttu-id="b1bbf-134">Prefijo de espacio de nombres XML para el atributo.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="b1bbf-135">Debe ser un espacio de nombres XML global que se define con una `Imports` instrucción o un espacio de nombres XML local que se define en este elemento o en un elemento primario.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`aName`|<span data-ttu-id="b1bbf-136">Necesario.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-136">Required.</span></span> <span data-ttu-id="b1bbf-137">Nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-137">Name of the attribute.</span></span> <span data-ttu-id="b1bbf-138">El formato es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b1bbf-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="b1bbf-139">: Texto literal.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-139">- Literal text.</span></span> <span data-ttu-id="b1bbf-140">Vea [nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="b1bbf-140">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="b1bbf-141">-Expresión insertada con el formato `<%= aNameExp %>` .</span><span class="sxs-lookup"><span data-stu-id="b1bbf-141">- Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="b1bbf-142">El tipo de `aNameExp` debe ser `String` o un tipo que se pueda convertir implícitamente en <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="b1bbf-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|
    |`aValue`|<span data-ttu-id="b1bbf-143">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-143">Optional.</span></span> <span data-ttu-id="b1bbf-144">Valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-144">Value of the attribute.</span></span> <span data-ttu-id="b1bbf-145">El formato es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b1bbf-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="b1bbf-146">-Texto literal, entre comillas.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-146">- Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="b1bbf-147">-Expresión insertada con el formato `<%= aValueExp %>` .</span><span class="sxs-lookup"><span data-stu-id="b1bbf-147">- Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="b1bbf-148">Se permite cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-148">Any type is allowed.</span></span>|

  - <span data-ttu-id="b1bbf-149">Expresión insertada con el formato `<%= aExp %>` .</span><span class="sxs-lookup"><span data-stu-id="b1bbf-149">Embedded expression of the form `<%= aExp %>`.</span></span>

- `/>`

  <span data-ttu-id="b1bbf-150">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-150">Optional.</span></span> <span data-ttu-id="b1bbf-151">Indica que el elemento es un elemento vacío, sin contenido.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-151">Indicates that the element is an empty element, without content.</span></span>

- `>`

  <span data-ttu-id="b1bbf-152">Necesario.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-152">Required.</span></span> <span data-ttu-id="b1bbf-153">Finaliza la etiqueta de elemento inicial o vacía.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-153">Ends the beginning or empty element tag.</span></span>

- `elementContents`

  <span data-ttu-id="b1bbf-154">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-154">Optional.</span></span> <span data-ttu-id="b1bbf-155">Contenido del elemento.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-155">Content of the element.</span></span>

  `content [ content ... ]`

  <span data-ttu-id="b1bbf-156">Cada `content` puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b1bbf-156">Each `content` can be one of the following:</span></span>

  - <span data-ttu-id="b1bbf-157">Texto literal.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-157">Literal text.</span></span> <span data-ttu-id="b1bbf-158">Todos los espacios en blanco de `elementContents` se convierten en significativos si hay texto literal.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>

  - <span data-ttu-id="b1bbf-159">Expresión insertada con el formato `<%= contentExp %>` .</span><span class="sxs-lookup"><span data-stu-id="b1bbf-159">Embedded expression of the form `<%= contentExp %>`.</span></span>

  - <span data-ttu-id="b1bbf-160">Literal de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-160">XML element literal.</span></span>

  - <span data-ttu-id="b1bbf-161">Literal de comentario XML.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-161">XML comment literal.</span></span> <span data-ttu-id="b1bbf-162">Vea [literal de comentario XML](xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="b1bbf-162">See [XML Comment Literal](xml-comment-literal.md).</span></span>

  - <span data-ttu-id="b1bbf-163">Literal de instrucción de procesamiento XML.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-163">XML processing instruction literal.</span></span> <span data-ttu-id="b1bbf-164">Vea [literal de instrucción de procesamiento XML](xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="b1bbf-164">See [XML Processing Instruction Literal](xml-processing-instruction-literal.md).</span></span>

  - <span data-ttu-id="b1bbf-165">Literal de CDATA XML.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-165">XML CDATA literal.</span></span> <span data-ttu-id="b1bbf-166">Vea [literal CDATA XML](xml-cdata-literal.md).</span><span class="sxs-lookup"><span data-stu-id="b1bbf-166">See [XML CDATA Literal](xml-cdata-literal.md).</span></span>

- `</[name]>`

  <span data-ttu-id="b1bbf-167">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-167">Optional.</span></span> <span data-ttu-id="b1bbf-168">Representa la etiqueta de cierre del elemento.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="b1bbf-169">`name`No se permite el parámetro opcional cuando es el resultado de una expresión incrustada.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>

## <a name="return-value"></a><span data-ttu-id="b1bbf-170">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b1bbf-170">Return Value</span></span>

<span data-ttu-id="b1bbf-171">Objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-171">An <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1bbf-172">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b1bbf-172">Remarks</span></span>

<span data-ttu-id="b1bbf-173">Puede usar la sintaxis de literales del elemento XML para crear <xref:System.Xml.Linq.XElement> objetos en el código.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>

> [!NOTE]
> <span data-ttu-id="b1bbf-174">Un literal XML puede abarcar varias líneas sin utilizar caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="b1bbf-175">Esta característica permite copiar contenido de un documento XML y pegarlo directamente en un programa Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>

<span data-ttu-id="b1bbf-176">Las expresiones incrustadas del formulario `<%= exp %>` permiten agregar información dinámica a un literal de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="b1bbf-177">Para obtener más información, vea [expresiones incrustadas en XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b1bbf-177">For more information, see [Embedded Expressions in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>

<span data-ttu-id="b1bbf-178">El compilador Visual Basic convierte el literal de elemento XML en llamadas al <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor y, si es necesario, el <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="b1bbf-179">Espacios de nombres XML</span><span class="sxs-lookup"><span data-stu-id="b1bbf-179">XML Namespaces</span></span>

<span data-ttu-id="b1bbf-180">Los prefijos de espacios de nombres XML son útiles cuando es necesario crear literales XML con elementos del mismo espacio de nombres muchas veces en el código.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="b1bbf-181">Puede usar prefijos globales de espacio de nombres XML, que se definen mediante la `Imports` instrucción, o prefijos locales, que se definen mediante la `xmlns:xmlPrefix="xmlNamespace"` Sintaxis de atributo.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="b1bbf-182">Para obtener más información, vea [instrucción Imports (espacio de nombres XML)](../statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="b1bbf-182">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>

<span data-ttu-id="b1bbf-183">De acuerdo con las reglas de ámbito de los espacios de nombres XML, los prefijos locales tienen prioridad sobre los prefijos globales.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="b1bbf-184">Sin embargo, si un literal XML define un espacio de nombres XML, ese espacio de nombres no está disponible para las expresiones que aparecen en una expresión incrustada.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="b1bbf-185">La expresión incrustada solo puede tener acceso al espacio de nombres XML global.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-185">The embedded expression can access only the global XML namespace.</span></span>

<span data-ttu-id="b1bbf-186">El compilador Visual Basic convierte cada espacio de nombres XML global utilizado por un literal XML en una definición de espacio de nombres local en el código generado.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="b1bbf-187">Los espacios de nombres XML globales que no se utilizan no aparecen en el código generado.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>

## <a name="example"></a><span data-ttu-id="b1bbf-188">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1bbf-188">Example</span></span>

<span data-ttu-id="b1bbf-189">En el ejemplo siguiente se muestra cómo crear un elemento XML simple que tiene dos elementos vacíos anidados.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

<span data-ttu-id="b1bbf-190">En el ejemplo se muestra el texto siguiente.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-190">The example displays the following text.</span></span> <span data-ttu-id="b1bbf-191">Observe que el literal conserva la estructura de los elementos vacíos.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-191">Notice that the literal preserves the structure of the empty elements.</span></span>

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a><span data-ttu-id="b1bbf-192">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1bbf-192">Example</span></span>

<span data-ttu-id="b1bbf-193">En el ejemplo siguiente se muestra cómo utilizar expresiones incrustadas para asignar un nombre a un elemento y crear atributos.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

<span data-ttu-id="b1bbf-194">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="b1bbf-194">This code displays the following text:</span></span>

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a><span data-ttu-id="b1bbf-195">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1bbf-195">Example</span></span>

<span data-ttu-id="b1bbf-196">En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="b1bbf-197">A continuación, usa el prefijo del espacio de nombres para crear un literal XML y muestra el formulario final del elemento.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="b1bbf-198">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="b1bbf-198">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="b1bbf-199">Observe que el compilador ha convertido el prefijo del espacio de nombres XML global en una definición de prefijo para el espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="b1bbf-200">El \<ns:middle> elemento redefine el prefijo del espacio de nombres XML para el \<ns:inner1> elemento.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="b1bbf-201">Sin embargo, el \<ns:inner2> elemento utiliza el espacio de nombres definido por la `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b1bbf-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1bbf-202">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1bbf-202">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="b1bbf-203">Nombres de atributos y elementos XML declarados</span><span class="sxs-lookup"><span data-stu-id="b1bbf-203">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="b1bbf-204">Literal de comentario XML</span><span class="sxs-lookup"><span data-stu-id="b1bbf-204">XML Comment Literal</span></span>](xml-comment-literal.md)
- [<span data-ttu-id="b1bbf-205">Literal de CDATA XML</span><span class="sxs-lookup"><span data-stu-id="b1bbf-205">XML CDATA Literal</span></span>](xml-cdata-literal.md)
- [<span data-ttu-id="b1bbf-206">Literales XML</span><span class="sxs-lookup"><span data-stu-id="b1bbf-206">XML Literals</span></span>](index.md)
- [<span data-ttu-id="b1bbf-207">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1bbf-207">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="b1bbf-208">Expresiones insertadas en XML</span><span class="sxs-lookup"><span data-stu-id="b1bbf-208">Embedded Expressions in XML</span></span>](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="b1bbf-209">Imports (Instrucción, Espacio de nombres XML)</span><span class="sxs-lookup"><span data-stu-id="b1bbf-209">Imports Statement (XML Namespace)</span></span>](../statements/imports-statement-xml-namespace.md)

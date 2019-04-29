---
title: Literal de elemento XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: 7bd47d2461ba86dfbd1d5ff5993382914116f9ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61649782"
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="086c9-102">Literal de elemento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="086c9-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="086c9-103">Un valor literal que representa un <xref:System.Xml.Linq.XElement> objeto.</span><span class="sxs-lookup"><span data-stu-id="086c9-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="086c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="086c9-104">Syntax</span></span>  
  
```xml  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a><span data-ttu-id="086c9-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="086c9-105">Parts</span></span>  
  
-   `<`  
  
     <span data-ttu-id="086c9-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="086c9-106">Required.</span></span> <span data-ttu-id="086c9-107">Se abre la etiqueta inicial del elemento.</span><span class="sxs-lookup"><span data-stu-id="086c9-107">Opens the starting element tag.</span></span>  
  
-   `name`  
  
     <span data-ttu-id="086c9-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="086c9-108">Required.</span></span> <span data-ttu-id="086c9-109">Nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="086c9-109">Name of the element.</span></span> <span data-ttu-id="086c9-110">El formato es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="086c9-110">The format is one of the following:</span></span>  
  
    -   <span data-ttu-id="086c9-111">Texto literal para el nombre del elemento, el formato `[ePrefix:]eName`, donde:</span><span class="sxs-lookup"><span data-stu-id="086c9-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>  
  
        |<span data-ttu-id="086c9-112">Parte</span><span class="sxs-lookup"><span data-stu-id="086c9-112">Part</span></span>|<span data-ttu-id="086c9-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="086c9-113">Description</span></span>|  
        |---|---|  
        |`ePrefix`|<span data-ttu-id="086c9-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="086c9-114">Optional.</span></span> <span data-ttu-id="086c9-115">Prefijo de espacio de nombres XML para el elemento.</span><span class="sxs-lookup"><span data-stu-id="086c9-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="086c9-116">Debe ser un espacio de nombres XML global definido con un `Imports` instrucción en el archivo o en el nivel de proyecto, o un espacio de nombres XML que se define en este elemento o un elemento primario.</span><span class="sxs-lookup"><span data-stu-id="086c9-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`eName`|<span data-ttu-id="086c9-117">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="086c9-117">Required.</span></span> <span data-ttu-id="086c9-118">Nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="086c9-118">Name of the element.</span></span> <span data-ttu-id="086c9-119">El formato es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="086c9-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="086c9-120">-Texto literal.</span><span class="sxs-lookup"><span data-stu-id="086c9-120">-   Literal text.</span></span> <span data-ttu-id="086c9-121">Consulte [nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="086c9-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="086c9-122">-Incrustados de la expresión de formato `<%= eNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="086c9-122">-   Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="086c9-123">El tipo de `eNameExp` debe ser `String` o un tipo que es implícitamente convertible a <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="086c9-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
  
    -   <span data-ttu-id="086c9-124">La forma expresión incrustada `<%= nameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="086c9-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="086c9-125">El tipo de `nameExp` debe ser `String` o un tipo implícitamente convertible a <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="086c9-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="086c9-126">No se permite una expresión incrustada en una etiqueta de cierre de un elemento.</span><span class="sxs-lookup"><span data-stu-id="086c9-126">An embedded expression is not allowed in a closing tag of an element.</span></span>  
  
-   `attributeList`  
  
     <span data-ttu-id="086c9-127">Opcional.</span><span class="sxs-lookup"><span data-stu-id="086c9-127">Optional.</span></span> <span data-ttu-id="086c9-128">Lista de atributos declarados en el literal.</span><span class="sxs-lookup"><span data-stu-id="086c9-128">List of attributes declared in the literal.</span></span>  
  
     `attribute [ attribute ... ]`  
  
     <span data-ttu-id="086c9-129">Cada `attribute` tiene una de las siguientes sintaxis:</span><span class="sxs-lookup"><span data-stu-id="086c9-129">Each `attribute` has one of the following syntaxes:</span></span>  
  
    -   <span data-ttu-id="086c9-130">Asignación, el formato del atributo `[aPrefix:]aName=aValue`, donde:</span><span class="sxs-lookup"><span data-stu-id="086c9-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>  
  
        |<span data-ttu-id="086c9-131">Parte</span><span class="sxs-lookup"><span data-stu-id="086c9-131">Part</span></span>|<span data-ttu-id="086c9-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="086c9-132">Description</span></span>|  
        |---|---|  
        |`aPrefix`|<span data-ttu-id="086c9-133">Opcional.</span><span class="sxs-lookup"><span data-stu-id="086c9-133">Optional.</span></span> <span data-ttu-id="086c9-134">Prefijo de espacio de nombres XML para el atributo.</span><span class="sxs-lookup"><span data-stu-id="086c9-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="086c9-135">Debe ser un espacio de nombres XML global definido con un `Imports` instrucción o un espacio de nombres XML que se define en este elemento o un elemento primario.</span><span class="sxs-lookup"><span data-stu-id="086c9-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`aName`|<span data-ttu-id="086c9-136">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="086c9-136">Required.</span></span> <span data-ttu-id="086c9-137">Nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="086c9-137">Name of the attribute.</span></span> <span data-ttu-id="086c9-138">El formato es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="086c9-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="086c9-139">-Texto literal.</span><span class="sxs-lookup"><span data-stu-id="086c9-139">-   Literal text.</span></span> <span data-ttu-id="086c9-140">Consulte [nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="086c9-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="086c9-141">-Incrustados de la expresión de formato `<%= aNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="086c9-141">-   Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="086c9-142">El tipo de `aNameExp` debe ser `String` o un tipo que es implícitamente convertible a <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="086c9-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
        |`aValue`|<span data-ttu-id="086c9-143">Opcional.</span><span class="sxs-lookup"><span data-stu-id="086c9-143">Optional.</span></span> <span data-ttu-id="086c9-144">Valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="086c9-144">Value of the attribute.</span></span> <span data-ttu-id="086c9-145">El formato es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="086c9-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="086c9-146">-Texto literal, entrecomillada comillas.</span><span class="sxs-lookup"><span data-stu-id="086c9-146">-   Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="086c9-147">-Incrustados de la expresión de formato `<%= aValueExp %>`.</span><span class="sxs-lookup"><span data-stu-id="086c9-147">-   Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="086c9-148">Se permite cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="086c9-148">Any type is allowed.</span></span>|  
  
    -   <span data-ttu-id="086c9-149">La forma expresión incrustada `<%= aExp %>`.</span><span class="sxs-lookup"><span data-stu-id="086c9-149">Embedded expression of the form `<%= aExp %>`.</span></span>  
  
-   `/>`  
  
     <span data-ttu-id="086c9-150">Opcional.</span><span class="sxs-lookup"><span data-stu-id="086c9-150">Optional.</span></span> <span data-ttu-id="086c9-151">Indica que el elemento es un elemento vacío sin contenido.</span><span class="sxs-lookup"><span data-stu-id="086c9-151">Indicates that the element is an empty element, without content.</span></span>  
  
-   `>`  
  
     <span data-ttu-id="086c9-152">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="086c9-152">Required.</span></span> <span data-ttu-id="086c9-153">Finaliza la etiqueta del elemento inicial o vacío.</span><span class="sxs-lookup"><span data-stu-id="086c9-153">Ends the beginning or empty element tag.</span></span>  
  
-   `elementContents`  
  
     <span data-ttu-id="086c9-154">Opcional.</span><span class="sxs-lookup"><span data-stu-id="086c9-154">Optional.</span></span> <span data-ttu-id="086c9-155">Contenido del elemento.</span><span class="sxs-lookup"><span data-stu-id="086c9-155">Content of the element.</span></span>  
  
     `content [ content ... ]`  
  
     <span data-ttu-id="086c9-156">Cada `content` puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="086c9-156">Each `content` can be one of the following:</span></span>  
  
    -   <span data-ttu-id="086c9-157">Texto literal.</span><span class="sxs-lookup"><span data-stu-id="086c9-157">Literal text.</span></span> <span data-ttu-id="086c9-158">Todos los espacios en blanco `elementContents` pasa a ser significativa si no hay ningún texto literal.</span><span class="sxs-lookup"><span data-stu-id="086c9-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>  
  
    -   <span data-ttu-id="086c9-159">La forma expresión incrustada `<%= contentExp %>`.</span><span class="sxs-lookup"><span data-stu-id="086c9-159">Embedded expression of the form `<%= contentExp %>`.</span></span>  
  
    -   <span data-ttu-id="086c9-160">Literal de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="086c9-160">XML element literal.</span></span>  
  
    -   <span data-ttu-id="086c9-161">Literal de comentario XML.</span><span class="sxs-lookup"><span data-stu-id="086c9-161">XML comment literal.</span></span> <span data-ttu-id="086c9-162">Consulte [Literal de comentario XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="086c9-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>  
  
    -   <span data-ttu-id="086c9-163">Literal de instrucción de procesamiento de XML.</span><span class="sxs-lookup"><span data-stu-id="086c9-163">XML processing instruction literal.</span></span> <span data-ttu-id="086c9-164">Consulte [Literal de instrucción de procesamiento XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="086c9-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>  
  
    -   <span data-ttu-id="086c9-165">XML CDATA literal.</span><span class="sxs-lookup"><span data-stu-id="086c9-165">XML CDATA literal.</span></span> <span data-ttu-id="086c9-166">Consulte [Literal de CDATA XML](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span><span class="sxs-lookup"><span data-stu-id="086c9-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>  
  
-   `</[name]>`  
  
     <span data-ttu-id="086c9-167">Opcional.</span><span class="sxs-lookup"><span data-stu-id="086c9-167">Optional.</span></span> <span data-ttu-id="086c9-168">Representa la etiqueta de cierre para el elemento.</span><span class="sxs-lookup"><span data-stu-id="086c9-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="086c9-169">El elemento opcional `name` parámetro no se permite cuando es el resultado de una expresión incrustada.</span><span class="sxs-lookup"><span data-stu-id="086c9-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="086c9-170">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="086c9-170">Return Value</span></span>  
 <span data-ttu-id="086c9-171">Un objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="086c9-171">An <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="086c9-172">Comentarios</span><span class="sxs-lookup"><span data-stu-id="086c9-172">Remarks</span></span>  
 <span data-ttu-id="086c9-173">Puede usar la sintaxis de literales de elemento XML para crear <xref:System.Xml.Linq.XElement> objetos en el código.</span><span class="sxs-lookup"><span data-stu-id="086c9-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="086c9-174">Un literal XML puede abarcar varias líneas sin usar caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="086c9-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="086c9-175">Esta característica le permite copiar el contenido de un documento XML y péguelo directamente en un programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="086c9-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="086c9-176">Expresiones del formulario incrustadas `<%= exp %>` permiten agregar información dinámica a un literal de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="086c9-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="086c9-177">Para obtener más información, consulte [expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="086c9-177">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="086c9-178">El compilador de Visual Basic convierte el literal de elemento XML en llamadas a la <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor y, si es necesario, el <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="086c9-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="086c9-179">Espacios de nombres XML</span><span class="sxs-lookup"><span data-stu-id="086c9-179">XML Namespaces</span></span>  
 <span data-ttu-id="086c9-180">Los prefijos de espacio de nombres XML son útiles cuando tiene que crear literales XML con los elementos del mismo espacio de nombres muchas veces en el código.</span><span class="sxs-lookup"><span data-stu-id="086c9-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="086c9-181">Puede usar globales prefijos de espacio de nombres XML, que se definen mediante el uso de la `Imports` instrucción o prefijos locales, que se definen mediante el uso de la `xmlns:xmlPrefix="xmlNamespace"` sintaxis de atributo.</span><span class="sxs-lookup"><span data-stu-id="086c9-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="086c9-182">Para obtener más información, consulte [instrucción Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="086c9-182">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
 <span data-ttu-id="086c9-183">Según las reglas de ámbito para los espacios de nombres XML, los prefijos locales tienen prioridad sobre los prefijos globales.</span><span class="sxs-lookup"><span data-stu-id="086c9-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="086c9-184">Sin embargo, si un literal XML define un espacio de nombres XML, ese espacio de nombres no está disponible para las expresiones que aparecen en una expresión incrustada.</span><span class="sxs-lookup"><span data-stu-id="086c9-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="086c9-185">La expresión insertada puede tener acceso a solo el espacio de nombres XML global.</span><span class="sxs-lookup"><span data-stu-id="086c9-185">The embedded expression can access only the global XML namespace.</span></span>  
  
 <span data-ttu-id="086c9-186">El compilador de Visual Basic convierte cada espacio de nombres XML global que se usa un literal XML en una definición de un espacio de nombres local en el código generado.</span><span class="sxs-lookup"><span data-stu-id="086c9-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="086c9-187">Los espacios de nombres XML globales que no se utilizan no aparecen en el código generado.</span><span class="sxs-lookup"><span data-stu-id="086c9-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="086c9-188">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="086c9-188">Example</span></span>  
 <span data-ttu-id="086c9-189">El ejemplo siguiente muestra cómo crear un elemento XML simple que tiene dos elementos vacíos anidados.</span><span class="sxs-lookup"><span data-stu-id="086c9-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>  
  
 [!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]  
  
 <span data-ttu-id="086c9-190">En el ejemplo se muestra el texto siguiente.</span><span class="sxs-lookup"><span data-stu-id="086c9-190">The example displays the following text.</span></span> <span data-ttu-id="086c9-191">Tenga en cuenta que el literal conserva la estructura de los elementos vacíos.</span><span class="sxs-lookup"><span data-stu-id="086c9-191">Notice that the literal preserves the structure of the empty elements.</span></span>  
  
```xml  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a><span data-ttu-id="086c9-192">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="086c9-192">Example</span></span>  
 <span data-ttu-id="086c9-193">El ejemplo siguiente muestra cómo utilizar expresiones incrustadas para nombrar un elemento y crear atributos.</span><span class="sxs-lookup"><span data-stu-id="086c9-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>  
  
 [!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]  
  
 <span data-ttu-id="086c9-194">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="086c9-194">This code displays the following text:</span></span>  
  
```xml  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a><span data-ttu-id="086c9-195">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="086c9-195">Example</span></span>  
 <span data-ttu-id="086c9-196">En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="086c9-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="086c9-197">A continuación, se usa el prefijo del espacio de nombres para crear un literal XML y se muestra la forma final del elemento.</span><span class="sxs-lookup"><span data-stu-id="086c9-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>  
  
 [!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]  
  
 <span data-ttu-id="086c9-198">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="086c9-198">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="086c9-199">Tenga en cuenta que el compilador convirtió el prefijo del espacio de nombres XML global en una definición de prefijo del espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="086c9-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="086c9-200">El \<ns:middle > elemento redefine el prefijo del espacio de nombres XML para el \<ns:inner1 > elemento.</span><span class="sxs-lookup"><span data-stu-id="086c9-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="086c9-201">Sin embargo, el \<ns:inner2 > elemento utiliza el espacio de nombres definido por el `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="086c9-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="086c9-202">Vea también</span><span class="sxs-lookup"><span data-stu-id="086c9-202">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="086c9-203">Nombres de atributos y elementos XML declarados</span><span class="sxs-lookup"><span data-stu-id="086c9-203">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="086c9-204">Literal de comentario XML</span><span class="sxs-lookup"><span data-stu-id="086c9-204">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="086c9-205">Literal de CDATA XML</span><span class="sxs-lookup"><span data-stu-id="086c9-205">XML CDATA Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)
- [<span data-ttu-id="086c9-206">Literales XML</span><span class="sxs-lookup"><span data-stu-id="086c9-206">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="086c9-207">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="086c9-207">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="086c9-208">Expresiones incrustadas en XML</span><span class="sxs-lookup"><span data-stu-id="086c9-208">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="086c9-209">Imports (instrucción), espacio de nombres XML</span><span class="sxs-lookup"><span data-stu-id="086c9-209">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)

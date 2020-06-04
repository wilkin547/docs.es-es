---
title: 'Instrucción Imports: espacio de nombres XML'
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: a3184d68b0e4cdff5d4296a5a638e22b4e83bcde
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404542"
---
# <a name="imports-statement-xml-namespace"></a><span data-ttu-id="855d3-102">Imports (Instrucción, Espacio de nombres XML)</span><span class="sxs-lookup"><span data-stu-id="855d3-102">Imports Statement (XML Namespace)</span></span>

<span data-ttu-id="855d3-103">Importa prefijos de espacios de nombres XML para su uso en literales XML y propiedades de eje XML.</span><span class="sxs-lookup"><span data-stu-id="855d3-103">Imports XML namespace prefixes for use in XML literals and XML axis properties.</span></span>

## <a name="syntax"></a><span data-ttu-id="855d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="855d3-104">Syntax</span></span>

```vb
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">
```

## <a name="parts"></a><span data-ttu-id="855d3-105">Partes</span><span class="sxs-lookup"><span data-stu-id="855d3-105">Parts</span></span>

`xmlNamespacePrefix`  
<span data-ttu-id="855d3-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="855d3-106">Optional.</span></span> <span data-ttu-id="855d3-107">Cadena por la que pueden hacer referencia los elementos y atributos XML `xmlNamespaceName` .</span><span class="sxs-lookup"><span data-stu-id="855d3-107">The string by which XML elements and attributes can refer to `xmlNamespaceName`.</span></span> <span data-ttu-id="855d3-108">Si no `xmlNamespacePrefix` se proporciona ningún valor, el espacio de nombres XML importado es el espacio de nombres XML predeterminado.</span><span class="sxs-lookup"><span data-stu-id="855d3-108">If no `xmlNamespacePrefix` is supplied, the imported XML namespace is the default XML namespace.</span></span> <span data-ttu-id="855d3-109">Debe ser un identificador XML válido.</span><span class="sxs-lookup"><span data-stu-id="855d3-109">Must be a valid XML identifier.</span></span> <span data-ttu-id="855d3-110">Para obtener más información, vea [nombres de elementos y atributos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="855d3-110">For more information, see [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>

`xmlNamespaceName`  
<span data-ttu-id="855d3-111">Necesario.</span><span class="sxs-lookup"><span data-stu-id="855d3-111">Required.</span></span> <span data-ttu-id="855d3-112">Cadena que identifica el espacio de nombres XML que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="855d3-112">The string identifying the XML namespace being imported.</span></span>

## <a name="remarks"></a><span data-ttu-id="855d3-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="855d3-113">Remarks</span></span>

<span data-ttu-id="855d3-114">Puede utilizar la `Imports` instrucción para definir espacios de nombres XML globales que puede usar con literales XML y propiedades de eje XML, o como parámetros pasados al `GetXmlNamespace` operador.</span><span class="sxs-lookup"><span data-stu-id="855d3-114">You can use the `Imports` statement to define global XML namespaces that you can use with XML literals and XML axis properties, or as parameters passed to the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="855d3-115">(Para obtener información sobre el uso de la `Imports` instrucción para importar un alias que se puede usar donde se usan los nombres de tipo en el código, vea [instrucción Imports (espacio de nombres y tipo de .net)](imports-statement-net-namespace-and-type.md)). La sintaxis para declarar un espacio de nombres XML mediante la `Imports` instrucción es idéntica a la sintaxis utilizada en XML.</span><span class="sxs-lookup"><span data-stu-id="855d3-115">(For information about using the `Imports` statement to import an alias that can be used where type names are used in your code, see [Imports Statement (.NET Namespace and Type)](imports-statement-net-namespace-and-type.md).) The syntax for declaring an XML namespace by using the `Imports` statement is identical to the syntax used in XML.</span></span> <span data-ttu-id="855d3-116">Por lo tanto, puede copiar una declaración de espacio de nombres de un archivo XML y utilizarla en una `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="855d3-116">Therefore, you can copy a namespace declaration from an XML file and use it in an `Imports` statement.</span></span>

<span data-ttu-id="855d3-117">Los prefijos de espacios de nombres XML son útiles cuando se desea crear repetidamente elementos XML que son del mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="855d3-117">XML namespace prefixes are useful when you want to repeatedly create XML elements that are from the same namespace.</span></span> <span data-ttu-id="855d3-118">El prefijo de espacio de nombres XML declarado con la `Imports` instrucción es global en el sentido de que está disponible para todo el código del archivo.</span><span class="sxs-lookup"><span data-stu-id="855d3-118">The XML namespace prefix declared with the `Imports` statement is global in the sense that it is available to all code in the file.</span></span> <span data-ttu-id="855d3-119">Se puede utilizar al crear literales de elemento XML y al tener acceso a las propiedades del eje XML.</span><span class="sxs-lookup"><span data-stu-id="855d3-119">You can use it when you create XML element literals and when you access XML axis properties.</span></span> <span data-ttu-id="855d3-120">Para obtener más información, vea [XML ELEMENT literal](../xml-literals/xml-element-literal.md) and [XML AXIS Properties](../xml-axis/index.md).</span><span class="sxs-lookup"><span data-stu-id="855d3-120">For more information, see [XML Element Literal](../xml-literals/xml-element-literal.md) and [XML Axis Properties](../xml-axis/index.md).</span></span>

<span data-ttu-id="855d3-121">Si define un espacio de nombres XML global sin un prefijo de espacio de nombres (por ejemplo, `Imports <xmlns="http://SomeNameSpace>"` ), ese espacio de nombres se considera el espacio de nombres XML predeterminado.</span><span class="sxs-lookup"><span data-stu-id="855d3-121">If you define a global XML namespace without a namespace prefix (for example, `Imports <xmlns="http://SomeNameSpace>"`), that namespace is considered the default XML namespace.</span></span> <span data-ttu-id="855d3-122">El espacio de nombres XML predeterminado se utiliza para los literales de elemento XML o las propiedades de eje de atributo XML que no especifican explícitamente un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="855d3-122">The default XML namespace is used for any XML element literals or XML attribute axis properties that do not explicitly specify a namespace.</span></span> <span data-ttu-id="855d3-123">También se utiliza el espacio de nombres predeterminado si el espacio de nombres especificado es el espacio de nombres vacío (es decir, `xmlns=""` ).</span><span class="sxs-lookup"><span data-stu-id="855d3-123">The default namespace is also used if the specified namespace is the empty namespace (that is, `xmlns=""`).</span></span> <span data-ttu-id="855d3-124">El espacio de nombres XML predeterminado no se aplica a los atributos XML en los literales XML ni a las propiedades del eje de atributo XML que no tienen un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="855d3-124">The default XML namespace does not apply to XML attributes in XML literals or to XML attribute axis properties that do not have a namespace.</span></span>

<span data-ttu-id="855d3-125">Los espacios de nombres XML que se definen en un literal XML, que se denominan *espacios de nombres XML locales*, tienen prioridad sobre los espacios de nombres XML definidos por la `Imports` instrucción como globales.</span><span class="sxs-lookup"><span data-stu-id="855d3-125">XML namespaces that are defined in an XML literal, which are called *local XML namespaces*, take precedence over XML namespaces that are defined by the `Imports` statement as global.</span></span> <span data-ttu-id="855d3-126">Los espacios de nombres XML definidos por la `Imports` instrucción tienen prioridad sobre los espacios de nombres XML importados para un proyecto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="855d3-126">XML namespaces that are defined by the `Imports` statement take precedence over XML namespaces imported for a Visual Basic project.</span></span> <span data-ttu-id="855d3-127">Si un literal XML define un espacio de nombres XML, ese espacio de nombres local no se aplica a las expresiones incrustadas.</span><span class="sxs-lookup"><span data-stu-id="855d3-127">If an XML literal defines an XML namespace, that local namespace does not apply to embedded expressions.</span></span>

<span data-ttu-id="855d3-128">Los espacios de nombres XML globales siguen las mismas reglas de ámbito y definición que .NET Framework espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="855d3-128">Global XML namespaces follow the same scoping and definition rules as .NET Framework namespaces.</span></span> <span data-ttu-id="855d3-129">Como resultado, puede incluir una `Imports` instrucción para definir un espacio de nombres XML global en cualquier lugar en el que pueda importar un espacio de nombres de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="855d3-129">As a result, you can include an `Imports` statement to define a global XML namespace anywhere you can import a .NET Framework namespace.</span></span> <span data-ttu-id="855d3-130">Esto incluye los archivos de código y los espacios de nombres importados en el nivel de proyecto.</span><span class="sxs-lookup"><span data-stu-id="855d3-130">This includes both code files and project-level imported namespaces.</span></span> <span data-ttu-id="855d3-131">Para obtener información sobre los espacios de nombres importados en el nivel de proyecto, vea [Página referencias, diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="855d3-131">For information about project-level imported namespaces, see [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>

<span data-ttu-id="855d3-132">Cada archivo de código fuente puede contener cualquier número de `Imports` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="855d3-132">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="855d3-133">Estos deben seguir las declaraciones de opciones, como la `Option Strict` instrucción, y deben preceder a las declaraciones de elementos de programación, como las `Module` `Class` instrucciones o.</span><span class="sxs-lookup"><span data-stu-id="855d3-133">These must follow option declarations, such as the `Option Strict` statement, and they must precede programming element declarations, such as `Module` or `Class` statements.</span></span>

## <a name="example"></a><span data-ttu-id="855d3-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="855d3-134">Example</span></span>

<span data-ttu-id="855d3-135">En el ejemplo siguiente se importa un espacio de nombres XML predeterminado y un espacio de nombres XML identificado con el prefijo `ns` .</span><span class="sxs-lookup"><span data-stu-id="855d3-135">The following example imports a default XML namespace and an XML namespace identified with the prefix `ns`.</span></span> <span data-ttu-id="855d3-136">A continuación, crea literales XML que usan ambos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="855d3-136">It then creates XML literals that use both namespaces.</span></span>

[!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]

<span data-ttu-id="855d3-137">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="855d3-137">This code displays the following text:</span></span>

```xml
<ns:outer xmlns="http://DefaultNamespace"
          xmlns:ns="http://NewNamespace">
  <ns:innerElement></ns:innerElement>
  <siblingElement></siblingElement>
  <innerElement />
</ns:outer>
```

## <a name="example"></a><span data-ttu-id="855d3-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="855d3-138">Example</span></span>

<span data-ttu-id="855d3-139">En el ejemplo siguiente se importa el prefijo del espacio de nombres XML `ns` .</span><span class="sxs-lookup"><span data-stu-id="855d3-139">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="855d3-140">A continuación, crea un literal XML que utiliza el prefijo de espacio de nombres y muestra el formulario final del elemento.</span><span class="sxs-lookup"><span data-stu-id="855d3-140">It then creates an XML literal that uses the namespace prefix and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="855d3-141">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="855d3-141">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="855d3-142">Observe que el compilador ha convertido el prefijo de espacio de nombres XML de un prefijo global a una definición de prefijo local.</span><span class="sxs-lookup"><span data-stu-id="855d3-142">Notice that the compiler converted the XML namespace prefix from a global prefix to a local prefix definition.</span></span>

## <a name="example"></a><span data-ttu-id="855d3-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="855d3-143">Example</span></span>

<span data-ttu-id="855d3-144">En el ejemplo siguiente se importa el prefijo del espacio de nombres XML `ns` .</span><span class="sxs-lookup"><span data-stu-id="855d3-144">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="855d3-145">A continuación, se usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario con el nombre completo `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="855d3-145">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>

[!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]

<span data-ttu-id="855d3-146">Este código muestra el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="855d3-146">This code displays the following text:</span></span>

`Patrick Hines`

## <a name="see-also"></a><span data-ttu-id="855d3-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="855d3-147">See also</span></span>

- [<span data-ttu-id="855d3-148">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="855d3-148">XML Element Literal</span></span>](../xml-literals/xml-element-literal.md)
- [<span data-ttu-id="855d3-149">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="855d3-149">XML Axis Properties</span></span>](../xml-axis/index.md)
- [<span data-ttu-id="855d3-150">Nombres de atributos y elementos XML declarados</span><span class="sxs-lookup"><span data-stu-id="855d3-150">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="855d3-151">Operador GetXmlNamespace</span><span class="sxs-lookup"><span data-stu-id="855d3-151">GetXmlNamespace Operator</span></span>](../operators/getxmlnamespace-operator.md)

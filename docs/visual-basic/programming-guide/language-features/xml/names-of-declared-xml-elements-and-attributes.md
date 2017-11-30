---
title: Nombres de atributos y elementos XML declarados (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 846a028e076873d1978f751fdb70e93c7c6a81af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="0f881-102">Nombres de atributos y elementos XML declarados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f881-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>
<span data-ttu-id="0f881-103">Este tema se proporcionan [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] directrices para asignar nombres a atributos en los literales XML y elementos XML.</span><span class="sxs-lookup"><span data-stu-id="0f881-103">This topic provides [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="0f881-104">En un literal XML, puede especificar un nombre local o un nombre completo.</span><span class="sxs-lookup"><span data-stu-id="0f881-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="0f881-105">Un nombre calificado se compone de un prefijo de espacio de nombres XML, un signo de dos puntos y un nombre local.</span><span class="sxs-lookup"><span data-stu-id="0f881-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="0f881-106">Para obtener más información acerca de los prefijos de espacio de nombres XML, vea [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="0f881-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="0f881-107">Reglas</span><span class="sxs-lookup"><span data-stu-id="0f881-107">Rules</span></span>  
 <span data-ttu-id="0f881-108">Un nombre local de un elemento o atributo en [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] debe cumplir las reglas siguientes.</span><span class="sxs-lookup"><span data-stu-id="0f881-108">A local name of an element or attribute in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must adhere to the following rules.</span></span>  
  
-   <span data-ttu-id="0f881-109">Puede comenzar con un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0f881-109">It can begin with a namespace.</span></span> <span data-ttu-id="0f881-110">Debe comenzar con un carácter alfabético o un carácter de subrayado (`_`).</span><span class="sxs-lookup"><span data-stu-id="0f881-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="0f881-111">Debe contener únicamente caracteres alfabéticos, dígitos decimales, caracteres de subrayado, puntos (.) y guiones (-).</span><span class="sxs-lookup"><span data-stu-id="0f881-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
-   <span data-ttu-id="0f881-112">No debe ser más de 1024 caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f881-112">It must not be more than 1,024 characters long.</span></span>  
  
-   <span data-ttu-id="0f881-113">Dos puntos que aparecen en los nombres indican la demarcación de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0f881-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="0f881-114">Por lo tanto, puede usar caracteres de dos puntos solo para especificar un espacio de nombres XML para un nombre determinado.</span><span class="sxs-lookup"><span data-stu-id="0f881-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="0f881-115">Además, debe respetar la siguiente directriz.</span><span class="sxs-lookup"><span data-stu-id="0f881-115">In addition, you should adhere to the following guideline.</span></span>  
  
-   <span data-ttu-id="0f881-116">La especificación XML 1.0 reserva todos los nombres que comienzan con la cadena "xml", de cualquier variación de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0f881-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="0f881-117">Por lo tanto, no use esos nombres para el elemento y nombres de atributo.</span><span class="sxs-lookup"><span data-stu-id="0f881-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="0f881-118">Instrucciones de longitud de nombre</span><span class="sxs-lookup"><span data-stu-id="0f881-118">Name Length Guidelines</span></span>  
 <span data-ttu-id="0f881-119">A efectos prácticos, un nombre debe ser lo más corto posible aunque tienen que identificar claramente la naturaleza del elemento.</span><span class="sxs-lookup"><span data-stu-id="0f881-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="0f881-120">Esto mejora la legibilidad del código y reduce el tamaño de archivo de origen y de longitud de línea.</span><span class="sxs-lookup"><span data-stu-id="0f881-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="0f881-121">Sin embargo, su nombre no debe ser tan corto que no adecuadamente describe el elemento o cómo lo usa el código.</span><span class="sxs-lookup"><span data-stu-id="0f881-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="0f881-122">Esto es importante para la legibilidad del código.</span><span class="sxs-lookup"><span data-stu-id="0f881-122">This is important for the readability of your code.</span></span> <span data-ttu-id="0f881-123">Si alguien está intentando lo entiende, o si usted está examinando mucho tiempo después de que lo ha escrito, nombres de elemento adecuados pueden ahorrar tiempo.</span><span class="sxs-lookup"><span data-stu-id="0f881-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="0f881-124">Mayúsculas y minúsculas en nombres</span><span class="sxs-lookup"><span data-stu-id="0f881-124">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="0f881-125">Los nombres de elemento XML distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0f881-125">XML element names are case sensitive.</span></span> <span data-ttu-id="0f881-126">Esto significa que, cuando el [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador compara dos nombres que difieran en mayúsculas o minúsculas, los interpreta como nombres distintos.</span><span class="sxs-lookup"><span data-stu-id="0f881-126">This means that when the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="0f881-127">Por ejemplo, interpreta `ABC` y `abc` como referencia para separar los elementos.</span><span class="sxs-lookup"><span data-stu-id="0f881-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="0f881-128">Espacios de nombres XML</span><span class="sxs-lookup"><span data-stu-id="0f881-128">XML Namespaces</span></span>  
 <span data-ttu-id="0f881-129">Al crear un elemento XML literal, puede especificar el prefijo de espacio de nombres XML para el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="0f881-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="0f881-130">Para obtener más información, consulte [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="0f881-130">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f881-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f881-131">See Also</span></span>  
 [<span data-ttu-id="0f881-132">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f881-132">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="0f881-133">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="0f881-133">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)

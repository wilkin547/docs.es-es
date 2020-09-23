---
title: Nombres de atributos y elementos XML declarados
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: 2142674c3de4c5ac9e806c1328daa3efb697beb9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085625"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="40da7-102">Nombres de atributos y elementos XML declarados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40da7-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>

<span data-ttu-id="40da7-103">En este tema se proporcionan instrucciones Visual Basic para asignar nombres a los elementos y atributos XML en los literales XML.</span><span class="sxs-lookup"><span data-stu-id="40da7-103">This topic provides Visual Basic guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="40da7-104">En un literal XML, puede especificar un nombre local o un nombre completo.</span><span class="sxs-lookup"><span data-stu-id="40da7-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="40da7-105">Un nombre completo consta de un prefijo de espacio de nombres XML, dos puntos y un nombre local.</span><span class="sxs-lookup"><span data-stu-id="40da7-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="40da7-106">Para obtener más información sobre los prefijos de espacios de nombres XML, vea [literal de elemento XML](../../../language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="40da7-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="40da7-107">Reglas</span><span class="sxs-lookup"><span data-stu-id="40da7-107">Rules</span></span>  

 <span data-ttu-id="40da7-108">Un nombre local de un elemento o atributo de Visual Basic debe cumplir las siguientes reglas.</span><span class="sxs-lookup"><span data-stu-id="40da7-108">A local name of an element or attribute in Visual Basic must adhere to the following rules.</span></span>  
  
- <span data-ttu-id="40da7-109">Puede comenzar con un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="40da7-109">It can begin with a namespace.</span></span> <span data-ttu-id="40da7-110">Debe empezar por un carácter alfabético o un carácter de subrayado ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="40da7-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="40da7-111">Debe contener solo caracteres alfabéticos, dígitos decimales, caracteres de subrayado, puntos (.) y guiones (-).</span><span class="sxs-lookup"><span data-stu-id="40da7-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
- <span data-ttu-id="40da7-112">No debe tener más de 1.024 caracteres de longitud.</span><span class="sxs-lookup"><span data-stu-id="40da7-112">It must not be more than 1,024 characters long.</span></span>  
  
- <span data-ttu-id="40da7-113">Los dos puntos que aparecen en los nombres indican la demarcación del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="40da7-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="40da7-114">Por lo tanto, solo puede usar dos puntos para especificar un espacio de nombres XML para un nombre determinado.</span><span class="sxs-lookup"><span data-stu-id="40da7-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="40da7-115">Además, debe cumplir la siguiente directriz.</span><span class="sxs-lookup"><span data-stu-id="40da7-115">In addition, you should adhere to the following guideline.</span></span>  
  
- <span data-ttu-id="40da7-116">La especificación XML 1,0 reserva todos los nombres que comienzan con la cadena "XML", de cualquier variación de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="40da7-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="40da7-117">Por lo tanto, no use esos nombres para los nombres de elementos y atributos.</span><span class="sxs-lookup"><span data-stu-id="40da7-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="40da7-118">Instrucciones de longitud de nombre</span><span class="sxs-lookup"><span data-stu-id="40da7-118">Name Length Guidelines</span></span>  

 <span data-ttu-id="40da7-119">Como cuestión práctica, un nombre debe ser lo más corto posible y, al mismo tiempo, identificar claramente la naturaleza del elemento.</span><span class="sxs-lookup"><span data-stu-id="40da7-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="40da7-120">Esto mejora la legibilidad del código y reduce la longitud de línea y el tamaño del archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="40da7-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="40da7-121">Sin embargo, el nombre no debe ser tan corto que no describe adecuadamente el elemento o cómo lo usa el código.</span><span class="sxs-lookup"><span data-stu-id="40da7-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="40da7-122">Esto es importante para la legibilidad del código.</span><span class="sxs-lookup"><span data-stu-id="40da7-122">This is important for the readability of your code.</span></span> <span data-ttu-id="40da7-123">Si alguien más está intentando comprenderlo, o si usted lo consulta mucho tiempo después de escribirlo, los nombres de elemento adecuados pueden ahorrar tiempo.</span><span class="sxs-lookup"><span data-stu-id="40da7-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="40da7-124">Distinción de mayúsculas y minúsculas en nombres</span><span class="sxs-lookup"><span data-stu-id="40da7-124">Case Sensitivity in Names</span></span>  

 <span data-ttu-id="40da7-125">Los nombres de elementos XML distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="40da7-125">XML element names are case sensitive.</span></span> <span data-ttu-id="40da7-126">Esto significa que cuando el compilador de Visual Basic compara dos nombres que solo se diferencian en el uso alfabético de mayúsculas y minúsculas, los interpreta como nombres diferentes.</span><span class="sxs-lookup"><span data-stu-id="40da7-126">This means that when the Visual Basic compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="40da7-127">Por ejemplo, interpreta `ABC` y `abc` como referencia a elementos independientes.</span><span class="sxs-lookup"><span data-stu-id="40da7-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="40da7-128">Espacios de nombres XML</span><span class="sxs-lookup"><span data-stu-id="40da7-128">XML Namespaces</span></span>  

 <span data-ttu-id="40da7-129">Al crear un literal de elemento XML, puede especificar el prefijo del espacio de nombres XML para el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="40da7-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="40da7-130">Para obtener más información, vea [literal de elemento XML](../../../language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="40da7-130">For more information, see [XML Element Literal](../../../language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40da7-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="40da7-131">See also</span></span>

- [<span data-ttu-id="40da7-132">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="40da7-132">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="40da7-133">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="40da7-133">XML Element Literal</span></span>](../../../language-reference/xml-literals/xml-element-literal.md)

---
title: Entidades de caracteres XML y XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- '&'
- '&amp'
- '&gt'
- '&lt'
helpviewer_keywords:
- XAML [XAML Services], special characters
- ampersand (&) [XAML Services]
- special characters [XAML Services]
- apostrophe (') [XAML Services]
- greater-than (>) character [XAML Services]
- XAML [XAML Services], quotation mark (")
- XAML [XAML Services], apostrophe (')
- '& (ampersand) [XAML Services]'
- XAML [XAML Services], & (ampersand)
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- less-than (<) character [XAML Services]
ms.assetid: 6896d0ce-74f7-420a-9ab4-de9bbf390e8d
caps.latest.revision: "23"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b325c931579606f6d1d90eb821766a4110acfd5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xml-character-entities-and-xaml"></a><span data-ttu-id="1f7cb-102">Entidades de caracteres XML y XAML</span><span class="sxs-lookup"><span data-stu-id="1f7cb-102">XML Character Entities and XAML</span></span>
<span data-ttu-id="1f7cb-103">XAML usa entidades de caracteres definidas en XML para los caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-103">XAML uses character entities defined in XML for special characters.</span></span> <span data-ttu-id="1f7cb-104">En este tema se describen algunas entidades de caracteres específicas y consideraciones generales para otros conceptos XML en XAML.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-104">This topic describes some specific character entities and general considerations for other XML concepts in XAML.</span></span>  
  
<a name="character_entities_and_escaping_issues_that_are_unique_to_xaml"></a>   
## <a name="character-entities-and-escaping-issues-that-are-unique-to-xaml"></a><span data-ttu-id="1f7cb-105">Entidades de caracteres y problemas de escape exclusivos de XAML</span><span class="sxs-lookup"><span data-stu-id="1f7cb-105">Character Entities and Escaping Issues That Are Unique to XAML</span></span>  
 <span data-ttu-id="1f7cb-106">Normalmente, el marcado XAML usa las mismas entidades de caracteres y secuencias de escape que se definen en XML.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-106">XAML markup typically uses the same character entities and escape sequences that are defined in XML.</span></span>  
  
 <span data-ttu-id="1f7cb-107">La excepción principal es que las llaves ({ y }) son importantes en XAML porque estos caracteres informan al procesador XAML de que la secuencia de caracteres incluida entre ellas se debe interpretar como una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-107">The main exception is that braces ({ and }) have significance in XAML because these characters inform a XAML processor that a character sequence enclosed by braces must be interpreted as a markup extension.</span></span> <span data-ttu-id="1f7cb-108">Para más información sobre las extensiones de marcado, vea [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1f7cb-108">For more information about markup extensions, see [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span></span>  
  
 <span data-ttu-id="1f7cb-109">Sin embargo, puede mostrar las llaves como caracteres literales si usa una secuencia de escape específica de XAML y no de XML.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-109">However, you can still display the braces as literal characters by using an escape sequence that is particular to XAML instead of XML.</span></span> <span data-ttu-id="1f7cb-110">Para obtener más información, consulte [{} secuencia de Escape: extensión de marcado](escape-sequence-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="1f7cb-110">For more information, see [{} Escape Sequence - Markup Extension](escape-sequence-markup-extension.md).</span></span>  
  
 <span data-ttu-id="1f7cb-111">Tenga en cuenta que una barra diagonal inversa (\\) no requiere una secuencia de escape cuando se administra como una cadena.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-111">Note that a backslash (\\) does not require an escape sequence when it is handled as a string.</span></span>  
  
<a name="xml_character_entities"></a>   
## <a name="xml-character-entities"></a><span data-ttu-id="1f7cb-112">Entidades de caracteres XML</span><span class="sxs-lookup"><span data-stu-id="1f7cb-112">XML Character Entities</span></span>  
 <span data-ttu-id="1f7cb-113">Como se mencionó anteriormente, la mayoría de las entidades de caracteres y de las secuencias de escape que se suelen usar para escribir el marcado XAML se definen mediante XML.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-113">As mentioned previously, most character entities and escape sequences that are typically used to write XAML markup are defined by XML.</span></span> <span data-ttu-id="1f7cb-114">En este tema no se proporciona la lista completa de estas entidades; encontrará una referencia detallada de las mismas en la documentación externa, como las especificaciones de XML.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-114">This topic does not provide the complete list of these entities; a detailed reference for the entities can be found in external documentation, such as in XML specifications.</span></span> <span data-ttu-id="1f7cb-115">Sin embargo, para mayor comodidad, en este tema se incluye una lista con algunas de las entidades de caracteres XML específicas que se usan normalmente para el marcado XAML.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-115">However, for convenience, this topic lists some of the specific XML character entities that are typically used in XAML markup.</span></span>  
  
|<span data-ttu-id="1f7cb-116">Carácter</span><span class="sxs-lookup"><span data-stu-id="1f7cb-116">Character</span></span>|<span data-ttu-id="1f7cb-117">Entity</span><span class="sxs-lookup"><span data-stu-id="1f7cb-117">Entity</span></span>|<span data-ttu-id="1f7cb-118">Notas</span><span class="sxs-lookup"><span data-stu-id="1f7cb-118">Notes</span></span>|  
|---------------|------------|-----------|  
|<span data-ttu-id="1f7cb-119">& (símbolo de Y comercial)</span><span class="sxs-lookup"><span data-stu-id="1f7cb-119">& (ampersand)</span></span>|<span data-ttu-id="1f7cb-120">\&amp;</span><span class="sxs-lookup"><span data-stu-id="1f7cb-120">\&amp;</span></span>|<span data-ttu-id="1f7cb-121">Debe usarse tanto para los valores de atributo como para el contenido de un elemento.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-121">Must be used both for attribute values and for content of an element.</span></span>|  
|<span data-ttu-id="1f7cb-122">> (carácter mayor que)</span><span class="sxs-lookup"><span data-stu-id="1f7cb-122">> (greater-than character)</span></span>|<span data-ttu-id="1f7cb-123">\&gt;</span><span class="sxs-lookup"><span data-stu-id="1f7cb-123">\&gt;</span></span>|<span data-ttu-id="1f7cb-124">Debe usarse para un valor de atributo, pero > es aceptable como contenido de un elemento siempre que esté precedido de <.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-124">Must be used for an attribute value, but > is acceptable as the content of an element as long as < does not precede it.</span></span>|  
|<span data-ttu-id="1f7cb-125">< (carácter menos que)</span><span class="sxs-lookup"><span data-stu-id="1f7cb-125">< (less-than character)</span></span>|<span data-ttu-id="1f7cb-126">\&lt;</span><span class="sxs-lookup"><span data-stu-id="1f7cb-126">\&lt;</span></span>|<span data-ttu-id="1f7cb-127">Se debe usar para un valor de atributo, pero \< es aceptable como contenido de un elemento siempre que > no siga.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-127">Must be used for an attribute value, but \< is acceptable as the content of an element as long as > does not follow it.</span></span>|  
|<span data-ttu-id="1f7cb-128">" (comillas dobles rectas)</span><span class="sxs-lookup"><span data-stu-id="1f7cb-128">" (straight quotation mark)</span></span>|<span data-ttu-id="1f7cb-129">\&quot;</span><span class="sxs-lookup"><span data-stu-id="1f7cb-129">\&quot;</span></span>|<span data-ttu-id="1f7cb-130">Debe usarse para un valor de atributo, pero las comillas dobles rectas (") son aceptables como contenido de un elemento.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-130">Must be used for an attribute value, but a straight quotation mark (") is acceptable as the content of an element.</span></span> <span data-ttu-id="1f7cb-131">Tenga en cuenta que los valores de atributo se pueden incluir entre comillas simples rectas (') o entre comillas dobles rectas ("); el carácter que aparece primero define el carácter que cierra el valor del atributo, mientras que el otro tipo de comillas se puede usar como valor literal dentro del valor.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-131">Note that attribute values may be enclosed either by a single straight quotation mark (') or by a straight quotation mark ("); whichever character appears first defines the attribute value enclosure, and the alternative quote can then be used as a literal within the value.</span></span>|  
|<span data-ttu-id="1f7cb-132">' (comilla simple recta)</span><span class="sxs-lookup"><span data-stu-id="1f7cb-132">' (single straight quotation mark)</span></span>|<span data-ttu-id="1f7cb-133">\&apos;</span><span class="sxs-lookup"><span data-stu-id="1f7cb-133">\&apos;</span></span>|<span data-ttu-id="1f7cb-134">Debe usarse para un valor de atributo, pero una comilla simple recta (') es aceptable como contenido de un elemento.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-134">Must be used for an attribute value, but a single straight quotation mark (') is acceptable as the content of an element.</span></span> <span data-ttu-id="1f7cb-135">Tenga en cuenta que los valores de atributo se pueden incluir entre comillas simples rectas (') o entre comillas dobles rectas ("); el carácter que aparece primero define el carácter que cierra el valor del atributo, mientras que el otro tipo de comillas se puede usar como valor literal dentro del valor.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-135">Note that attribute values may be enclosed either by a single straight quotation mark (') or by a straight quotation mark ("); whichever character appears first defines the attribute value enclosure, and the alternative quote can then be used as a literal within the value.</span></span>|  
|<span data-ttu-id="1f7cb-136">(asignaciones de caracteres numéricos)</span><span class="sxs-lookup"><span data-stu-id="1f7cb-136">(numeric character mappings)</span></span>|<span data-ttu-id="1f7cb-137">&#*[entero]* ; o & #x*[hex]*;</span><span class="sxs-lookup"><span data-stu-id="1f7cb-137">&#*[integer]*; or &#x*[hex]*;</span></span>|<span data-ttu-id="1f7cb-138">XAML admite las asignaciones de caracteres numéricos en la codificación que está activa.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-138">XAML supports numeric character mappings into the encoding that is active.</span></span>|  
|<span data-ttu-id="1f7cb-139">(espacio de no separación)</span><span class="sxs-lookup"><span data-stu-id="1f7cb-139">(nonbreaking space)</span></span>|<span data-ttu-id="1f7cb-140">&\#160; (suponiendo la codificación UTF-8)</span><span class="sxs-lookup"><span data-stu-id="1f7cb-140">&\#160; (assuming UTF-8 encoding)</span></span>|<span data-ttu-id="1f7cb-141">Para los elementos de documentos dinámicos o los elementos que aceptan texto como <xref:System.Windows.Controls.TextBox> de WPF, los espacios de no separación no se normalizan fuera del marcado, ni siquiera en `xml:space="default"`.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-141">For flow document elements, or elements that take text such as the WPF <xref:System.Windows.Controls.TextBox>, nonbreaking spaces are not normalized out of the markup, even for `xml:space="default"`.</span></span> <span data-ttu-id="1f7cb-142">(Para obtener más información, consulte [procesamiento de espacios en blanco en XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).)</span><span class="sxs-lookup"><span data-stu-id="1f7cb-142">(For more information, see [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).)</span></span>|  
  
<a name="xml_comment_format"></a>   
## <a name="xml-comment-format"></a><span data-ttu-id="1f7cb-143">Formato de los comentarios XML</span><span class="sxs-lookup"><span data-stu-id="1f7cb-143">XML Comment Format</span></span>  
 <span data-ttu-id="1f7cb-144">XAML usa el formato de comentario XML: el inicio del comentario es `<!--`, el final del comentario es `-->,` y la secuencia `--` no debe aparecer en el comentario.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-144">XAML uses the XML comment format: the start of the comment is `<!--`, the end of comment is `-->,` and the sequence `--` must not occur within the comment.</span></span>  
  
<a name="xml_processing_instructions"></a>   
## <a name="xml-processing-instructions"></a><span data-ttu-id="1f7cb-145">Instrucciones de procesamiento de XML</span><span class="sxs-lookup"><span data-stu-id="1f7cb-145">XML Processing Instructions</span></span>  
 <span data-ttu-id="1f7cb-146">XAML controla las instrucciones de procesamiento de XML de acuerdo con las especificaciones de XML, que indican que las instrucciones deben pasarse.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-146">XAML handles XML processing instructions according to XML specifications, which state that the instructions must be passed through.</span></span> <span data-ttu-id="1f7cb-147">Procesamiento XAML en los servicios XAML de .NET Framework no utiliza las instrucciones de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="1f7cb-147">XAML processing in .NET Framework XAML Services  does not use any processing instructions.</span></span> <span data-ttu-id="1f7cb-148">Otros marcos existentes que usan XAML tampoco usan las instrucciones de procesamiento de XAML. </span><span class="sxs-lookup"><span data-stu-id="1f7cb-148">Other existing frameworks that use XAML also do not use processing instructions from XAML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f7cb-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f7cb-149">See Also</span></span>  
 [<span data-ttu-id="1f7cb-150">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="1f7cb-150">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="1f7cb-151">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="1f7cb-151">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="1f7cb-152">Gramática de XamlName</span><span class="sxs-lookup"><span data-stu-id="1f7cb-152">XamlName Grammar</span></span>](../../../docs/framework/xaml-services/xamlname-grammar.md)  
 [<span data-ttu-id="1f7cb-153">Procesamiento de espacios en blanco en XAML</span><span class="sxs-lookup"><span data-stu-id="1f7cb-153">Whitespace Processing in XAML</span></span>](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)

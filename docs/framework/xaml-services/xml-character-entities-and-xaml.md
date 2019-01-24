---
title: Entidades de caracteres XML y XAML
ms.date: 03/30/2017
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
ms.openlocfilehash: 03ce1645b859e9c3ebe470131ae2aee578cb366f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661365"
---
# <a name="xml-character-entities-and-xaml"></a>Entidades de caracteres XML y XAML
XAML usa entidades de caracteres definidas en XML para los caracteres especiales. En este tema se describen algunas entidades de caracteres específicas y consideraciones generales para otros conceptos XML en XAML.  
  
<a name="character_entities_and_escaping_issues_that_are_unique_to_xaml"></a>   
## <a name="character-entities-and-escaping-issues-that-are-unique-to-xaml"></a>Entidades de caracteres y problemas de escape exclusivos de XAML  
 Normalmente, el marcado XAML usa las mismas entidades de caracteres y secuencias de escape que se definen en XML.  
  
 La excepción principal es que las llaves ({ y }) son importantes en XAML porque estos caracteres informan al procesador XAML de que la secuencia de caracteres incluida entre ellas se debe interpretar como una extensión de marcado. Para más información sobre las extensiones de marcado, vea [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).  
  
 Sin embargo, puede mostrar las llaves como caracteres literales si usa una secuencia de escape específica de XAML y no de XML. Para obtener más información, consulte [ {} secuencia de Escape: extensión de marcado](escape-sequence-markup-extension.md).  
  
 Tenga en cuenta que una barra diagonal inversa (\\) no requiere una secuencia de escape cuando se administra como una cadena.  
  
<a name="xml_character_entities"></a>   
## <a name="xml-character-entities"></a>Entidades de caracteres XML  
 Como se mencionó anteriormente, la mayoría de las entidades de caracteres y de las secuencias de escape que se suelen usar para escribir el marcado XAML se definen mediante XML. En este tema no se proporciona la lista completa de estas entidades; encontrará una referencia detallada de las mismas en la documentación externa, como las especificaciones de XML. Sin embargo, para mayor comodidad, en este tema se incluye una lista con algunas de las entidades de caracteres XML específicas que se usan normalmente para el marcado XAML.  
  
|Carácter|Entity|Notas|  
|---------------|------------|-----------|  
|& (símbolo de Y comercial)|\&amp;|Debe usarse tanto para los valores de atributo como para el contenido de un elemento.|  
|> (carácter mayor que)|\&gt;|Debe usarse para un valor de atributo, pero > es aceptable como contenido de un elemento siempre que esté precedido de <.|  
|< (carácter menos que)|\&lt;|Se debe utilizar para un valor de atributo, pero \< es aceptable como contenido de un elemento siempre y cuando > no la cumple.|  
|" (comillas dobles rectas)|\&quot;|Debe usarse para un valor de atributo, pero las comillas dobles rectas (") son aceptables como contenido de un elemento. Tenga en cuenta que los valores de atributo se pueden incluir entre comillas simples rectas (') o entre comillas dobles rectas ("); el carácter que aparece primero define el carácter que cierra el valor del atributo, mientras que el otro tipo de comillas se puede usar como valor literal dentro del valor.|  
|' (comilla simple recta)|\&apos;|Debe usarse para un valor de atributo, pero una comilla simple recta (') es aceptable como contenido de un elemento. Tenga en cuenta que los valores de atributo se pueden incluir entre comillas simples rectas (') o entre comillas dobles rectas ("); el carácter que aparece primero define el carácter que cierra el valor del atributo, mientras que el otro tipo de comillas se puede usar como valor literal dentro del valor.|  
|(asignaciones de caracteres numéricos)|&#*[entero]*; o &#x *[hex]*;|XAML admite las asignaciones de caracteres numéricos en la codificación que está activa.|  
|(espacio de no separación)|&\#160; (suponiendo la codificación UTF-8)|Para los elementos de documentos dinámicos o los elementos que aceptan texto como <xref:System.Windows.Controls.TextBox> de WPF, los espacios de no separación no se normalizan fuera del marcado, ni siquiera en `xml:space="default"`. (Para obtener más información, consulte [espacio en blanco en XAML de procesamiento](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).)|  
  
<a name="xml_comment_format"></a>   
## <a name="xml-comment-format"></a>Formato de los comentarios XML  
 XAML usa el formato de comentario XML: el inicio del comentario es `<!--`, el final del comentario es `-->,` y la secuencia `--` no debe aparecer en el comentario.  
  
<a name="xml_processing_instructions"></a>   
## <a name="xml-processing-instructions"></a>Instrucciones de procesamiento de XML  
 XAML controla las instrucciones de procesamiento de XML de acuerdo con las especificaciones de XML, que indican que las instrucciones deben pasarse. XAML de procesamiento en los servicios XAML de .NET Framework no utiliza las instrucciones de procesamiento. Otros marcos existentes que usan XAML tampoco usan las instrucciones de procesamiento de XAML.   
  
## <a name="see-also"></a>Vea también
- [Información general sobre XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [Extensiones de marcado y XAML de WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [Gramática de XamlName](../../../docs/framework/xaml-services/xamlname-grammar.md)
- [Espacio en blanco en XAML de procesamiento](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)

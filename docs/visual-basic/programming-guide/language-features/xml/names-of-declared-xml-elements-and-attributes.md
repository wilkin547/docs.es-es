---
title: Nombres de atributos y elementos XML declarados (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: 9b586936281bfbf2dcace7cf2892bebf305fc842
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650431"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>Nombres de atributos y elementos XML declarados (Visual Basic)
Este tema proporcionan instrucciones de Visual Basic para asignar nombres a atributos en los literales XML y elementos XML.  En un literal XML, puede especificar un nombre local o un nombre completo. Un nombre calificado se compone de un prefijo de espacio de nombres XML, un signo de dos puntos y un nombre local. Para obtener más información acerca de los prefijos de espacio de nombres XML, vea [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="rules"></a>Reglas  
 Un nombre local de un elemento o atributo en Visual Basic debe cumplir las reglas siguientes.  
  
-   Puede comenzar con un espacio de nombres. Debe comenzar con un carácter alfabético o un carácter de subrayado (`_`).  
  
-   Debe contener únicamente caracteres alfabéticos, dígitos decimales, caracteres de subrayado, puntos (.) y guiones (-).  
  
-   No debe ser más de 1024 caracteres.  
  
-   Dos puntos que aparecen en los nombres indican la demarcación de espacio de nombres. Por lo tanto, puede usar caracteres de dos puntos solo para especificar un espacio de nombres XML para un nombre determinado.  
  
 Además, debe respetar la siguiente directriz.  
  
-   La especificación XML 1.0 reserva todos los nombres que comienzan con la cadena "xml", de cualquier variación de mayúsculas y minúsculas. Por lo tanto, no use esos nombres para el elemento y nombres de atributo.  
  
### <a name="name-length-guidelines"></a>Instrucciones de longitud de nombre  
 A efectos prácticos, un nombre debe ser lo más corto posible aunque tienen que identificar claramente la naturaleza del elemento. Esto mejora la legibilidad del código y reduce el tamaño de archivo de origen y de longitud de línea.  
  
 Sin embargo, su nombre no debe ser tan corto que no adecuadamente describe el elemento o cómo lo usa el código. Esto es importante para la legibilidad del código. Si alguien está intentando lo entiende, o si usted está examinando mucho tiempo después de que lo ha escrito, nombres de elemento adecuados pueden ahorrar tiempo.  
  
## <a name="case-sensitivity-in-names"></a>Mayúsculas y minúsculas en nombres  
 Los nombres de elemento XML distinguen mayúsculas de minúsculas. Esto significa que cuando el compilador de Visual Basic compara dos nombres que difieran en mayúsculas o minúsculas, interpreta como nombres diferentes. Por ejemplo, interpreta `ABC` y `abc` como referencia para separar los elementos.  
  
## <a name="xml-namespaces"></a>Espacios de nombres XML  
 Al crear un elemento XML literal, puede especificar el prefijo de espacio de nombres XML para el nombre del elemento. Para obtener más información, consulte [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="see-also"></a>Vea también  
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)

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
ms.openlocfilehash: 2221f2677183cf360fa82a4d73a679a8b68927d1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819689"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>Nombres de atributos y elementos XML declarados (Visual Basic)
Este tema proporciona instrucciones de Visual Basic para asignar nombres a los elementos XML y atributos en los literales XML.  En un literal XML, puede especificar un nombre local o un nombre completo. Un nombre completo consta de un prefijo de espacio de nombres XML, dos puntos y un nombre local. Para obtener más información acerca de los prefijos de espacio de nombres XML, vea [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="rules"></a>Reglas  
 Un nombre local de un elemento o atributo en Visual Basic debe cumplir las reglas siguientes.  
  
-   Puede comenzar con un espacio de nombres. Debe comenzar con un carácter alfabético o un carácter de subrayado (`_`).  
  
-   Debe contener solo caracteres alfabéticos, dígitos decimales, caracteres de subrayado, puntos (.) y guiones (-).  
  
-   No debe ser más de 1.024 caracteres.  
  
-   Dos puntos que aparecen en los nombres indican demarcación del espacio de nombres. Por lo tanto, puede usar dos puntos exclusivamente para especificar un espacio de nombres XML para un nombre determinado.  
  
 Además, deben adherirse a la instrucción siguiente.  
  
-   La especificación XML 1.0 reserva todos los nombres que comienzan con la cadena "xml", de cualquier variación de mayúsculas y minúsculas. Por lo tanto, no use esos nombres para el elemento y nombres de atributo.  
  
### <a name="name-length-guidelines"></a>Directrices de longitud de nombre  
 Como cuestión práctica, debe ser un nombre más corto posible al identificar claramente la naturaleza del elemento. Esto mejora la legibilidad del código y reduce el tamaño de archivo de origen y de longitud de línea.  
  
 Sin embargo, el nombre no debe ser tan corto que no adecuadamente describe el elemento o cómo lo utiliza el código. Esto es importante para la legibilidad del código. Si alguien más está intentando entenderla, o si usted está examinando mucho tiempo después de que lo escribió, nombres de elemento apropiados pueden ahorrar tiempo.  
  
## <a name="case-sensitivity-in-names"></a>Mayúsculas y minúsculas en nombres  
 Los nombres de elemento XML distinguen mayúsculas de minúsculas. Esto significa que cuando el compilador de Visual Basic compara dos nombres que difieran en mayúsculas o minúsculas, interpreta como nombres diferentes. Por ejemplo, interpreta `ABC` y `abc` remiten al separar los elementos.  
  
## <a name="xml-namespaces"></a>Espacios de nombres XML  
 Al crear un elemento XML literal, puede especificar el prefijo de espacio de nombres XML para el nombre del elemento. Para obtener más información, consulte [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="see-also"></a>Vea también

- [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)

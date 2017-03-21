---
title: Nombres de atributos (Visual Basic) y elementos XML declarados | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: 13
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ed8ecf69170acf9745a4038975e7e3421722d52d
ms.lasthandoff: 03/13/2017

---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>Nombres de atributos y elementos XML declarados (Visual Basic)
Este tema proporciona [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] directrices para asignar nombres a atributos en los literales XML y elementos XML.  En un literal XML, puede especificar un nombre local o un nombre completo. Un nombre calificado se compone de un prefijo de espacio de nombres XML, dos puntos y un nombre local. Para obtener más información acerca de los prefijos de espacio de nombres XML, vea [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="rules"></a>Reglas  
 Un nombre local de un elemento o atributo en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] debe cumplir las reglas siguientes.  
  
-   Puede comenzar con un espacio de nombres. Debe comenzar con un carácter alfabético o un carácter de subrayado (`_`).  
  
-   Debe contener sólo caracteres alfabéticos, dígitos decimales, caracteres de subrayado, puntos (.) y guiones (-).  
  
-   No debe ser más de 1.024 caracteres.  
  
-   Dos puntos que aparecen en los nombres indican la demarcación del espacio de nombres. Por lo tanto, puede utilizar dos puntos solo para especificar un espacio de nombres XML para un nombre determinado.  
  
 Además, debe adherirse a la instrucción siguiente.  
  
-   La especificación XML 1.0 reserva todos los nombres que comienzan con la cadena "xml" de cualquier variación de mayúsculas y minúsculas. Por lo tanto, no use esos nombres para el elemento y nombres de atributo.  
  
### <a name="name-length-guidelines"></a>Directrices de longitud de nombre  
 A efectos prácticos, un nombre debe ser lo más corto posible al identificar claramente la naturaleza del elemento. Esto mejora la legibilidad del código y reduce el tamaño de línea de longitud y el archivo de código fuente.  
  
 Sin embargo, su nombre no debe ser tan corto que no adecuadamente describe el elemento o cómo lo usa el código. Esto es importante para la legibilidad del código. Si alguien intenta entenderlo o si usted busca lo mucho tiempo después de que lo escribió, nombres de elemento adecuados pueden ahorrar tiempo.  
  
## <a name="case-sensitivity-in-names"></a>Mayúsculas y minúsculas en nombres  
 Los nombres de elemento XML distinguen mayúsculas de minúsculas. Esto significa que cuando el [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador compara dos nombres que difieran en mayúsculas o minúsculas, los interpreta como nombres distintos. Por ejemplo, interpreta `ABC` y `abc` como referencia para separar los elementos.  
  
## <a name="xml-namespaces"></a>Espacios de nombres XML  
 Al crear un elemento XML literal, puede especificar el prefijo de espacio de nombres XML para el nombre del elemento. Para obtener más información, consulte [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="see-also"></a>Vea también  
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)

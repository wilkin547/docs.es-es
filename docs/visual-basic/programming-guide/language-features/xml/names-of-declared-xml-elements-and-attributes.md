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
ms.openlocfilehash: 043243eeee7c24d8c63105047fa3e7e0ed58c7b0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374673"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>Nombres de atributos y elementos XML declarados (Visual Basic)
En este tema se proporcionan instrucciones Visual Basic para asignar nombres a los elementos y atributos XML en los literales XML.  En un literal XML, puede especificar un nombre local o un nombre completo. Un nombre completo consta de un prefijo de espacio de nombres XML, dos puntos y un nombre local. Para obtener más información sobre los prefijos de espacios de nombres XML, vea [literal de elemento XML](../../../language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="rules"></a>Reglas  
 Un nombre local de un elemento o atributo de Visual Basic debe cumplir las siguientes reglas.  
  
- Puede comenzar con un espacio de nombres. Debe empezar por un carácter alfabético o un carácter de subrayado ( `_` ).  
  
- Debe contener solo caracteres alfabéticos, dígitos decimales, caracteres de subrayado, puntos (.) y guiones (-).  
  
- No debe tener más de 1.024 caracteres de longitud.  
  
- Los dos puntos que aparecen en los nombres indican la demarcación del espacio de nombres. Por lo tanto, solo puede usar dos puntos para especificar un espacio de nombres XML para un nombre determinado.  
  
 Además, debe cumplir la siguiente directriz.  
  
- La especificación XML 1,0 reserva todos los nombres que comienzan con la cadena "XML", de cualquier variación de mayúsculas y minúsculas. Por lo tanto, no use esos nombres para los nombres de elementos y atributos.  
  
### <a name="name-length-guidelines"></a>Instrucciones de longitud de nombre  
 Como cuestión práctica, un nombre debe ser lo más corto posible y, al mismo tiempo, identificar claramente la naturaleza del elemento. Esto mejora la legibilidad del código y reduce la longitud de línea y el tamaño del archivo de origen.  
  
 Sin embargo, el nombre no debe ser tan corto que no describe adecuadamente el elemento o cómo lo usa el código. Esto es importante para la legibilidad del código. Si alguien más está intentando comprenderlo, o si usted lo consulta mucho tiempo después de escribirlo, los nombres de elemento adecuados pueden ahorrar tiempo.  
  
## <a name="case-sensitivity-in-names"></a>Distinción de mayúsculas y minúsculas en nombres  
 Los nombres de elementos XML distinguen mayúsculas de minúsculas. Esto significa que cuando el compilador de Visual Basic compara dos nombres que solo se diferencian en el uso alfabético de mayúsculas y minúsculas, los interpreta como nombres diferentes. Por ejemplo, interpreta `ABC` y `abc` como referencia a elementos independientes.  
  
## <a name="xml-namespaces"></a>Espacios de nombres XML  
 Al crear un literal de elemento XML, puede especificar el prefijo del espacio de nombres XML para el nombre del elemento. Para obtener más información, vea [literal de elemento XML](../../../language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="see-also"></a>Consulte también

- [Crear XML en Visual Basic](creating-xml.md)
- [Literal de elemento XML](../../../language-reference/xml-literals/xml-element-literal.md)

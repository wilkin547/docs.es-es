---
title: 'Dominio de accesibilidad: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
ms.openlocfilehash: 529d256a553c4000c77bcd5096db1a4d943874ff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141757"
---
# <a name="accessibility-domain-c-reference"></a>Dominio de accesibilidad (Referencia de C#)
El dominio de accesibilidad de un miembro especifica en qué secciones del programa se puede hacer referencia a dicho miembro. Si el miembro está anidado dentro de otro tipo, su dominio de accesibilidad viene determinado por el [nivel de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md) del miembro y por el dominio de accesibilidad del tipo contenedor inmediato.  
  
 El dominio de accesibilidad de un tipo de nivel superior es por lo menos el texto del programa del proyecto en el que se declara. Es decir, el dominio incluye todos los archivos de origen de este proyecto. El dominio de accesibilidad de un tipo anidado es, al menos, el texto del programa del tipo en el que se declara. Es decir, el dominio es el cuerpo del tipo, que incluye todos los tipos anidados. El dominio de accesibilidad de un tipo anidado no puede superar nunca al del tipo contenedor. Estos conceptos se muestran en el siguiente ejemplo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo contiene un tipo de nivel superior, `T1`, y dos clases anidadas, `M1` y `M2`. Las clases contienen campos que tienen diferentes accesibilidades declaradas. En el método `Main`, a cada instrucción le sigue un comentario que indica el dominio de accesibilidad de cada miembro. Observe que las instrucciones que intentan hacer referencia a los miembros inaccesibles están marcadas con comentarios. Si quiere ver los errores generados por el compilador cuando se intenta hacer referencia a un miembro inaccesible, quite los comentarios de uno en uno.  
  
[!code-csharp[csrefKeywordsModifiers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#4)]
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)
- [Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md)
- [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md)
- [Restricciones en el uso de los niveles de accesibilidad](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)
- [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
- [public](../../../csharp/language-reference/keywords/public.md)
- [private](../../../csharp/language-reference/keywords/private.md)
- [protected](../../../csharp/language-reference/keywords/protected.md)
- [internal](../../../csharp/language-reference/keywords/internal.md)

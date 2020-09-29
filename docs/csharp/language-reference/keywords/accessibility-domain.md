---
description: 'Dominio de accesibilidad: Referencia de C#'
title: 'Dominio de accesibilidad: Referencia de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
ms.openlocfilehash: 35fc619dd284ff9915662ba48fa06dd295cbbf42
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168847"
---
# <a name="accessibility-domain-c-reference"></a>Dominio de accesibilidad (Referencia de C#)

El dominio de accesibilidad de un miembro especifica en qué secciones del programa se puede hacer referencia a dicho miembro. Si el miembro está anidado dentro de otro tipo, su dominio de accesibilidad viene determinado por el [nivel de accesibilidad](./accessibility-levels.md) del miembro y por el dominio de accesibilidad del tipo contenedor inmediato.  
  
 El dominio de accesibilidad de un tipo de nivel superior es por lo menos el texto del programa del proyecto en el que se declara. Es decir, el dominio incluye todos los archivos de origen de este proyecto. El dominio de accesibilidad de un tipo anidado es, al menos, el texto del programa del tipo en el que se declara. Es decir, el dominio es el cuerpo del tipo, que incluye todos los tipos anidados. El dominio de accesibilidad de un tipo anidado no puede superar nunca al del tipo contenedor. Estos conceptos se muestran en el siguiente ejemplo.  
  
## <a name="example"></a>Ejemplo  

 Este ejemplo contiene un tipo de nivel superior, `T1`, y dos clases anidadas, `M1` y `M2`. Las clases contienen campos que tienen diferentes accesibilidades declaradas. En el método `Main`, a cada instrucción le sigue un comentario que indica el dominio de accesibilidad de cada miembro. Observe que las instrucciones que intentan hacer referencia a los miembros inaccesibles están marcadas con comentarios. Si quiere ver los errores generados por el compilador cuando se intenta hacer referencia a un miembro inaccesible, quite los comentarios de uno en uno.  
  
[!code-csharp[csrefKeywordsModifiers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#4)]
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](./index.md)
- [Modificadores de acceso](./access-modifiers.md)
- [Niveles de accesibilidad](./accessibility-levels.md)
- [Restricciones en el uso de los niveles de accesibilidad](./restrictions-on-using-accessibility-levels.md)
- [Modificadores de acceso](../../programming-guide/classes-and-structs/access-modifiers.md)
- [public](./public.md)
- [private](./private.md)
- [protected](./protected.md)
- [internal](./internal.md)

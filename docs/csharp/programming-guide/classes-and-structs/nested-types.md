---
title: "Tipos anidados (Guía de programación de C#)"
ms.date: 07/10/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ab13c68b638062ab89c90dbfc51b51b8d72d3bde
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="nested-types-c-programming-guide"></a>Tipos anidados (Guía de programación de C#)
Un tipo definido en una [clase](../../../csharp/language-reference/keywords/class.md) o [struct](../../../csharp/language-reference/keywords/struct.md) se denomina tipo anidado. Por ejemplo:  
  
[!code-csharp[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
Con independencia de si el tipo externo es una clase o struct, los tipos anidados se establecen de manera predeterminada en [private](../../../csharp/language-reference/keywords/private.md), solo son accesibles desde su tipo contenedor. En el ejemplo anterior, la clase `Nested` es inaccesible a los tipos externos. 

También puede especificar un [modificador de acceso](../../language-reference/keywords/access-modifiers.md) para definir la accesibilidad de un tipo anidado, de la manera siguiente:

- Anidar tipos de un **clase** puede ser [público](../../../csharp/language-reference/keywords/public.md), [protegido](../../../csharp/language-reference/keywords/protected.md), [interno](../../../csharp/language-reference/keywords/internal.md), [protegido interno](../../../csharp/language-reference/keywords/protected-internal.md), [privada](../../../csharp/language-reference/keywords/private.md) o [privado protegido](../../../csharp/language-reference/keywords/private-protected.md). 

   Sin embargo, definir una `protected`, `protected internal` o `private protected` dentro de la clase anidada un [clase sealed](../../language-reference/keywords/sealed.md) genera la advertencia del compilador [CS0628](../../misc/cs0628.md), "nuevo miembro protegido declarado en una clase sealed."
  
- Los tipos anidados de un **struct** pueden ser [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md) o [private](../../../csharp/language-reference/keywords/private.md).
  
En el ejemplo siguiente se convierte la clase `Nested` en public:
  
[!code-csharp[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 El tipo anidado o interno puede tener acceso al tipo contenedor o externo. Para tener acceso al tipo contenedor, páselo como un argumento al constructor del tipo anidado. Por ejemplo:  
  
 [!code-csharp[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 Un tipo anidado tiene acceso a todos los miembros que estén accesibles para el tipo contenedor. Puede tener acceso a los miembros privados y protegidos del tipo contenedor, incluidos los miembros protegidos heredados.  
  
 En la declaración anterior, el nombre completo de la clase `Nested` es `Container.Nested`. Este es el nombre que se utiliza para crear una instancia nueva de la clase anidada, de la siguiente manera:  
  
 [!code-csharp[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)

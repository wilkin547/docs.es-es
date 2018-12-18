---
title: 'Tipos anidados: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/10/2017
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: b08a7e95e3ddf7e2392be30f2e69c4ec8f425107
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244016"
---
# <a name="nested-types-c-programming-guide"></a>Tipos anidados (Guía de programación de C#)
Un tipo definido en una [clase](../../../csharp/language-reference/keywords/class.md) o [struct](../../../csharp/language-reference/keywords/struct.md) se denomina tipo anidado. Por ejemplo:  
  
[!code-csharp[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
Con independencia de si el tipo externo es una clase o struct, los tipos anidados se establecen de manera predeterminada en [private](../../../csharp/language-reference/keywords/private.md), solo son accesibles desde su tipo contenedor. En el ejemplo anterior, la clase `Nested` es inaccesible a los tipos externos. 

También puede especificar un [modificador de acceso](../../language-reference/keywords/access-modifiers.md) para definir la accesibilidad de un tipo anidado, de la manera siguiente:

- Los tipos anidados de una **clase** pueden ser [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md), [private](../../../csharp/language-reference/keywords/private.md) o [private protected](../../../csharp/language-reference/keywords/private-protected.md). 

   En cambio, al definir una clase anidada `protected`, `protected internal` o `private protected` dentro de una [clase sellada](../../language-reference/keywords/sealed.md), se genera una advertencia del compilador [CS0628](../../misc/cs0628.md), "Nuevo miembro protegido declarado en la clase sealed".
  
- Los tipos anidados de un **struct** pueden ser [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md) o [private](../../../csharp/language-reference/keywords/private.md).
  
En el ejemplo siguiente se convierte la clase `Nested` en public:
  
[!code-csharp[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 El tipo anidado o interno puede tener acceso al tipo contenedor o externo. Para tener acceso al tipo contenedor, páselo como un argumento al constructor del tipo anidado. Por ejemplo:  
  
 [!code-csharp[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 Un tipo anidado tiene acceso a todos los miembros que estén accesibles para el tipo contenedor. Puede tener acceso a los miembros privados y protegidos del tipo contenedor, incluidos los miembros protegidos heredados.  
  
 En la declaración anterior, el nombre completo de la clase `Nested` es `Container.Nested`. Este es el nombre que se utiliza para crear una instancia nueva de la clase anidada, de la siguiente manera:  
  
 [!code-csharp[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
- [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)

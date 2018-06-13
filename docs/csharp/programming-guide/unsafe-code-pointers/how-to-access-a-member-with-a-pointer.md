---
title: 'Cómo: Obtener acceso a un miembro con un puntero (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
ms.openlocfilehash: 20f0dd18bb5ca132d05335953958d8f747b6abc4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332207"
---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a>Cómo: Obtener acceso a un miembro con un puntero (Guía de programación de C#)
Para tener acceso a un miembro de un struct que se declara en un contexto no seguro, puede usar el operador de acceso a miembros, como se muestra en el ejemplo siguiente en el que `p` es un puntero a un [struct](../../../csharp/language-reference/keywords/struct.md) que contiene un miembro `x`.  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, se declara un [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, que contiene dos coordenadas `x` e `y` y se crean instancias de la misma. Usando el operador de acceso a miembros `->` y un puntero a la instancia `home`, se asignan valores a `x` e `y`.  
  
> [!NOTE]
>  Tenga en cuenta que la expresión `p->x` es equivalente a la expresión `(*p).x`, y puede obtener el mismo resultado con cualquiera de las dos expresiones.  
  
 [!code-csharp[csProgGuidePointers#9](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#10](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_2.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [Tipos](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)

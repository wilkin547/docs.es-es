---
title: 'Cómo: Acceder a un miembro con un puntero: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
ms.openlocfilehash: d0ca4a0b2189ee652ad1d9c2b63690306a651df4
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635078"
---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a>Cómo: Acceder a un miembro con un puntero (Guía de programación de C#)
Para tener acceso a un miembro de un struct que se declara en un contexto no seguro, puede usar el operador de acceso a miembros, como se muestra en el ejemplo siguiente en el que `p` es un puntero a un [struct](../../../csharp/language-reference/keywords/struct.md) que contiene un miembro `x`.  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, se declara un [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, que contiene dos coordenadas `x` e `y` y se crean instancias de la misma. Usando el operador de acceso a miembros `->` y un puntero a la instancia `home`, se asignan valores a `x` e `y`.  
  
> [!NOTE]
>  Tenga en cuenta que la expresión `p->x` es equivalente a la expresión `(*p).x`, y puede obtener el mismo resultado con cualquiera de las dos expresiones.  
  
 [!code-csharp[csProgGuidePointers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#9)]  
  
 [!code-csharp[csProgGuidePointers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#10)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipos](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)

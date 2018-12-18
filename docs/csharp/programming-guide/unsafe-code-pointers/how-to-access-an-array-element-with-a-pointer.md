---
title: 'Acceder a un elemento de matriz con un puntero: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
ms.openlocfilehash: 57b1bebb95c1b3f24e550d554fe369d931d6f6b4
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241806"
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a>Cómo: Acceder a un elemento de matriz con un puntero (Guía de programación de C#)

En un contexto no seguro, puede tener acceso a un elemento en la memoria con el acceso a un elemento de puntero, como se muestra en el ejemplo siguiente:

```csharp
char* charPointer = stackalloc char[123];
for (int i = 65; i < 123; i++)
{
    charPointer[i] = (char)i; //access array elements
}
```

La expresión entre corchetes debe poder convertirse implícitamente en `int`, `uint`, `long` o `ulong`. La operación p[e] es equivalente a \*(p+e). Como C y C++, el acceso al elemento de puntero no comprueba errores fuera de los límites.

## <a name="example"></a>Ejemplo

En este ejemplo, las ubicaciones de memoria 123 se asignan a una matriz de caracteres, `charPointer`. La matriz se usa para mostrar las letras en minúsculas y las letras en mayúsculas en dos bucles [for](../../../csharp/language-reference/keywords/for.md).

Tenga en cuenta que la expresión `charPointer[i]` es equivalente a la expresión `*(charPointer + i)`, y puede obtener el mismo resultado con cualquiera de las dos expresiones.

[!code-csharp[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]

[!code-csharp[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]

**Letras mayúsculas:**
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**
**Letras minúsculas:**
**abcdefghijklmnopqrstuvwxyz**

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipos](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)

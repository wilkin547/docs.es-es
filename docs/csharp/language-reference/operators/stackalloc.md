---
title: 'Operador stackalloc: Referencia de C#'
ms.date: 09/20/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: 9c9767e0c9945a9589d049fa7abba192cb928ad5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846262"
---
# <a name="stackalloc-operator-c-reference"></a>Operador stackalloc (referencia de C#)

El operador `stackalloc` asigna un bloque de memoria en la pila. Un bloque de memoria asignado a la pila creado durante la ejecución del método se descarta automáticamente cuando se devuelva dicho método. No puede liberar explícitamente memoria asignada con el operador `stackalloc`. Un bloque de memoria asignada a la pila no está sujeto a la [recolección de elementos no utilizados](../../../standard/garbage-collection/index.md) y no tiene que fijarse con una [instrucción `fixed`](../keywords/fixed-statement.md).

Puede asignar el resultado del operador `stackalloc` a una variable de uno de los siguientes tipos:

- A partir de C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> o <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente:

  [!code-csharp[stackalloc span](snippets/StackallocOperator.cs#AssignToSpan)]

  No tiene que usar un contexto [unsafe](../keywords/unsafe.md) al asignar un bloque de memoria asignado a la pila para una variable <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>.

  Cuando se trabaja con esos tipos, puede usar una expresión `stackalloc` en expresiones [condicionales](conditional-operator.md) o de asignación, como se muestra en el ejemplo siguiente:

  [!code-csharp[stackalloc expression](snippets/StackallocOperator.cs#AsExpression)]

  A partir de C# 8.0, se puede usar una expresión `stackalloc` dentro de otras expresiones siempre que se permita una variable <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>, como se muestra en el ejemplo siguiente:

  [!code-csharp[stackalloc in nested expressions](snippets/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > Se recomienda usar los tipos <xref:System.Span%601> o <xref:System.ReadOnlySpan%601> para trabajar con memoria asignada a la pila siempre que sea posible.

- Un [tipo de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md), como se muestra en el ejemplo siguiente:

  [!code-csharp[stackalloc pointer](snippets/StackallocOperator.cs#AssignToPointer)]

  Como se muestra en el ejemplo anterior, se debe utilizar un contexto `unsafe` cuando se trabaja con tipos de puntero.

  En el caso de los tipos de puntero, solo se puede usar una expresión `stackalloc` en una declaración de variable local para inicializar la variable.

El contenido de la memoria recién asignada está sin definir. A partir de C# 7.3, puede usar la sintaxis de inicializador de matriz para definir el contenido de la memoria recién asignada. En el ejemplo siguiente se muestran diversas formas de hacerlo:

[!code-csharp[stackalloc initialization](snippets/StackallocOperator.cs#StackallocInit)]

En la expresión `stackalloc T[E]`, `T` debe ser un [tipo no administrado](../builtin-types/unmanaged-types.md) y `E` debe ser una expresión de tipo [int](../builtin-types/integral-numeric-types.md).

## <a name="security"></a>Seguridad

El uso de `stackalloc` habilita automáticamente las características de detección de saturación del búfer en el entorno Common Language Runtime (CLR). Si se detecta saturación del búfer, se finaliza el proceso lo antes posible para minimizar el riesgo de que se ejecute código malintencionado.

## <a name="c-language-specification"></a>especificación del lenguaje C#

Para más información, consulte la sección sobre [asignación de pila](~/_csharplang/spec/unsafe-code.md#stack-allocation) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md) y la nota de la característica [Permitir `stackalloc` en contextos anidados](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [Operadores relacionados con el puntero](pointer-related-operators.md)
- [Tipos de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipos relacionados con el intervalo y la memoria](../../../standard/memory-and-spans/index.md)

---
title: 'Operador stackalloc: Referencia de C#'
ms.custom: seodec18
ms.date: 06/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: 3be4e827e75e4e26a34d9ed70423af5aa317e7fb
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025006"
---
# <a name="stackalloc-operator-c-reference"></a>Operador stackalloc (referencia de C#)

El operador `stackalloc` asigna un bloque de memoria en la pila. Un bloque de memoria asignado a la pila creado durante la ejecución del método se descarta automáticamente cuando se devuelva dicho método. No puede liberar explícitamente memoria asignada con el operador `stackalloc`. Un bloque de memoria asignada a la pila no está sujeto a [recolección de elementos no utilizados](../../../standard/garbage-collection/index.md) y no tiene que fijarse con la instrucción [`fixed`](../keywords/fixed-statement.md).

Puede asignar el resultado del operador `stackalloc` a una variable de uno de los siguientes tipos:

- A partir de C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> o <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente:

  [!code-csharp[stackalloc span](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToSpan)]

  No tiene que usar un contexto [unsafe](../keywords/unsafe.md) al asignar un bloque de memoria asignado a la pila para una variable <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>.

  Cuando se trabaja con esos tipos, puede usar una expresión `stackalloc` en expresiones [condicionales](conditional-operator.md) o de asignación, como se muestra en el ejemplo siguiente:

  [!code-csharp[stackalloc expression](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AsExpression)]

  > [!NOTE]
  > Se recomienda usar los tipos <xref:System.Span%601> o <xref:System.ReadOnlySpan%601> para trabajar con memoria asignada a la pila siempre que sea posible.

- Un [tipo de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md), como se muestra en el ejemplo siguiente:

  [!code-csharp[stackalloc pointer](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToPointer)]

  Como se muestra en el ejemplo anterior, se debe utilizar un contexto `unsafe` cuando se trabaja con tipos de puntero.

El contenido de la memoria recién asignada está sin definir. A partir de C# 7.3, puede usar la sintaxis de inicializador de matriz para definir el contenido de la memoria recién asignada. En el ejemplo siguiente se muestran diversas formas de hacerlo:

[!code-csharp[stackalloc initialization](~/samples/csharp/language-reference/operators/StackallocOperator.cs#StackallocInit)]

## <a name="security"></a>Seguridad

El uso de `stackalloc` habilita automáticamente las características de detección de saturación del búfer en el entorno Common Language Runtime (CLR). Si se detecta saturación del búfer, se finaliza el proceso lo antes posible para minimizar el riesgo de que se ejecute código malintencionado.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección sobre [asignación de pila](~/_csharplang/spec/unsafe-code.md#stack-allocation) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [Operadores relacionados con el puntero](pointer-related-operators.md)
- [Tipos de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Tipos relacionados con el intervalo y la memoria](../../../standard/memory-and-spans/index.md)

---
title: 'Conversión boxing y unboxing: Guía de programación de C#'
ms.date: 07/20/2015
f1_keywords:
- cs.boxing
helpviewer_keywords:
- C# language, boxing
- C# language, unboxing
- unboxing [C#]
- boxing [C#]
ms.assetid: 8da9bbf4-bce9-4b08-b2e5-f64c11c56514
ms.openlocfilehash: 62df08bf4ae3580e9b8d5b3aab0697d396674ca1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76745415"
---
# <a name="boxing-and-unboxing-c-programming-guide"></a>Conversión boxing y unboxing (Guía de programación de C#)

La conversión boxing es el proceso de convertir un [tipo de valor](../../language-reference/builtin-types/value-types.md) en el tipo `object` o en cualquier tipo de interfaz implementado por este tipo de valor. Cuando Common Language Runtime (CLR) aplica la conversión boxing a un tipo de valor, ajusta el valor dentro de una instancia <xref:System.Object?displayProperty=nameWithType> y lo almacena en el montón administrado. La conversión unboxing extrae el tipo de valor del objeto. La conversión boxing es implícita y la conversión unboxing es explícita. El concepto de conversión boxing y unboxing es la base de la vista unificada del sistema de tipos de C#, en el que un valor de cualquier tipo se puede tratar como objeto.

En el ejemplo siguiente, se aplica `i`conversión boxing*a la variable de entero* y esta se asigna al objeto `o`.

[!code-csharp[csProgGuideTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#14)]

Luego se puede aplicar conversión unboxing al objeto `o` y asignarlo a la variable de entero `i`:

[!code-csharp[csProgGuideTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#15)]

En los ejemplos siguientes se muestra cómo usar la conversión boxing en C#.

[!code-csharp[csProgGuideTypes#47](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#47)]

## <a name="performance"></a>Rendimiento

Con relación a las asignaciones simples, las conversiones boxing y unboxing son procesos que consumen muchos recursos. Cuando se aplica la conversión boxing a un tipo de valor, se debe asignar y construir un objeto completamente nuevo. En menor grado, la conversión de tipos requerida para aplicar la conversión unboxing también es costosa. Para más información, vea [Rendimiento](../../../framework/performance/performance-tips.md).

## <a name="boxing"></a>Boxing

La conversión boxing se utiliza para almacenar tipos de valor en el montón de recolección de elementos no utilizados. La conversión boxing es una conversión implícita de un [tipo de valor](../../language-reference/builtin-types/value-types.md) en el tipo `object` o en cualquier tipo de interfaz implementado por este tipo de valor. Al aplicar la conversión boxing a un tipo de valor se asigna una instancia de objeto en el montón y se copia el valor en el nuevo objeto.

Considere la siguiente declaración de una variable de tipo de valor:

[!code-csharp[csProgGuideTypes#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#17)]

La siguiente instrucción aplica implícitamente la operación de conversión boxing en la variable `i`:

[!code-csharp[csProgGuideTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#18)]

El resultado de esta instrucción es crear una referencia de objeto `o` en la pila que hace referencia a un valor del tipo `int` en el montón. Este valor es una copia del tipo de valor asignado a la variable `i`. La diferencia entre las dos variables, `i` y `o`, se muestra en la imagen siguiente de la conversión boxing:

![Gráfico en el que se muestra la diferencia entre las variables i y o.](./media/boxing-and-unboxing/boxing-operation-i-o-variables.gif)

También es posible realizar la conversión boxing de manera explícita, tal como se muestra en el ejemplo siguiente, pero esta nunca es necesaria:

[!code-csharp[csProgGuideTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#19)]

## <a name="description"></a>Description

Este ejemplo convierte una variable de entero `i` en un objeto `o` mediante la conversión boxing. A continuación, el valor almacenado en la variable `i` se cambia de `123` a `456`. El ejemplo muestra que el tipo de valor original y el objeto al que se ha aplicado la conversión boxing usan ubicaciones de memoria independientes y, por consiguiente, pueden almacenar valores diferentes.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideTypes#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#16)]

## <a name="unboxing"></a>Conversión unboxing

La conversión unboxing es una conversión explícita del tipo `object` en un [tipo de valor](../../language-reference/builtin-types/value-types.md) o de un tipo de interfaz en un tipo de valor que implementa la interfaz. Una operación de conversión unboxing consiste en lo siguiente:

- Comprobar la instancia de objeto para asegurarse de que se trata de un valor de conversión boxing del tipo de valor dado.

- Copiar el valor de la instancia en la variable de tipo de valor.

Las siguientes instrucciones muestran las operaciones de conversión boxing y unboxing:

[!code-csharp[csProgGuideTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#21)]

En la figura siguiente se muestra el resultado de las instrucciones anteriores:

![Gráfico en el que se muestra una conversión unboxing.](./media/boxing-and-unboxing/unboxing-conversion-operation.gif)

Para que la conversión unboxing de tipos de valor sea correcta en tiempo de ejecución, el elemento al que se aplica debe ser una referencia a un objeto creado previamente mediante la conversión boxing de una instancia de ese tipo de valor. Si se intenta aplicar la conversión unboxing a `null`, se producirá una excepción <xref:System.NullReferenceException>. Si se intenta aplicar la conversión unboxing a una referencia de un tipo de valor incompatible, se producirá una excepción <xref:System.InvalidCastException>.

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra un caso de conversión unboxing no válida y la excepción `InvalidCastException` resultante. Si se utiliza `try` y `catch`, se muestra un mensaje de error cuando se produce el error.

[!code-csharp[csProgGuideTypes#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#20)]

Este programa produce el resultado siguiente:

`Specified cast is not valid. Error: Incorrect unboxing.`

Si cambia la instrucción:

```csharp
int j = (short) o;
```

a:

```csharp
int j = (int) o;
```

la conversión se realizará y se obtendrá el resultado:

`Unboxing OK.`

## <a name="c-language-specification"></a>especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Tipos de referencia](../../language-reference/keywords/reference-types.md)
- [Tipos de valor](../../language-reference/builtin-types/value-types.md)

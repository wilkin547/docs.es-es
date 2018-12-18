---
title: Uso de tipos que aceptan valores NULL - Guía de programación de C#
ms.custom: seodec18
description: Obtenga información sobre cómo trabajar con tipos de C# que aceptan valores NULL
ms.date: 08/02/2018
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: d2c6f2f78ed71558b71adcc1d4d8cc9a6f459d75
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235220"
---
# <a name="using-nullable-types-c-programming-guide"></a>Uso de tipos que aceptan valores NULL (Guía de programación de C#)

Los tipos que aceptan valores NULL son los que representan todos los valores de un tipo de valor `T` subyacente y un valor [NULL](../../language-reference/keywords/null.md) adicional. Para obtener más información, vea el tema [Tipos que aceptan valores NULL](index.md).

Puede hacer referencia a un tipo que acepta valores NULL en cualquiera de las formas siguientes: `Nullable<T>` o `T?`. Estas dos formas son intercambiables.  
  
## <a name="declaration-and-assignment"></a>Declaración y asignación

Como un tipo de valor se puede convertir de forma implícita al tipo que acepta valores NULL correspondiente, un valor se asigna a un tipo que acepta valores NULL como se haría para su tipo de valor subyacente. También se puede asignar el valor `null`.  Por ejemplo:
  
[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a>Examen de un valor de tipo que acepta valores NULL

Use las propiedades de solo lectura siguientes para examinar una instancia de un tipo que acepta valores NULL en busca de NULL y recuperar un valor de un tipo subyacente:  
  
- <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indica si una instancia de un tipo que acepta valores NULL tiene un valor de su tipo subyacente.
  
- <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> obtiene el valor de un tipo subyacente si <xref:System.Nullable%601.HasValue%2A> es `true`. Si <xref:System.Nullable%601.HasValue%2A> es `false`, la propiedad <xref:System.Nullable%601.Value%2A> inicia una excepción <xref:System.InvalidOperationException>.
  
En el código del ejemplo siguiente se usa la propiedad `HasValue` para comprobar si la variable contiene un valor antes de mostrarlo:
  
[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]
  
También se puede comparar una variable de tipo que acepta valores NULL con `null` en lugar de usar la propiedad `HasValue`, como se muestra en el ejemplo siguiente:  
  
[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

A partir de C# 7.0, se puede usar la [coincidencia de patrones](../../pattern-matching.md) tanto para examinar como para obtener un valor de un tipo que acepta valores NULL:

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-type-to-an-underlying-type"></a>Conversión de un tipo que acepta valores NULL a un tipo subyacente

Si es necesario asignar un valor de tipo que acepta valores NULL a un tipo que no acepta valores NULL, use el [operador de uso combinado de NULL`??`](../../language-reference/operators/null-coalescing-operator.md) para especificar el valor que se va a asignar si un valor de tipo que acepta valores NULL es NULL (también se puede usar el método <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType>):
  
[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

Use el método <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> si el valor que se va usar cuando un valor de tipo que acepta valores NULL es NULL debe ser el valor predeterminado del tipo de valor subyacente.
  
Puede convertir de forma explícita un tipo que acepta valores NULL en un tipo que no acepta valores NULL. Por ejemplo:  
  
[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

En tiempo de ejecución, si el valor de un tipo que acepta valores NULL es NULL, la conversión explícita inicia una excepción <xref:System.InvalidOperationException>.

Un tipo de valor que no acepta valores NULL se convierte implícitamente al tipo que acepta valores NULL correspondiente.
  
## <a name="operators"></a>Operadores

Los tipos que aceptan valores NULL también pueden hacer uso de los operadores predefinidos unario y binario, así como de cualquier operador definido por el usuario que exista para los tipos de valor. Estos operadores generan un valor NULL si uno o los dos operandos son NULL; si no, el operador usa los valores contenidos para calcular el resultado. Por ejemplo:  
  
[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]
  
Para los operadores relacionales (`<`, `>`, `<=`, `>=`), si uno o ambos operandos son NULL, el resultado es `false`. No asuma que, como una comparación determinada (por ejemplo, `<=`) devuelve `false`, la comparación contraria (`>`) devolverá `true`. En el ejemplo siguiente se muestra que 10 no es

- mayor o igual que NULL,
- ni menor que NULL.
  
[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]
  
En el ejemplo anterior también se muestra que una comparación de igualdad entre dos tipos que aceptan valores NULL donde ambos son NULL se evalúa como `true`.

## <a name="boxing-and-unboxing"></a>Conversión boxing y conversión unboxing

A un tipo de valor que acepta valores NULL se le aplica la [conversión boxing](../types/boxing-and-unboxing.md) por las reglas siguientes:

- Si <xref:System.Nullable%601.HasValue%2A> devuelve `false`, se genera la referencia nula.  
- Si <xref:System.Nullable%601.HasValue%2A> devuelve `true`, se aplica la conversión boxing a un valor del tipo de valor subyacente `T`, no a la instancia de <xref:System.Nullable%601>.

Se puede aplicar conversión unboxing al tipo de valor con conversión boxing al tipo que acepta valores NULL correspondiente, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="the-bool-type"></a>Tipo bool?

El tipo que acepta valores NULL `bool?` puede contener tres valores distintos: [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md) y [NULL](../../language-reference/keywords/null.md). El tipo `bool?` es como el tipo de variable booleano que se usa en SQL. Para asegurarse de que los resultados generados por los operadores `&` y `|` sean coherentes con el tipo booleano de tres valores en SQL, se proporcionan los siguientes operadores predefinidos:

- `bool? operator &(bool? x, bool? y)`  
- `bool? operator |(bool? x, bool? y)`  
  
La semántica de estos operadores se define en la tabla siguiente:  
  
|x|y|x e y|x&#124;y|  
|-------|-------|---------|--------------|  
|true|true|true|true|  
|true|False|false|true|  
|true|nulo|nulo|true|  
|False|true|False|true|  
|False|False|False|False|  
|False|nulo|False|nulo|  
|nulo|true|nulo|true|  
|nulo|False|False|nulo|  
|nulo|nulo|nulo|nulo|  

Tenga en cuenta que estos dos operadores no siguen las reglas descritas en la sección [Operadores](#operators): el resultado de un operador de evaluación puede ser distinto de NULL, incluso si uno de los operandos es NULL.
  
## <a name="see-also"></a>Vea también

- [Nullable types](index.md) (Tipos que aceptan valores NULL [Guía de programación de C#])  
- [Guía de programación de C#](../../programming-guide/index.md)  
- [¿Qué significa exactamente "elevado"?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)  

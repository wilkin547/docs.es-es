---
title: Tipos numéricos de punto flotante - referencia de C#
description: 'Información sobre los tipos de punto flotante de C# integrados: float, double y decimal'
ms.date: 02/04/2021
f1_keywords:
- float
- float_CSharpKeyword
- double
- double_CSharpKeyword
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- floating-point numbers [C#]
- ranges of floating-point types [C#]
- size of floating-point types [C#]
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: a086e8de60bbb63408c3f2cd557feb36c4baa0f8
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585759"
---
# <a name="floating-point-numeric-types-c-reference"></a>Tipos numéricos de punto flotante (referencia de C#)

Los *tipos numéricos de punto flotante* representan números reales. Todos los tipos numéricos de punto flotante son [tipos de valor](value-types.md). También son [tipos simples](value-types.md#built-in-value-types) y se pueden inicializar con [literales](#real-literals). Todos los tipos de punto flotante numéricos admiten operadores [aritméticos](../operators/arithmetic-operators.md), [de comparación](../operators/comparison-operators.md) y de [igualdad](../operators/equality-operators.md).

## <a name="characteristics-of-the-floating-point-types"></a>Características de los tipos de punto flotante

C# admite los siguientes tipos de punto flotante predefinidos:
  
|Palabra clave/tipo de C#|Intervalo aproximado|Precisión|Tamaño|Tipo de .NET|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|De ±1,5 x 10<sup>-45</sup> a ±3,4 x 10<sup>38</sup>|De 6 a 9 dígitos aproximadamente|4 bytes|<xref:System.Single?displayProperty=nameWithType>|
|`double`|De ±5,0 × 10<sup>−324</sup> a ±1,7 × 10<sup>308</sup>|De 15 a 17 dígitos aproximadamente|8 bytes|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|De ±1,0 x 10<sup>-28</sup> to ±7,9228 x 10<sup>28</sup>|28-29 dígitos|16 bytes|<xref:System.Decimal?displayProperty=nameWithType>|

En la tabla anterior, cada palabra clave de tipo de C# de la columna ubicada más a la izquierda es un alias del tipo de .NET correspondiente. Son intercambiables. Por ejemplo, en las declaraciones siguientes se declaran variables del mismo tipo:

```csharp
double a = 12.3;
System.Double b = 12.3;
```

El valor predeterminado de cada tipo de punto flotante es cero, `0`. Cada uno de los tipos de punto flotante tiene las constantes `MinValue` y `MaxValue` que proporcionan el valor finito mínimo y máximo de ese tipo. Los tipos `float` y `double` también brindan constantes que representan valores infinitos y no numéricos. Por ejemplo, el tipo `double` ofrece las siguientes constantes: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> y <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.

El tipo de `decimal` es adecuado cuando el grado de precisión requerido viene determinado por el número de dígitos a la derecha del separador decimal. Estos números se utilizan normalmente en aplicaciones financieras, para importes monetarios (por ejemplo, 1,00 $), tasas de interés (por ejemplo, 2,625 %), etc. Los números pares que son precisos únicamente para un dígito decimal se controlan de forma más precisa en el tipo `decimal`: 0,1, por ejemplo, se puede representar exactamente mediante una instancia de `decimal`, mientras que no hay una instancia `double` o `float` que representa exactamente 0,1. Debido a esta diferencia en los tipos numéricos, se pueden producir errores de redondeo inesperados en cálculos aritméticos cuando se usa `double` o `float` para datos decimales. Puede usar `double` en lugar de `decimal` cuando optimizar el rendimiento es más importante que asegurar la precisión. Sin embargo, cualquier diferencia de rendimiento pasaría desapercibida para todas las aplicaciones, salvo las que consumen más cálculos. Otra posible razón para evitar `decimal` es minimizar los requisitos de almacenamiento. Por ejemplo, [ML.NET](../../../machine-learning/how-does-mldotnet-work.md) usa `float` porque la diferencia entre 4 bytes y 16 bytes se acumula para conjuntos de datos muy grandes. Para obtener más información, vea <xref:System.Decimal?displayProperty=nameWithType>.

En una expresión, puede combinar tipos [enteros](integral-numeric-types.md) y tipos `float` y `double`. En este caso, los tipos enteros se convierten implícitamente en uno de los tipos de punto flotante y, si es necesario, el tipo `float` se convierte implícitamente en `double`. La expresión se evalúa de la siguiente forma:

- Si hay un tipo `double` en la expresión, esta se evalúa como `double`, o bien como [`bool`](bool.md) en comparaciones relacionales o de igualdad.
- Si no hay un tipo `double` en la expresión, esta se evalúa como `float`, o bien como `bool` en comparaciones relacionales o de igualdad.

También es posible combinar en una expresión tipos enteros y el tipo `decimal`. En este caso, los tipos enteros se convierten implícitamente en el tipo `decimal` y la expresión se evalúa como `decimal`, o bien como `bool` en comparaciones relacionales y de igualdad.

En una expresión, no se puede mezclar el tipo `decimal` con los tipos `float` y `double`. En este caso, si quiere realizar operaciones aritméticas, de comparación o de igualdad, debe convertir explícitamente los operandos del tipo `decimal` o a este mismo tipo, como se muestra en el ejemplo siguiente:

```csharp-interactive
double a = 1.0;
decimal b = 2.1m;
Console.WriteLine(a + (double)b);
Console.WriteLine((decimal)a + b);
```

Puede usar [cadenas con formato numérico estándar](../../../standard/base-types/standard-numeric-format-strings.md) o [cadenas con formato numérico personalizado](../../../standard/base-types/custom-numeric-format-strings.md) para dar formato a un valor de punto flotante.

## <a name="real-literals"></a>Literales reales

El tipo de un literal real viene determinado por su sufijo, como se indica a continuación:

- El literal sin sufijo o con el sufijo `d` o `D` es del tipo `double`
- El literal con el sufijo `f` o `F` es del tipo `float`
- El literal con el sufijo `m` o `M` es del tipo `decimal`

En el código siguiente se muestra un ejemplo de cada uno de ellos:

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

En el ejemplo anterior también se muestra el uso de `_` como un *separador de dígitos*, que se admite a partir de C# 7.0. Puede usar el separador de dígitos con todos los tipos de literales numéricos.

También puede usar la notación científica; es decir, especificar una parte exponencial de un literal real, como se muestra en el ejemplo siguiente:

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a>Conversiones

Solo hay una conversión implícita entre los tipos numéricos de punto flotante: de `float` a `double`. Sin embargo, puede convertir un tipo de punto flotante a cualquier otro tipo de punto flotante con la [conversión explícita](../operators/type-testing-and-cast.md#cast-expression). Para obtener más información, consulte [Conversiones numéricas integradas](numeric-conversions.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Tipos de punto flotante](~/_csharplang/spec/types.md#floating-point-types)
- [El tipo decimal](~/_csharplang/spec/types.md#the-decimal-type)
- [Literales reales](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Tipos de valor](value-types.md)
- [Tipos enteros](integral-numeric-types.md)
- [Cadenas con formato numérico estándar](../../../standard/base-types/standard-numeric-format-strings.md)
- [Valores numéricos en .NET](../../../standard/numerics.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>

---
title: Tipos numéricos de punto flotante - referencia de C#
description: Información general de los tipos de punto flotante integrados de C#
ms.date: 10/22/2019
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
ms.openlocfilehash: 9c8b11f9337ee9de90f2d4d96b5be162713bfcbd
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093219"
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

Como el tipo `decimal` tiene más precisión y un intervalo más reducido que `float` y `double`, es adecuado para los cálculos financieros y monetarios.

Puede combinar tipos [enteros](integral-numeric-types.md) y tipos de punto flotante en una expresión. En este caso, los tipos enteros se convierten a tipos de punto flotante. La evaluación de la expresión se realiza según las reglas siguientes:

- Si uno de los tipos de punto flotante es `double`, la expresión se evalúa como `double` o [bool](bool.md) en comparaciones relacionales y de igualdad.
- Si no hay ningún tipo `double` en la expresión, esta se evalúa como `float` o [bool](bool.md) en comparaciones relacionales o de igualdad.

Una expresión de punto flotante puede contener los siguientes conjuntos de valores:

- Cero positivo y negativo
- Infinito positivo y negativo
- Valor no numérico (NaN)
- El conjunto finito de valores distintos de cero

Para obtener más información sobre estos valores, vea el estándar IEEE para aritmética binaria de punto flotante, disponible en el sitio web de [IEEE](https://www.ieee.org).

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
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a>Conversiones

Solo hay una conversión implícita entre los tipos numéricos de punto flotante: de `float` a `double`. Sin embargo, puede convertir un tipo de punto flotante a cualquier otro tipo de punto flotante con la [conversión explícita](../operators/type-testing-and-cast.md#cast-operator-). Para obtener más información, consulte [Conversiones numéricas integradas](numeric-conversions.md).

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

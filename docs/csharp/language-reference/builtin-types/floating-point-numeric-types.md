---
title: Tipos numéricos de punto flotante - referencia de C#
description: Información general de los tipos de punto flotante integrados de C#
ms.date: 06/30/2019
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
ms.openlocfilehash: 17ae154780679dd1f42f43f1ec345cdc722815d3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002193"
---
# <a name="floating-point-numeric-types-c-reference"></a>Tipos numéricos de punto flotante (referencia de C#)

Los **tipos de punto flotante** son un subconjunto de **tipos simples** y se pueden inicializar con [*literales*](#floating-point-literals). Todos los tipos de punto flotante también son tipos de valor. Todos los tipos de punto flotante numéricos admiten operadores [aritméticos](../operators/arithmetic-operators.md) [de comparación e igualdad](../operators/equality-operators.md).

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

- Si uno de los tipos de punto flotante es `double`, la expresión se evalúa como `double` o [bool](../keywords/bool.md) en comparaciones relacionales o de igualdad.
- Si no hay ningún tipo `double` en la expresión, esta se evalúa como `float` o [bool](../keywords/bool.md) en comparaciones relacionales o de igualdad.

Una expresión de punto flotante puede contener los siguientes conjuntos de valores:

- Cero positivo y negativo
- Infinito positivo y negativo
- Valor no numérico (NaN)
- El conjunto finito de valores distintos de cero

Para obtener más información sobre estos valores, vea el estándar IEEE para aritmética binaria de punto flotante, disponible en el sitio web de [IEEE](https://www.ieee.org).

Puede usar [cadenas con formato numérico estándar](../../../standard/base-types/standard-numeric-format-strings.md) o [cadenas con formato numérico personalizado](../../../standard/base-types/custom-numeric-format-strings.md) para dar formato a un valor de punto flotante.

## <a name="floating-point-literals"></a>Literales de punto flotante

De forma predeterminada, un literal numérico de punto flotante a la derecha del operador de asignación se trata como `double`. Puede usar sufijos para convertir un literal de punto flotante o entero a un tipo específico:

- El sufijo `d` o `D` convierte un literal en `double`.
- El sufijo `f` o `F` convierte un literal en `float`.
- El sufijo `m` o `M` convierte un literal en `decimal`.

En los siguientes ejemplos se muestra cada sufijo:

```csharp
double d = 3D;
d = 4d;
float f = 3.5F;
f = 5.4f;
decimal myMoney = 300.5m;
myMoney = 400.75M;
```

## <a name="conversions"></a>Conversiones

Hay una conversión implícita (llamada *conversión de ampliación*) desde `float` a `double` porque el intervalo de valores `float` es un subconjunto apropiado de `double` y no hay ninguna pérdida de precisión de `float` a `double`.

Debe usar una conversión explícita para convertir un tipo de punto flotante en otro tipo de punto flotante cuando no se define una conversión implícita del tipo de origen en el tipo de destino. Esto se denomina *conversión de restricción*. El caso explícito es necesario porque la conversión puede producir pérdida de datos. No hay ninguna conversión implícita entre otros tipos de punto flotante y el tipo `decimal` puesto que el tipo `decimal` tiene mayor precisión que `float` o `double`.

Para obtener más información sobre las conversiones numéricas implícitas, consulte [Tabla de conversiones numéricas implícitas](../keywords/implicit-numeric-conversions-table.md).

Para obtener más información sobre las conversiones numéricas explícitas, consulte [Tabla de conversiones numéricas explícitas](../keywords/explicit-numeric-conversions-table.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Tipos enteros](integral-numeric-types.md)
- [Tabla de tipos integrados](../keywords/built-in-types-table.md)
- [Valores numéricos en .NET](../../../standard/numerics.md)
- [Conversiones de tipos](../../programming-guide/types/casting-and-type-conversions.md)
- [Tabla de conversiones numéricas implícitas](../keywords/implicit-numeric-conversions-table.md)
- [Tabla de conversiones numéricas explícitas](../keywords/explicit-numeric-conversions-table.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [Tabla de formatos de presentación para valores numéricos](../keywords/formatting-numeric-results-table.md)
- [Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md)

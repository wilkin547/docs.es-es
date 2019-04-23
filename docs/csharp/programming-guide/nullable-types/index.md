---
title: 'Tipos que aceptan valores NULL: Guía de programación de C#'
ms.custom: seodec18
description: Más información sobre los tipos que aceptan valores NULL de C# y su uso
ms.date: 07/30/2018
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
ms.openlocfilehash: 740b39c9c729f0768e75b0465eb8ca98eb5b318f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61710152"
---
# <a name="nullable-types-c-programming-guide"></a>Tipos que aceptan valores NULL (Guía de programación de C#)

Los tipos que aceptan valores NULL son instancias de la estructura <xref:System.Nullable%601?displayProperty=nameWithType>. Los tipos que aceptan valores NULL pueden representar todos los valores de un tipo `T` subyacente y un valor [NULL](../../language-reference/keywords/null.md) adicional. EL tipo `T` subyacente puede ser cualquier [tipo de valor](../../language-reference/keywords/value-types.md) que no acepte valores NULL. `T` no puede ser un tipo de referencia.

Por ejemplo, puede asignar `null` o cualquier valor entero de <xref:System.Int32.MinValue?displayProperty=nameWithType> a <xref:System.Int32.MaxValue?displayProperty=nameWithType> a un elemento `Nullable<int>` y [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md) o `null` a un elemento `Nullable<bool>`.

Los tipos que aceptan valores NULL se usan cuando es necesario representar el valor indefinido de un tipo subyacente. Una variable booleana solo puede tener dos valores: true y false. No hay ningún valor "sin definir". En muchas aplicaciones de programación, especialmente en las interacciones de las bases de datos, el valor de una variable puede ser indefinido o incluso no estar disponible. Por ejemplo, un campo de una base de datos puede contener los valores true o false, pero también puede no contener ningún valor. En tal caso, se usa un tipo `Nullable<bool>`.

Los tipos que aceptan valores NULL tienen la siguientes características:
  
- Los tipos que aceptan valores NULL representan variables de tipo de valor a las que se puede asignar el valor `null`. No se puede crear un tipo que acepta valores NULL basado en un tipo de referencia. (Los tipos de referencia ya admiten el valor `null`).  
  
- La sintaxis `T?` es una abreviatura de `Nullable<T>`. Las dos formas son intercambiables.  
  
- Asigne un valor a un tipo que acepta valores NULL del mismo modo que para un tipo de valor subyacente: `int? x = 10;` o `double? d = 4.108;`. También puede asignar el valor `null`: `int? x = null;`.  
  
- Use las propiedades de solo lectura <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> y <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> para probar si hay valores NULL y recuperar el valor, como se muestra en el ejemplo siguiente: `if (x.HasValue) y = x.Value;`  
  
  - La propiedad <xref:System.Nullable%601.HasValue%2A> devuelve `true` si la variable contiene un valor, o `false` si es `null`.
  
  - La propiedad <xref:System.Nullable%601.Value%2A> devuelve un valor si <xref:System.Nullable%601.HasValue%2A> devuelve `true`. De lo contrario, se produce una excepción <xref:System.InvalidOperationException>.  
  
- También puede utilizar los operadores `==` y `!=` con un tipo que acepta valores NULL, como se muestra en el ejemplo siguiente: `if (x != null) y = x.Value;`. Si `a` y `b` son ambos NULL, `a == b` se evalúa como `true`.  

- A partir de C# 7.0, se puede usar la [coincidencia de patrones](../../pattern-matching.md#the-is-type-pattern-expression) tanto para examinar como para obtener un valor de un tipo que acepta valores NULL: `if (x is int valueOfX) y = valueOfX;`.
  
- El valor predeterminado de `T?` es una instancia cuya propiedad <xref:System.Nullable%601.HasValue%2A> devuelve `false`.  

- Use el método <xref:System.Nullable%601.GetValueOrDefault> para devolver el valor asignado, o bien el [valor predeterminado](../../language-reference/keywords/default-values-table.md) del tipo subyacente si el valor es `null`.  

- Use el método <xref:System.Nullable%601.GetValueOrDefault(%600)> para devolver el valor asignado, o bien el valor predeterminado proporcionado si el valor es `null`.
  
- Use el [operador de fusión NULL](../../language-reference/operators/null-coalescing-operator.md) (`??`) para asignar un valor a un tipo subyacente basado en un valor del tipo que acepta valores NULL: `int? x = null; int y = x ?? -1;`. En el ejemplo, dado que `x` es NULL, el valor resultante de `y` es `-1`.

- Si se establece una conversión definida por el usuario entre dos tipos de datos, esa misma conversión también se puede usar con las versiones que aceptan valores NULL de dichos tipos de datos.
  
- No se permiten los tipos anidados que aceptan valores NULL. La línea siguiente no se compilará: `Nullable<Nullable<int>> n;`  

Para más información, consulte los temas [Uso de tipos que aceptan valores NULL ](using-nullable-types.md) y [Cómo: Identificar tipos que aceptan valores NULL](how-to-identify-a-nullable-type.md)
  
## <a name="see-also"></a>Vea también

- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Nullable?displayProperty=nameWithType>
- [Operador !](../../language-reference/operators/null-coalescing-operator.md)
- [Guía de programación de C#](../index.md)
- [Guía de C#](../../index.md)
- [Referencia de C#](../../language-reference/index.md)
- [Tipos de valores que aceptan valores NULL (Visual Basic)](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)

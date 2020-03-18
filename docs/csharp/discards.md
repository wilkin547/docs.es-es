---
title: Descartes - Guía de C#
description: Describe la compatibilidad de C# con descartes, que son variables sin asignar y descartables, así como las maneras en que pueden usarse.
ms.technology: csharp-fundamentals
ms.date: 07/21/2017
ms.openlocfilehash: a76e7fc13f92ec0de87153bb35eb3924bb317616
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73100638"
---
# <a name="discards---c-guide"></a>Descartes - Guía de C#

A partir de C# 7.0, C# admite descartes, que son variables temporales y ficticias que no se usan deliberadamente en el código de la aplicación. Los descartes son equivalentes a variables sin asignar, ya que no tienen un valor. Puesto que solo hay una variable de descarte única y es posible que a dicha variable no se le haya asignado almacenamiento, los descartes pueden reducir las asignaciones de memoria. Como la intención de estas variables es que el código sea claro, mejoran su legibilidad y facilidad de mantenimiento.

Para indicar que una variable es un descarte, se le asigna como nombre el carácter de subrayado (`_`). Por ejemplo, la siguiente llamada al método devuelve una tupla de tres donde el primer y el segundo valor se descartan y *area* es una variable declarada previamente para establecerse en el tercer componente correspondiente devuelto por  *GetCityInformation*:

```csharp
(_, _, area) = city.GetCityInformation(cityName);
```

En C# 7.0, se admiten descartes en asignaciones en los contextos siguientes:

- [Deconstrucción](deconstruct.md) de tuplas y objetos.
- Coincidencia de patrones con [is](language-reference/keywords/is.md) y [switch](language-reference/keywords/switch.md).
- Llamadas de métodos con parámetros `out`.
- Un carácter de subrayado `_` independiente cuando no hay `_` dentro del ámbito.

Cuando `_` es un descarte válido, si se intenta recuperar su valor o usarlo en una operación de asignación, se genera el error del compilador CS0301: "El nombre '\_' no existe en el contexto actual". Esto se debe a que no se le ha asignado un valor a `_`, y es posible que tampoco se le haya asignado una ubicación de almacenamiento. Si fuese una variable real no se podría descartar más de un valor, como en el ejemplo anterior.

## <a name="tuple-and-object-deconstruction"></a>Deconstrucción de tuplas y objetos

Los descartes son especialmente útiles en el trabajo con tuplas, cuando el código de la aplicación usa algunos elementos de tupla pero omite otros. Por ejemplo, el siguiente método `QueryCityDataForYears` devuelve una tupla de 6 con el nombre de una ciudad, su superficie, un año, la población de la ciudad en ese año, un segundo año y la población de la ciudad en ese segundo año. En el ejemplo se muestra la evolución de la población entre esos dos años. De los datos disponibles en la tupla, no nos interesa la superficie de la ciudad, y conocemos el nombre de la ciudad y las dos fechas en tiempo de diseño. Como resultado, solo nos interesan los dos valores de población almacenados en la tupla, y podemos controlar los valores restantes como descartes.  

[!code-csharp[Tuple-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

Para obtener más información sobre la deconstrucción de tuplas con descartes, vea [Deconstructing tuples and other types](deconstruct.md#deconstructing-tuple-elements-with-discards) (Deconstruir tuplas y otros tipos).

El método `Deconstruct` de una clase, estructura o interfaz también permite recuperar y deconstruir un conjunto de datos específico de un objeto. Puede usar descartes cuando le interese trabajar con un solo subconjunto de los valores deconstruidos. En el siguiente ejemplo se deconstruye un objeto `Person` en cuatro cadenas (el nombre propio, los apellidos, la ciudad y el estado), pero se descartan los apellidos y el estado.

[!code-csharp[Class-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/class-discard1.cs)]

Para obtener más información sobre la deconstrucción de tipos definidos por el usuario con descartes, vea [Deconstructing tuples and other types](deconstruct.md#deconstructing-a-user-defined-type-with-discards) (Deconstruir tuplas y otros tipos).

## <a name="pattern-matching-with-switch-and-is"></a>Coincidencia de patrones con `switch` y `is`

El *patrón de descarte* se puede usar en la coincidencia de patrones con las palabras clave [is](language-reference/keywords/is.md) y [switch](language-reference/keywords/switch.md). Todas las expresiones siempre coinciden con el patrón de descarte.

En el ejemplo siguiente se define un método `ProvidesFormatInfo` que usa instrucciones [is](language-reference/keywords/is.md) para determinar si un objeto proporciona una implementación de <xref:System.IFormatProvider> y probar si el objeto es `null`. También se usa el patrón de descarte para controlar los objetos que no son NULL de cualquier otro tipo.

[!code-csharp[discard-pattern](../../samples/snippets/csharp/programming-guide/discards/discard-pattern2.cs)]

## <a name="calls-to-methods-with-out-parameters"></a>Llamadas de métodos sin parámetros

Cuando se llama al método `Deconstruct` para deconstruir un tipo definido por el usuario (una instancia de una clase, estructura o interfaz), puede descartar los valores de argumentos `out` individuales. Pero también puede descartar el valor de argumentos `out` al llamar a cualquier método con un parámetro out.

En el ejemplo siguiente se llama al método [DateTime.TryParse(String, out DateTime)](<xref:System.DateTime.TryParse(System.String,System.DateTime@)>) para determinar si la representación de cadena de una fecha es válida en la referencia cultural actual. Dado que al ejemplo solo le interesa validar la cadena de fecha, y no analizarla para extraer la fecha, el argumento `out` para el método es un descarte.

[!code-csharp[discard-with-out](../../samples/snippets/csharp/programming-guide/discards/discard-out1.cs)]

## <a name="a-standalone-discard"></a>Descarte independiente

Puede usar un descarte independiente para indicar cualquier variable que decida omitir. En el ejemplo siguiente se usa un descarte independiente para omitir el objeto <xref:System.Threading.Tasks.Task> devuelto por una operación asincrónica. Como resultado, se suprime la excepción que se produce en la operación cuando está a punto de completarse.

[!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard1.cs)]

Tenga en cuenta que `_` también es un identificador válido. Cuando se usa fuera de un contexto compatible, `_` no se trata como un descarte, sino como una variable válida. Si un identificador denominado `_` ya está en el ámbito, el uso de `_` como descarte independiente puede producir lo siguiente:

- La modificación accidental del valor de la variable `_` en el ámbito, al asignarle el valor del descarte previsto. Por ejemplo:

   [!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#1)]

- Un error del compilador por infringir la seguridad de tipos. Por ejemplo:

   [!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#2)]

- Error del compilador CS0136: "Una variable local o un parámetro denominados '\_' no se pueden declarar en este ámbito porque ese nombre se está usando en un ámbito local envolvente para definir una variable local o un parámetro". Por ejemplo:

   [!code-csharp[standalone-discard](../../samples/snippets/csharp/programming-guide/discards/standalone-discard2.cs#3)]

## <a name="see-also"></a>Vea también

- [Deconstrucción de tuplas y otros tipos](deconstruct.md)
- [Palabra clave `is`](language-reference/keywords/is.md)
- [Palabra clave `switch`](language-reference/keywords/switch.md)

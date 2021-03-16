---
title: Descartes - Guía de C#
description: Describe la compatibilidad de C# con descartes, que son variables sin asignar y descartables, así como las maneras en que pueden usarse.
ms.technology: csharp-fundamentals
ms.date: 09/22/2020
ms.openlocfilehash: eefa81d3bd8d56c9296e01533aaf93c4725323a3
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104957"
---
# <a name="discards---c-guide"></a>Descartes - Guía de C#

A partir de C# 7.0, C# admite descartes, que son variables de marcador de posición que no se usan deliberadamente en el código de la aplicación. Los descartes son equivalentes a variables sin asignar, ya que no tienen un valor. Un descarte comunica la intención al compilador y otros usuarios que leen el código: Pretendía ignorar el resultado de una expresión. Es posible que desee ignorar el resultado de una expresión, uno o varios miembros de una expresión de tupla, un parámetro `out` de un método o el destino de una expresión de coincidencia de patrones.

Puesto que solo hay una variable de descarte única, es posible que a dicha variable no se le haya asignado almacenamiento. Los descartes pueden reducir las asignaciones de memoria. Los descartes aclaran la intención del código. Mejoran la legibilidad y el mantenimiento.

Para indicar que una variable es un descarte, se le asigna como nombre el carácter de subrayado (`_`). Por ejemplo, la siguiente llamada de método devuelve una tupla en la que el primer y el segundo valor son descartes. `area` es una variable declarada previamente establecida en el tercer componente devuelto por `GetCityInformation`:

```csharp
(_, _, area) = city.GetCityInformation(cityName);
```

A partir de C# 9.0, se pueden usar descartes para especificar los parámetros de entrada de una expresión lambda que no se utilizan. Para más información, consulte sección sobre [parámetros de entrada de una expresión lambda](language-reference/operators/lambda-expressions.md#input-parameters-of-a-lambda-expression) en el artículo sobre [expresiones lambda](language-reference/operators/lambda-expressions.md).

Cuando `_` es un descarte válido, si se intenta recuperar su valor o usarlo en una operación de asignación, se genera el error del compilador CS0301: "El nombre '\_' no existe en el contexto actual". Este error se debe a que no se le ha asignado un valor a `_`, y es posible que tampoco se le haya asignado una ubicación de almacenamiento. Si fuese una variable real no se podría descartar más de un valor, como en el ejemplo anterior.

## <a name="tuple-and-object-deconstruction"></a>Deconstrucción de tuplas y objetos

Los descartes son útiles en el trabajo con tuplas, cuando el código de la aplicación usa algunos elementos de tupla pero omite otros. Por ejemplo, el siguiente método `QueryCityDataForYears` devuelve una tupla con el nombre de una ciudad, su superficie, un año, la población de la ciudad en ese año, un segundo año y la población de la ciudad en ese segundo año. En el ejemplo se muestra la evolución de la población entre esos dos años. De los datos disponibles en la tupla, no nos interesa la superficie de la ciudad, y conocemos el nombre de la ciudad y las dos fechas en tiempo de diseño. Como resultado, solo nos interesan los dos valores de población almacenados en la tupla, y podemos controlar los valores restantes como descartes.  

:::code language="csharp" source="snippets/discards/discard-tuple.cs" ID="DiscardTupleMember" :::

Para obtener más información sobre la deconstrucción de tuplas con descartes, vea [Deconstructing tuples and other types](deconstruct.md#deconstructing-tuple-elements-with-discards) (Deconstruir tuplas y otros tipos).

El método `Deconstruct` de una clase, estructura o interfaz también permite recuperar y deconstruir un conjunto de datos específico de un objeto. Puede usar descartes cuando le interese trabajar con un solo subconjunto de los valores deconstruidos. En el siguiente ejemplo se deconstruye un objeto `Person` en cuatro cadenas (el nombre propio, los apellidos, la ciudad y el estado), pero se descartan los apellidos y el estado.

:::code language="csharp" source="snippets/discards/discard-class.cs" :::

Para obtener más información sobre la deconstrucción de tipos definidos por el usuario con descartes, vea [Deconstructing tuples and other types](deconstruct.md#deconstructing-a-user-defined-type-with-discards) (Deconstruir tuplas y otros tipos).

## <a name="pattern-matching-with-switch"></a>Coincidencia de patrones con `switch`

El *patrón de descarte* se puede usar en la coincidencia de patrones con la [expresión switch](language-reference/operators/switch-expression.md). Todas las expresiones, incluida `null`, siempre coinciden con el patrón de descarte.

En el ejemplo siguiente se define un método `ProvidesFormatInfo` que usa una expresión `switch` para determinar si un objeto proporciona una implementación de <xref:System.IFormatProvider> y probar si el objeto es `null`. También se usa el patrón de descarte para controlar los objetos que no son NULL de cualquier otro tipo.

:::code language="csharp" source="snippets/discards/discard-pattern2.cs" ID="DiscardSwitchExample" :::

## <a name="calls-to-methods-with-out-parameters"></a>Llamadas a métodos con parámetros `out`

Cuando se llama al método `Deconstruct` para deconstruir un tipo definido por el usuario (una instancia de una clase, estructura o interfaz), puede descartar los valores de argumentos `out` individuales. Pero también puede descartar el valor de argumentos `out` al llamar a cualquier método con un parámetro `out`.

En el ejemplo siguiente se llama al método [DateTime.TryParse(String, out DateTime)](<xref:System.DateTime.TryParse(System.String,System.DateTime@)>) para determinar si la representación de cadena de una fecha es válida en la referencia cultural actual. Dado que al ejemplo solo le interesa validar la cadena de fecha, y no analizarla para extraer la fecha, el argumento `out` para el método es un descarte.

:::code language="csharp" source="snippets/discards/discard-out1.cs" ID="DiscardOutParameter" :::

## <a name="a-standalone-discard"></a>Descarte independiente

Puede usar un descarte independiente para indicar cualquier variable que decida omitir. Un uso típico es usar una asignación para asegurarse de que un argumento no sea NULL. En el código siguiente se usa un descarte para forzar una asignación. El lado derecho de la asignación utiliza el [operador de uso combinado de NULL](language-reference/operators/null-coalescing-operator.md) para producir <xref:System.ArgumentNullException?displayProperty=nameWithType> cuando el argumento es `null`. El código no necesita el resultado de la asignación, por lo que se descarta. La expresión fuerza una comprobación nula. El descarte aclara su intención: el resultado de la asignación no es necesario ni se usa.

:::code language="csharp" source="snippets/discards/standalone-discard1.cs" ID="ArgNullCheck" :::

En el ejemplo siguiente se usa un descarte independiente para omitir el objeto <xref:System.Threading.Tasks.Task> devuelto por una operación asincrónica. La asignación de la tarea tiene el efecto de suprimir la excepción que se produce en la operación cuando está a punto de completarse. Hace que su intención sea clara: Quiere descartar `Task` y omitir los errores generados a partir de esa operación asincrónica.

:::code language="csharp" source="snippets/discards/standalone-discard1.cs" ID="SnippetDiscardTask" :::

Sin asignar la tarea a un descarte, el código siguiente genera una advertencia del compilador:

:::code language="csharp" source="snippets/discards/standalone-discard1.cs" ID="SnippetNoDiscardTask" :::

> [!NOTE]
> Si ejecuta cualquiera de los dos ejemplos anteriores mediante un depurador, este detendrá el programa cuando se produzca la excepción. Sin un depurador asociado, la excepción se omite en ambos casos en modo silencioso.

`_` también es un identificador válido. Cuando se usa fuera de un contexto compatible, `_` no se trata como un descarte, sino como una variable válida. Si un identificador denominado `_` ya está en el ámbito, el uso de `_` como descarte independiente puede producir lo siguiente:

- La modificación accidental del valor de la variable `_` en el ámbito, al asignarle el valor del descarte previsto. Por ejemplo:
   :::code language="csharp" source="snippets/discards/standalone-discard2.cs" ID="VariableIdentifier" :::
- Un error del compilador por infringir la seguridad de tipos. Por ejemplo:
   :::code language="csharp" source="snippets/discards/standalone-discard2.cs" ID="VariableTypeInference" :::
- Error del compilador CS0136: "Una variable local o un parámetro denominados '\_' no se pueden declarar en este ámbito porque ese nombre se está usando en un ámbito local envolvente para definir una variable local o un parámetro". Por ejemplo:
   :::code language="csharp" source="snippets/discards/standalone-discard2.cs" ID="CannotRedeclare" :::

## <a name="see-also"></a>Consulte también

- [Deconstruir tuplas y otros tipos](deconstruct.md)
- [Palabra clave `is`](language-reference/keywords/is.md)
- [Palabra clave `switch`](language-reference/keywords/switch.md)

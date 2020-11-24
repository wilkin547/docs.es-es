---
title: Separación de cadenas en subcadenas
description: Obtenga información sobre las distintas técnicas para extraer partes de una cadena, como String.Split, expresiones regulares y String.Substring.
ms.date: 10/30/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET], breaking up
ms.openlocfilehash: b753476b7d8e5808fdcacc6f28bd1de5f8b232bb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829654"
---
# <a name="extract-substrings-from-a-string"></a>Extracción de subcadenas de una cadena

En este artículo se tratan algunas técnicas diferentes para extraer partes de una cadena.

- Use el [método Split](#stringsplit-method) cuando las subcadenas que desee están separadas por un carácter de delimitador conocido (o caracteres).
- Las [expresiones regulares](#regular-expressions) son útiles cuando la cadena se ajusta a un patrón fijo.
- Use los [métodos IndexOf y Substring](#stringindexof-and-stringsubstring-methods) cuando no desee extraer *todas* las subcadenas de una cadena.

## <a name="stringsplit-method"></a>Método String.Split

<xref:System.String.Split%2A?displayProperty=nameWithType> proporciona una serie de sobrecargas para ayudarle a dividir una cadena en un grupo de subcadenas en función de uno o más caracteres delimitadores que especifique. Puede elegir limitar el número total de subcadenas en el resultado final, recortar los caracteres de espacio en blanco de las subcadenas o excluir las subcadenas vacías.

En los siguientes ejemplos se muestran tres sobrecargas diferentes de `String.Split()`. En el primer ejemplo se llama a la sobrecarga <xref:System.String.Split(System.Char[])> sin pasar ningún carácter separador. Cuando no se especifica ningún carácter delimitador, `String.Split()` usa delimitadores predeterminados, que son caracteres de espacio en blanco, para dividir la cadena.

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#1)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="1":::

Como puede ver, los caracteres de punto (`.`) se incluyen en dos de las subcadenas. Si desea excluir los caracteres de punto, puede agregar el carácter de punto como un carácter delimitador adicional. En el ejemplo siguiente se muestra cómo hacerlo.

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#2)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="2":::

Los puntos desaparecen de las subcadenas, pero ahora se han incluido dos subcadenas vacías adicionales. Esta subcadena vacía representa la subcadena entre la palabra y el punto que la sigue. Para omitir las subcadenas vacías de la matriz resultante, puede llamar a la sobrecarga <xref:System.String.Split(System.Char[],System.StringSplitOptions)> y especificar <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> para el parámetro `options`.

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#3)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="3":::

## <a name="regular-expressions"></a>Expresiones regulares

Si la cadena se ajusta a un patrón fijo, puede usar una expresión regular para extraer y controlar sus elementos. Por ejemplo, si las cadenas adoptan el formato "*número* *operando* *número*", puede utilizar una [expresión regular](regular-expressions.md) para extraer y administrar los elementos de la cadena. Este es un ejemplo:

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="1":::

El patrón de expresión regular `(\d+)\s+([-+*/])\s+(\d+)` se define como se indica a continuación:

|Patrón|Descripción|
|-------------|-----------------|
|`(\d+)`|Buscar coincidencias con uno o más dígitos decimales. Este es el primer grupo de captura.|
|`\s+`|Coincide con uno o varios caracteres de espacio en blanco.|
|`([-+*/])`|Coincide con un signo de operador aritmético (+, -, *, o /). Este es el segundo grupo de captura.|
|`\s+`|Coincide con uno o varios caracteres de espacio en blanco.|
|`(\d+)`|Buscar coincidencias con uno o más dígitos decimales. Éste es el tercer grupo de captura.|

También puede usar una expresión regular para extraer subcadenas de una cadena basada en un patrón en lugar de un conjunto fijo de caracteres. Este es un escenario común cuando se produce cualquiera de estas condiciones:

- Uno o varios caracteres delimitadores no *siempre* sirven como delimitador en la instancia de <xref:System.String>.

- La secuencia y el número de caracteres delimitadores son variables o desconocidos.

Por ejemplo, el método <xref:System.String.Split%2A> no se puede usar para dividir la cadena siguiente, porque el número de caracteres `\n` (nueva línea) es variable y no siempre sirven como delimitadores.

```text
[This is captured\ntext.]\n\n[\n[This is more captured text.]\n]
\n[Some more captured text:\n   Option1\n   Option2][Terse text.]
```

Una expresión regular puede dividir fácilmente esta cadena, como se muestra en el ejemplo siguiente.

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="2" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="2":::

El patrón de expresión regular `\[([^\[\]]+)\]` se define como se indica a continuación:

|Patrón|Descripción|
|-------------|-----------------|
|`\[`|Coincide con un corchete de apertura.|
|`([^\[\]]+)`|Coincide con cualquier carácter que no sea un corchete de apertura o de cierre una o varias veces. Este es el primer grupo de captura.|
|`\]`|Coincide con un corchete de cierre.|

El método <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> es casi idéntico a <xref:System.String.Split%2A?displayProperty=nameWithType>, salvo que divide una cadena basándose en un patrón de expresión regular en lugar de un juego de caracteres fijo. Por ejemplo, en el ejemplo siguiente se usa el método <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> para dividir una cadena que contiene subcadenas delimitadas por varias combinaciones de guiones y otros caracteres.

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="3" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="3":::

El patrón de expresión regular `\s-\s?[+*]?\s?-\s` se define como se indica a continuación:

|Patrón|Descripción|
|-------------|-----------------|
|`\s-`|Coincide con un carácter de espacio en blanco seguido de un guion.|
|`\s?`|Busca coincidencias con cero o un carácter de espacio en blanco.|
|`[+*]?`|Coincide con cero o una aparición del carácter + o *.|
|`\s?`|Busca coincidencias con cero o un carácter de espacio en blanco.|
|`-\s`|Coincide con un guion seguido de un carácter de espacio en blanco.|

## <a name="stringindexof-and-stringsubstring-methods"></a>Métodos String.IndexOf y String.Substring

Si no está interesado en todas las subcadenas de una cadena, puede que prefiera trabajar con uno de los métodos de comparación de cadenas que devuelve el índice en el que comienza la coincidencia. Después, puede llamar al método <xref:System.String.Substring%2A> para extraer la subcadena que desee. Entre los métodos de comparación de cadenas están los siguientes:

- <xref:System.String.IndexOf%2A>, que devuelve el índice basado en cero de la primera aparición de un carácter o cadena en una instancia de cadena.

- <xref:System.String.IndexOfAny%2A>, que devuelve el índice basado en cero de la instancia de cadena actual de la primera aparición de cualquier carácter de una matriz de caracteres.

- <xref:System.String.LastIndexOf%2A>, que devuelve el índice basado en cero de la última aparición de un carácter o cadena en una instancia de cadena.

- <xref:System.String.LastIndexOfAny%2A>, que devuelve un índice basado en cero en la instancia de la cadena actual de la última aparición de cualquier carácter de una matriz de caracteres.

En el ejemplo siguiente se utiliza el método <xref:System.String.IndexOf%2A> para encontrar los puntos de una cadena. A continuación, usa el método <xref:System.String.Substring%2A> para devolver oraciones completas.

:::code language="csharp" source="snippets/parse-strings/csharp/indexof.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/indexof.vb" id="1":::

## <a name="see-also"></a>Vea también

- [Operaciones básicas de cadenas en .NET](basic-string-operations.md)
- [Expresiones regulares de .NET](regular-expressions.md)
- [Procedimiento para analizar cadenas mediante String.Split en C#](../../csharp/how-to/parse-strings-using-split.md)

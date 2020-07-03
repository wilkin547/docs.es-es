---
title: Procedimiento para modificar el contenido de cadenas - Guía de C#
ms.date: 02/26/2018
helpviewer_keywords:
- strings [C#], modifying
ms.openlocfilehash: e607a8a2e96a73f64463d75a75a2bfe3f518d118
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324165"
---
# <a name="how-to-modify-string-contents-in-c"></a>Procedimiento para modificar el contenido de cadenas en C\#

En este artículo se muestran varias técnicas para producir una `string` modificando una `string` existente. Todas las técnicas mostradas devuelven el resultado de las modificaciones como un objeto `string` nuevo. Para demostrar que las cadenas originales y modificadas son instancias distintas, los ejemplos almacenan el resultado en una variable nueva. Al ejecutar cada ejemplo, se puede examinar tanto el objeto `string` original como el objeto `string` nuevo y modificado.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

En este artículo se muestran varias técnicas. Puede reemplazar el texto existente. Puede buscar patrones y reemplazar el texto coincidente por otro texto. Puede tratar una cadena con una secuencia de caracteres. También puede usar métodos de conveniencia para eliminar espacios en blanco. Elija la técnica con mayor coincidencia con el escenario.

## <a name="replace-text"></a>Reemplazo de texto

Con el código siguiente se crea una cadena mediante el reemplazo de texto con un sustituto.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet1":::

En el código anterior se muestra esta propiedad *inmutable* de las cadenas. En el ejemplo anterior puede ver que la cadena original, `source`, no se ha modificado. Con el método <xref:System.String.Replace%2A?displayProperty=nameWithType> se crea una `string` que contiene las modificaciones.

Con el método <xref:System.String.Replace%2A> se pueden reemplazar cadenas o caracteres únicos. En ambos casos, se reemplazan todas las instancias del texto buscado.  En el siguiente ejemplo se reemplazan todos los caracteres " " por "\_":

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet2":::

La cadena de origen se mantiene y se devuelve una cadena nueva con los reemplazos.

## <a name="trim-white-space"></a>Recorte de espacios en blanco

Puede usar los métodos <xref:System.String.Trim%2A?displayProperty=nameWithType>, <xref:System.String.TrimStart%2A?displayProperty=nameWithType>, y <xref:System.String.TrimEnd%2A?displayProperty=nameWithType> para quitar los espacios en blanco al inicio y al final.  En el código siguiente se muestra un ejemplo de cada caso. La cadena de origen no cambia; con estos métodos se devuelve una cadena nueva con el contenido modificado.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet3":::

## <a name="remove-text"></a>Eliminación de texto

Puede quitar texto de una cadena con el método <xref:System.String.Remove%2A?displayProperty=nameWithType>. Este método quita un número de caracteres que comienzan con un índice específico. En el siguiente ejemplo se muestra cómo usar <xref:System.String.IndexOf%2A?displayProperty=nameWithType> seguido por <xref:System.String.Remove%2A> para quitar texto de una cadena:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet4":::

## <a name="replace-matching-patterns"></a>Reemplazo de patrones de coincidencia

Puede usar [expresiones regulares](../../standard/base-types/regular-expressions.md) para reemplazar texto que coincida con patrones por texto nuevo, posiblemente definido por un patrón. En el ejemplo siguiente se usa la clase <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> para encontrar un patrón en una cadena de origen y reemplazarlo con un uso de mayúsculas y minúsculas adecuado. Con el método <xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.Text.RegularExpressions.MatchEvaluator,System.Text.RegularExpressions.RegexOptions)?displayProperty=nameWithType> se usa una función que proporciona la lógica del reemplazo de uno de los argumentos. En este ejemplo, la función `LocalReplaceMatchCase` es una **función local** declarada dentro del método de ejemplo. `LocalReplaceMatchCase` usa la clase <xref:System.Text.StringBuilder?displayProperty=nameWithType> para crear la cadena de reemplazo con un uso de mayúsculas y minúsculas adecuado.

Las expresiones regulares son más útiles al buscar y reemplazar texto que sigue un patrón, en vez de texto que ya conoce. Para obtener más información, vea [Procedimiento para buscar cadenas](search-strings.md). Con el patrón de búsqueda "the\s" se busca la palabra "the" seguida de un carácter de espacio en blanco. Con esa parte del patrón se asegura de que no se busca "there" en la cadena de origen. Para obtener más información sobre los elementos de lenguaje de expresiones regulares, vea [Lenguaje de expresiones regulares - Referencia rápida](../../standard/base-types/regular-expression-language-quick-reference.md).

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet5":::

Con el método <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> se devuelve una cadena inmutable con el contenido del objeto <xref:System.Text.StringBuilder>.

## <a name="modifying-individual-characters"></a>Modificación de caracteres individuales

Puede producir un matriz de caracteres a partir de una cadena, modificar el contenido de la matriz y crear después una cadena a partir del contenido modificado de la matriz.

En el siguiente ejemplo se muestra cómo reemplazar un conjunto de caracteres en una cadena. En primer lugar, se usa el método <xref:System.String.ToCharArray?displayProperty=nameWithType> para crear una matriz de caracteres. Se usa el método <xref:System.String.IndexOf%2A> para encontrar el índice de inicio de la palabra "fox". Los siguientes tres caracteres se reemplazan por otra palabra. Por último, se construye una cadena nueva a partir de la matriz de carácter actualizada.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet6":::

## <a name="programmatically-build-up-string-content"></a>Creación mediante programación del contenido de la cadena

Dado que las cadenas son inmutables, en los ejemplos anteriores se crean cadenas temporales o matrices de caracteres. En escenarios de alto rendimiento, puede ser conveniente evitar estas asignaciones de montón. .NET Core proporciona un método <xref:System.String.Create%2A?displayProperty=nameWithType> que permite rellenar mediante programación el contenido de los caracteres de una cadena a través de una devolución de llamada, a la vez que evita las asignaciones de cadenas temporales intermedias.

:::code language="csharp" source="../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs" id="Snippet7":::

Puede modificar una cadena en un bloque fijo con código no seguro, pero es **totalmente** desaconsejable modificar el contenido de la cadena una vez que se ha creado. Si lo hace, puede haber problemas imprevisibles. Por ejemplo, si alguien se conecta a una cadena que tiene el mismo contenido que la suya, esa persona obtendrá la copia de usted y no esperará que usted modifique la cadena.

## <a name="see-also"></a>Vea también

- [Expresiones regulares de .NET Framework](../../standard/base-types/regular-expressions.md)
- [Lenguaje de expresiones regulares: referencia rápida](../../standard/base-types/regular-expression-language-quick-reference.md)

---
title: Procedimiento para modificar el contenido de cadenas - Guía de C#
ms.date: 02/26/2018
helpviewer_keywords:
- strings [C#], modifying
ms.openlocfilehash: 539e313173d46c2c92399cefe94207c8beed03b4
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973263"
---
# <a name="how-to-modify-string-contents-in-c"></a>Procedimiento para modificar el contenido de cadenas en C\#

En este artículo se muestran varias técnicas para producir una `string` modificando una `string` existente. Todas las técnicas mostradas devuelven el resultado de las modificaciones como un objeto `string` nuevo. Para indicarlo de forma clara, en todos los ejemplos se almacena el resultado en una variable nueva. Entonces, podrá examinar tanto la `string` original como la `string` resultante de la modificación al ejecutar cada ejemplo.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

En este artículo se muestran varias técnicas. Puede reemplazar el texto existente. Puede buscar patrones y reemplazar el texto coincidente por otro texto. Puede tratar una cadena con una secuencia de caracteres. También puede usar métodos de conveniencia para eliminar espacios en blanco. Debe elegir la técnica con mayor coincidencia con su caso.

## <a name="replace-text"></a>Reemplazo de texto

Con el código siguiente se crea una cadena mediante el reemplazo de texto con un sustituto.

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#1)]

En el código anterior se muestra esta propiedad *inmutable* de las cadenas. En el ejemplo anterior puede ver que la cadena original, `source`, no se ha modificado. Con el método <xref:System.String.Replace%2A?displayProperty=nameWithType> se crea una `string` que contiene las modificaciones.

Con el método <xref:System.String.Replace%2A> se pueden reemplazar cadenas o caracteres únicos. En ambos casos, se reemplazan todas las instancias del texto buscado.  En el siguiente ejemplo se reemplazan todos los caracteres " " por "\_":

[!code-csharp-interactive[replace characters](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#2)]

La cadena de origen se mantiene y se devuelve una cadena nueva con los reemplazos.

## <a name="trim-white-space"></a>Recorte de espacios en blanco

Puede usar los métodos <xref:System.String.Trim%2A?displayProperty=nameWithType>, <xref:System.String.TrimStart%2A?displayProperty=nameWithType>, y <xref:System.String.TrimEnd%2A?displayProperty=nameWithType> para quitar los espacios en blanco al inicio y al final.  En el código siguiente se muestra un ejemplo de cada caso. La cadena de origen no cambia; con estos métodos se devuelve una cadena nueva con el contenido modificado.

[!code-csharp-interactive[trim white space](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#3)]

## <a name="remove-text"></a>Eliminación de texto

Puede quitar texto de una cadena con el método <xref:System.String.Remove%2A?displayProperty=nameWithType>. Este método quita un número de caracteres que comienzan con un índice específico. En el siguiente ejemplo se muestra cómo usar <xref:System.String.IndexOf%2A?displayProperty=nameWithType> seguido por <xref:System.String.Remove%2A> para quitar texto de una cadena:

[!code-csharp-interactive[remove text](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#4)]

## <a name="replace-matching-patterns"></a>Reemplazo de patrones de coincidencia

Puede usar [expresiones regulares](../../standard/base-types/regular-expressions.md) para reemplazar texto que coincida con patrones por texto nuevo, posiblemente definido por un patrón. En el ejemplo siguiente se usa la clase <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> para encontrar un patrón en una cadena de origen y reemplazarlo con un uso de mayúsculas y minúsculas adecuado. Con el método <xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.Text.RegularExpressions.MatchEvaluator,System.Text.RegularExpressions.RegexOptions)?displayProperty=nameWithType> se usa una función que proporciona la lógica del reemplazo de uno de los argumentos. En este ejemplo, la función `LocalReplaceMatchCase` es una **función local** declarada dentro del método de ejemplo. `LocalReplaceMatchCase` usa la clase <xref:System.Text.StringBuilder?displayProperty=nameWithType> para crear la cadena de reemplazo con un uso de mayúsculas y minúsculas adecuado.

Las expresiones regulares son más útiles al buscar y reemplazar texto que sigue un patrón, en vez de texto que ya conoce. Vea [Cómo buscar cadenas](search-strings.md) para obtener más información. Con el patrón de búsqueda "the\s" se busca la palabra "the" seguida de un carácter de espacio en blanco. Con esa parte del patrón se asegura de que no se busca "there" en la cadena de origen. Para obtener más información sobre los elementos de lenguaje de expresiones regulares, vea [Lenguaje de expresiones regulares - Referencia rápida](../../standard/base-types/regular-expression-language-quick-reference.md).

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#5)]

Con el método <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> se devuelve una cadena inmutable con el contenido del objeto <xref:System.Text.StringBuilder>.

## <a name="modifying-individual-characters"></a>Modificación de caracteres individuales

Puede producir un matriz de caracteres a partir de una cadena, modificar el contenido de la matriz y crear después una cadena a partir del contenido modificado de la matriz.

En el siguiente ejemplo se muestra cómo reemplazar un conjunto de caracteres en una cadena. En primer lugar, se usa el método <xref:System.String.ToCharArray?displayProperty=nameWithName> para crear una matriz de caracteres. Se usa el método <xref:System.String.IndexOf%2A> para encontrar el índice de inicio de la palabra "fox". Los siguientes tres caracteres se reemplazan por otra palabra. Por último, se construye una cadena nueva a partir de la matriz de carácter actualizada.

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#6)]

## <a name="unsafe-modifications-to-string"></a>Modificaciones no seguras a una cadena

Con el código **unsafe** puede modificar una cadena "en contexto" después de haberla creado. Con este código se anulan muchas de las características de .NET diseñadas para minimizar ciertos tipos de errores en el código. Es necesario su uso para modificar una cadena en contexto porque la clase de cadena se diseña como un tipo **inmutable**. Una vez se haya creado, el valor no cambia. El código no seguro evita esta propiedad mediante el acceso y la modificación de la memoria que usa una `string` sin usar los métodos `string` normales.
En el ejemplo siguiente se indican estas extrañas situaciones en las que quiere modificar una cadena en contexto con código no seguro. En este ejemplo se muestra cómo usar la palabra clave `fixed`. Con la palabra clave `fixed` se evita que el recolector de elementos no utilizados (GC) mueva los objetos de cadenas en memoria mientras que el código accede a la memoria mediante el puntero no seguro. También muestra un posible efecto secundario de operaciones no seguras en cadenas que se obtienen de la manera en que el compilador de C# almacena cadenas (internos) internamente. En general, no debe usar esta técnica a no ser que sea absolutamente necesario. Puede obtener más información en los artículos sobre [unsafe](../language-reference/keywords/unsafe.md) y [fixed](../language-reference/keywords/fixed-statement.md). En la referencia a la API para <xref:System.String.Intern%2A> se incluye información sobre el internamiento de cadenas.

[!code-csharp[unsafe ways to create a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#7)]

Eche un vistazo al código de nuestro [repositorio de GitHub](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings) y pruebe estos ejemplos. O bien, puede descargar los ejemplos [como un archivo ZIP](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip).

## <a name="see-also"></a>Vea también

- [Expresiones regulares de .NET Framework](../../standard/base-types/regular-expressions.md)
- [Lenguaje de expresiones regulares: referencia rápida](../../standard/base-types/regular-expression-language-quick-reference.md)

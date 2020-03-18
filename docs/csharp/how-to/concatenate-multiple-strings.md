---
title: Procedimiento para concatenar varias cadenas (Guía de C#)
description: Hay varias maneras de concatenar cadenas en C#. Obtenga información sobre las opciones y las razones para las diferentes opciones.
ms.date: 02/20/2018
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
ms.openlocfilehash: 9a0640a7ce73fa8454442cd301157bf5c265f9de
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713899"
---
# <a name="how-to-concatenate-multiple-strings-c-guide"></a>Procedimiento para concatenar varias cadenas (Guía de C#)

*Concatenación* es el proceso de anexar una cadena al final de otra cadena. Las cadenas se concatenan con el operador `+`. En el caso de los literales y las constantes de cadena, la concatenación se produce en tiempo de compilación, y no en tiempo de ejecución. En cambio, para las variables de cadena, la concatenación solo se produce en tiempo de ejecución.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

En el ejemplo siguiente se usa la concatenación para dividir un literal de cadena larga en cadenas más pequeñas para mejorar la legibilidad del código fuente. Estas partes se concatenan en una sola cadena en tiempo de compilación. No existe ningún costo de rendimiento en tiempo de ejecución independientemente del número de cadenas de que se trate.  
  
 [!code-csharp-interactive[Combining strings at compile time](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#1)]  

Para concatenar variables de cadena, puede usar los operadores `+` o `+=`, la [interpolación de cadena](../language-reference/tokens/interpolated.md) o los métodos <xref:System.String.Format%2A?displayProperty=nameWithType>, <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Join%2A?displayProperty=nameWithType> o <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>. El operador `+` es sencillo de usar y genera un código intuitivo. Aunque use varios operadores `+` en una instrucción, el contenido de la cadena se copiará solo una vez. En el código siguiente se muestran ejemplos del uso de los operadores `+` y `+=` para concatenar cadenas:

[!code-csharp-interactive[combining strings using +](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#2)]  

En algunas expresiones, es más fácil concatenar cadenas mediante la interpolación de cadena, como se muestra en este código:
  
[!code-csharp-interactive[building strings using string interpolation](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#3)]  
  
> [!NOTE]
> En operaciones de concatenación de cadenas, el compilador de C# trata una cadena NULL igual que una cadena vacía.

Otro método para concatenar cadenas es <xref:System.String.Format%2A?displayProperty=nameWithType>. Este método funciona bien para compilar una cadena a partir de un número reducido de cadenas de componente.

En otros casos, puede combinar cadenas en un bucle, donde no sabe cuántas cadenas de origen se combinan, y el número real de cadenas de origen puede ser bastante elevado. La clase <xref:System.Text.StringBuilder> se diseñó para estos escenarios. El código siguiente usa el método <xref:System.Text.StringBuilder.Append%2A> de la clase <xref:System.Text.StringBuilder> para concatenar cadenas.  
  
[!code-csharp-interactive[string concatenation using string builder](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#4)]  

Puede obtener más información sobre las [razones para elegir la concatenación de cadenas o sobre la clase `StringBuilder`](xref:System.Text.StringBuilder#StringAndSB).

Otra opción para combinar cadenas a partir de una colección consiste en usar el método <xref:System.String.Concat%2A?displayProperty=nameWithType>. Use el método <xref:System.String.Join%2A?displayProperty=nameWithType> si las cadenas de origen se deben separar con un delimitador. El código siguiente combina una matriz de palabras usando ambos métodos:

[!code-csharp-interactive[concatenation of string collection](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#5)]

Por último, puede usar [LINQ](../programming-guide/concepts/linq/index.md) y el método <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType> para combinar cadenas a partir de una colección. Este método combina las cadenas de origen mediante una expresión lambda. La expresión lambda realiza el trabajo de agregar cada cadena a la acumulación existente. En el ejemplo siguiente se combina una matriz de palabras mediante la adición de un espacio entre cada palabra de la matriz:

[!code-csharp-interactive[string concatenation using LINQ expressions](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#6)]  

Eche un vistazo al código de nuestro [repositorio de GitHub](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings) y pruebe estos ejemplos. O bien, puede descargar los ejemplos [como un archivo ZIP](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip).

## <a name="see-also"></a>Vea también

- <xref:System.String>
- <xref:System.Text.StringBuilder>
- [Guía de programación de C#](../programming-guide/index.md)
- [Cadenas](../programming-guide/strings/index.md)

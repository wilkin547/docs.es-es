---
title: Expresiones regulares de .NET
description: Use expresiones regulares para buscar patrones de caracteres específicos, validar texto, trabajar con subcadenas de texto y agregar cadenas extraídas en una colección en .NET.
ms.date: 06/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pattern-matching with regular expressions, about pattern-matching
- substrings
- searching with regular expressions, about regular expressions
- pattern-matching with regular expressions
- searching with regular expressions
- parsing text with regular expressions
- regular expressions [.NET], about regular expressions
- regular expressions [.NET]
- .NET regular expressions, about
- characters [.NET], regular expressions
- parsing text with regular expressions, overview
- .NET regular expressions
- strings [.NET], regular expressions
ms.assetid: 521b3f6d-f869-42e1-93e5-158c54a6895d
ms.openlocfilehash: 6704ab4a99789e2e0bb4c4336f8c73aa8a89671d
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888989"
---
# <a name="net-regular-expressions"></a>Expresiones regulares de .NET

Las expresiones regulares proporcionan un método eficaz y flexible para procesar texto. La notación extensa de coincidencia de patrones de expresiones regulares permite analizar rápidamente grandes cantidades de texto para lo siguiente:

- Buscar patrones concretos de caracteres.
- Validar el texto para garantizar que coincide con un patrón predefinido (como una dirección de correo electrónico).
- Extraer, editar, reemplazar o eliminar subcadenas de texto.
- Agregar cadenas extraídas en una colección para generar un informe.

Para muchas aplicaciones que usan cadenas o analizan grandes bloques de texto, las expresiones regulares son una herramienta indispensable.  
  
## <a name="how-regular-expressions-work"></a>Funcionamiento de las expresiones regulares

 El eje del procesamiento de texto mediante expresiones regulares es el motor de expresiones regulares, que viene representado por el objeto <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> en .NET. Como mínimo, el procesamiento de texto mediante expresiones regulares necesita que el motor de expresiones regulares disponga de los dos elementos de información siguientes:  
  
- El patrón de expresión regular que se debe identificar en el texto.  
  
     En .NET, los patrones de expresiones regulares se definen mediante una sintaxis o un lenguaje especial, que es compatible con las expresiones regulares de Perl 5 y agrega algunas características adicionales, como búsquedas de coincidencias de derecha a izquierda. Para obtener más información, consulte [Lenguaje de expresiones regulares: Referencia rápida](regular-expression-language-quick-reference.md).  
  
- El texto que se debe analizar para el patrón de expresión regular.  
  
Los métodos de la clase <xref:System.Text.RegularExpressions.Regex> permiten realizar las operaciones siguientes:  
  
- Determinar si el patrón de expresión regular se produce en el texto de entrada llamando al método <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType>. Para obtener un ejemplo en donde se utiliza el método <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> para validar texto, vea [Procedimiento: Comprobación de que las cadenas están en un formato de correo electrónico válido](how-to-verify-that-strings-are-in-valid-email-format.md).  
  
- Recuperar una o todas las apariciones del texto que coincide con el patrón de expresión regular llamando al método <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType> o <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType>. El primer método devuelve un objeto <xref:System.Text.RegularExpressions.Match?displayProperty=nameWithType> que proporciona información sobre el texto coincidente. El segundo método devuelve un objeto <xref:System.Text.RegularExpressions.MatchCollection> que contiene un objeto <xref:System.Text.RegularExpressions.Match?displayProperty=nameWithType> por cada coincidencia encontrada en el texto analizado.  
  
- Reemplazar el texto que coincide con el patrón de expresión regular llamando al método <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType>. Para obtener ejemplos en donde se utiliza el método <xref:System.Text.RegularExpressions.Regex.Replace%2A> para cambiar formatos de fecha y quitar caracteres no válidos de una cadena, vea [Procedimiento: Eliminación de caracteres no válidos de una cadena](how-to-strip-invalid-characters-from-a-string.md) y [Ejemplo: Cambio de formatos de fecha](regular-expression-example-changing-date-formats.md).  
  
Para obtener información general acerca del modelo de objetos de expresiones regulares, consulte [El modelo de objetos de expresión regular](the-regular-expression-object-model.md).  
  
Para obtener más información acerca del lenguaje de expresiones regulares, consulte [Lenguaje de expresiones regulares - Referencia rápida](regular-expression-language-quick-reference.md) o descargue e imprima uno de estos folletos:  
  
- [Referencia rápida en formato Word (.docx)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.docx)  
- [Referencia rápida en formato PDF (.pdf)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.pdf)  
  
## <a name="regular-expression-examples"></a>Ejemplos de expresiones regulares

La clase <xref:System.String> incluye varios métodos de búsqueda y reemplazo de cadenas que puede usar cuando desee buscar cadenas literales en una cadena mayor. Las expresiones regulares son muy útiles cuando se desea buscar una de varias subcadenas en una cadena mayor o cuando se desea identificar patrones en una cadena, como se muestra en los ejemplos siguientes.

[!INCLUDE [regex](../../../includes/regex.md)]

> [!TIP]
> El espacio de nombres <xref:System.Web.RegularExpressions> contiene un número de objetos de expresión regular que implementan modelos de expresión regular predefinidos para el análisis de cadenas a partir de documentos HTML, XML y ASP.NET. Por ejemplo, la clase <xref:System.Web.RegularExpressions.TagRegex> identifica las etiquetas de inicio en una cadena y la clase <xref:System.Web.RegularExpressions.CommentRegex> identifica los comentarios de ASP.NET en una cadena.

### <a name="example-1-replace-substrings"></a>Ejemplo 1: Reemplazo de subcadenas  

 Suponga que una lista de distribución de correo contiene nombres que a veces incluyen un tratamiento (Sr., Sra. o Srta.) junto con un nombre y un apellido. Si no desea incluir los tratamientos al generar las etiquetas de los sobres a partir de la lista, puede usar una expresión regular para quitarlos, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[Conceptual.Regex#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex/cs/example1.cs#2)]
 [!code-vb[Conceptual.Regex#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex/vb/example1.vb#2)]  
  
 El patrón de expresión regular `(Mr\.? |Mrs\.? |Miss |Ms\.? )` busca coincidencias con cualquier aparición de "Mr ", "Mr. ", "Mrs ", "Mrs. ", "Miss ", "Ms " o "Ms. ". La llamada al método <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> reemplaza la cadena coincidente con <xref:System.String.Empty?displayProperty=nameWithType>; es decir, la quita de la cadena original.  
  
### <a name="example-2-identify-duplicated-words"></a>Ejemplo 2: Identificación de palabras duplicadas  

 Duplicar palabras accidentalmente es un error frecuente que cometen los escritores. Se puede usar una expresión regular para identificar palabras duplicadas, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[Conceptual.Regex#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex/cs/example2.cs#3)]
 [!code-vb[Conceptual.Regex#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex/vb/example2.vb#3)]  
  
 El patrón de expresión regular `\b(\w+?)\s\1\b` se puede interpretar de la manera siguiente:  
  
> [!div class="mx-tdCol2BreakAll"]
> |Modelo|Interpretación|  
> |-|-|
> |`\b`|Empieza en un límite de palabras.|  
> |`(\w+?)`|Coincide con uno o más caracteres de palabra, pero con el menor número de caracteres posible. Juntos, forman un grupo al que se puede hacer referencia como `\1`.|  
> |`\s`|Coincide con un carácter de espacio en blanco.|  
> |`\1`|Coincide con la subcadena que es igual al grupo denominado `\1`.|  
> |`\b`|Coincide con un límite de palabras.|  
  
 Se llama al método <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> con las opciones de expresiones regulares establecidas en <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType>. Por tanto, la operación de coincidencia no distingue mayúsculas de minúsculas y el ejemplo identifica la subcadena "Esto esto" como una duplicación.  
  
 La cadena de entrada incluye la subcadena "this? This". Sin embargo, debido al signo de puntuación intermedio, no se identifica como una duplicación.  
  
### <a name="example-3-dynamically-build-a-culture-sensitive-regular-expression"></a>Ejemplo 3: Compilación dinámica de una expresión regular de referencia cultural  

 En el ejemplo siguiente se muestra la eficacia de las expresiones regulares, además de la flexibilidad que ofrecen las características de globalización de .NET. Se usa el objeto <xref:System.Globalization.NumberFormatInfo> para determinar el formato de los valores de divisa en la referencia cultural actual del sistema. A continuación, se usa dicha información para construir dinámicamente una expresión regular que extrae los valores de divisa del texto. Para cada coincidencia, se extrae el subgrupo que solo contiene la cadena numérica, se convierte el subgrupo en un valor <xref:System.Decimal> y se calcula un total acumulativo.  
  
 [!code-csharp[Conceptual.Regex#1](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex/cs/example.cs#1)]
 [!code-vb[Conceptual.Regex#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex/vb/example.vb#1)]  
  
 En un equipo cuya referencia cultural actual sea Inglés - Estados Unidos (en-US), el ejemplo crea dinámicamente la expresión regular `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`. Este patrón de expresión regular se puede interpretar de la manera siguiente:  

> [!div class="mx-tdCol2BreakAll"]
> |Modelo|Interpretación|  
> |-|-|  
> |`\$`|Busque una sola aparición del símbolo de dólar (`$`) en la cadena de entrada. La cadena del patrón de expresión regular incluye una barra diagonal inversa para indicar que el símbolo de dólar debe interpretarse literalmente en lugar de interpretarse como un delimitador de la expresión regular. (Si solo apareciese el símbolo `$`, esto indicaría que el motor de expresión regular debe intentar comenzar su búsqueda de coincidencias al final de una cadena). Para asegurarse de que el símbolo de divisa de la referencia cultural actual no se interprete erróneamente como un símbolo de expresión regular, en el ejemplo se llama al método <xref:System.Text.RegularExpressions.Regex.Escape%2A?displayProperty=nameWithType> como escape de caracteres.|  
> |`\s*`|Buscar cero o más apariciones de un carácter de espacio en blanco.|  
> |`[-+]?`|Buscar cero o una aparición de un signo positivo o un signo negativo.|  
> |`([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`|Los paréntesis externos alrededor de esta expresión la definen como un grupo de captura o una subexpresión. Si se encuentra una coincidencia, la información sobre esta parte de la cadena coincidente se puede recuperar del segundo objeto <xref:System.Text.RegularExpressions.Group> en el objeto <xref:System.Text.RegularExpressions.GroupCollection> devuelto por la propiedad <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>. (El primer elemento de la colección representa la coincidencia completa.)|  
> |`[0-9]{0,3}`|Buscar de cero a tres apariciones de los dígitos decimales comprendidos entre 0 y 9.|  
> |`(,[0-9]{3})*`|Buscar cero o más apariciones de un separador de grupos seguido de tres dígitos decimales.|  
> |`\.`|Buscar una única aparición del separador decimal.|  
> |`[0-9]+`|Buscar uno o más dígitos decimales.|  
> |`(\.[0-9]+)?`|Buscar cero o una aparición del separador decimal seguido de al menos un dígito decimal.|  
  
 Si se encuentra cada uno de estos subpatrones en la cadena de entrada, la búsqueda de coincidencias se realiza correctamente y se agrega al objeto <xref:System.Text.RegularExpressions.Match> un objeto <xref:System.Text.RegularExpressions.MatchCollection> que contiene información sobre la coincidencia.  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Title|Descripción|  
|-----------|-----------------|  
|[Lenguaje de expresiones regulares: referencia rápida](regular-expression-language-quick-reference.md)|Ofrece información sobre el conjunto de caracteres, operadores y construcciones que se pueden utilizar para definir expresiones regulares.|  
|[Modelo de objetos de expresión regular](the-regular-expression-object-model.md)|Proporciona información y ejemplos de código que muestran cómo usar las clases de expresiones regulares.|  
|[Detalles del comportamiento de expresiones regulares](details-of-regular-expression-behavior.md)|Proporciona información sobre las funcionalidades y el comportamiento de las expresiones regulares de .NET.|
|[Usar expresiones regulares en Visual Studio](/visualstudio/ide/using-regular-expressions-in-visual-studio)||
  
## <a name="reference"></a>Referencia  

- <xref:System.Text.RegularExpressions?displayProperty=nameWithType>  
- <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>  
- [Expresiones regulares: referencia rápida (descarga en formato Word)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.docx)  
- [Expresiones regulares: referencia rápida (descarga en formato PDF)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.pdf)

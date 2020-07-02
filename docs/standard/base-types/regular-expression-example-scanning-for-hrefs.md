---
title: 'Ejemplo de expresiones regulares: Buscar etiquetas HREF'
description: Vea un ejemplo de expresiones regulares en .NET. En el ejemplo se busca una cadena de entrada y se muestran todos los valores href y sus ubicaciones.
ms.date: 06/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: fae2c15b-7adf-4b15-b118-58eb3906994f
ms.openlocfilehash: 7bcc2a4242bfaed3e3340347a30e97e7e4060794
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85802862"
---
# <a name="regular-expression-example-scanning-for-hrefs"></a>Ejemplo de expresiones regulares: Buscar etiquetas HREF
En el ejemplo siguiente se busca una cadena de entrada y se muestran todos los valores href="…" y sus ubicaciones en la cadena.  

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="the-regex-object"></a>El objeto Regex
 Dado que el método `DumpHRefs` puede llamarse varias veces desde el código de usuario, usa el método `static` (`Shared` en Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType>. Esto permite que el motor de expresiones regulares almacene en caché la expresión regular y evita la sobrecarga que se produciría al crear instancias de un nuevo objeto <xref:System.Text.RegularExpressions.Regex> cada vez que se llamara al método. Después, se usa un objeto <xref:System.Text.RegularExpressions.Match> para iterar todas las coincidencias de la cadena.  
  
 [!code-csharp[RegularExpressions.Examples.HREF#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#1)]
 [!code-vb[RegularExpressions.Examples.HREF#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#1)]  
  
 En el ejemplo siguiente se muestra la llamada al método `DumpHRefs`.  
  
 [!code-csharp[RegularExpressions.Examples.HREF#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#2)]
 [!code-vb[RegularExpressions.Examples.HREF#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#2)]  
  
 El patrón de la expresión regular `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` se interpreta como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`href`|Coincide con la cadena literal "href". La búsqueda no distingue entre mayúsculas y minúsculas.|  
|`\s*`|Busca coincidencias con cero o más caracteres de espacio en blanco.|  
|`=`|Coincide con el signo igual.|  
|`\s*`|Busca coincidencias con cero o más caracteres de espacio en blanco.|  
|`(?:\["'\](?<1>\[^"'\]*)["']|(?<1>\S+))`|Coincide con uno de los siguientes sin asignar el resultado a un grupo capturado:<br /> <ul><li><p>Una comilla o un apóstrofo, seguido de cero o más apariciones de cualquier carácter que no sea una comilla o un apóstrofo, seguido por una comilla o un apóstrofo. El grupo con nombre `1` se incluye en este patrón.</p></li><li><p>Uno o varios caracteres que no son espacios en blanco. El grupo con nombre `1` se incluye en este patrón.</p></li></ul>|  
|`(?<1>[^"']*)`|Asigna cero o más apariciones de cualquier carácter que no sea apóstrofo o comilla al grupo de captura con nombre `1`.|  
|`(?<1>\S+)`|Asigna uno o varios caracteres que no sean un espacio en blanco al grupo de captura con nombre `1`.|  
  
## <a name="match-result-class"></a>Clase de resultado Match  
 Los resultados de la búsqueda se almacenan en la clase <xref:System.Text.RegularExpressions.Match>, que proporciona acceso a todas las subcadenas extraídas por la búsqueda. También recuerda la cadena buscada y la expresión regular que se usa, por lo que puede llamar al método <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> para realizar otra búsqueda desde donde terminó la anterior.  
  
## <a name="explicitly-named-captures"></a>Capturas con nombre explícito  
 En las expresiones regulares tradicionales, los paréntesis de captura se numeran secuencialmente de forma automática. Esto origina dos problemas. En primer lugar, si se modifica una expresión regular al insertar o quitar un conjunto de paréntesis, se debe reescribir todo el código que hace referencia a las capturas numeradas para reflejar la nueva numeración. En segundo lugar, puesto que a menudo se usan diferentes conjuntos de paréntesis para proporcionar expresiones alternativas para una coincidencia aceptable, puede resultar difícil determinar cuál de las dos expresiones devolvió realmente un resultado.  
  
 Para abordar estos problemas, la clase <xref:System.Text.RegularExpressions.Regex> admite la sintaxis `(?<name>…)` para capturar una coincidencia en una ranura especificada (el nombre dado a la ranura puede ser una cadena o un entero; los enteros se pueden recuperar con más rapidez). Así, las coincidencias alternativas para la misma cadena se pueden dirigir todas al mismo lugar. En caso de conflicto, la última coincidencia situada en la ranura es la coincidencia correcta. (Pero está disponible una lista completa de varias coincidencias para una única ranura. Consulte la colección <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> para obtener más información).  
  
## <a name="see-also"></a>Vea también

- [Expresiones regulares de .NET](regular-expressions.md)

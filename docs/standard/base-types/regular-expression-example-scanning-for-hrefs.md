---
title: 'Ejemplo de expresiones regulares: Buscar etiquetas HREF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2bc9db7317c7a73f70a2cb83322b8b3a4c3771b9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-example-scanning-for-hrefs"></a>Ejemplo de expresiones regulares: Buscar etiquetas HREF
En el ejemplo siguiente se busca una cadena de entrada y se muestran todos los valores href="…" y sus ubicaciones en la cadena.  
  
## <a name="the-regex-object"></a>El objeto Regex  
 Dado que la `DumpHRefs` método puede llamarse varias veces desde el código de usuario, usa el `static` (`Shared` en Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> método. Esto permite que el motor de expresiones regulares para almacenar en caché la expresión regular y evita la sobrecarga de crear instancias de un nuevo <xref:System.Text.RegularExpressions.Regex> objeto cada vez que se llama al método. Un <xref:System.Text.RegularExpressions.Match> objeto, a continuación, se usa para recorrer en iteración todas las coincidencias en la cadena.  
  
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
|`(?:["'](?<1>[^"']*)"&#124;(?<1>\S+))`|Coincidir con uno de los siguientes valores sin asignar el resultado a un grupo capturado:<br /><br /> -Un signo de comillas o apóstrofo, seguido de cero o más apariciones de cualquier carácter que no sea una comilla o apóstrofo, seguido por un signo de comillas o apóstrofo. El grupo con nombre `1` se incluye en este patrón.<br />-Uno o varios caracteres de espacios en blanco. El grupo con nombre `1` se incluye en este patrón.|  
|`(?<1>[^"']*)`|Asigna cero o más apariciones de cualquier carácter que no sea apóstrofo o comilla al grupo de captura con nombre `1`.|  
|`"(?<1>\S+)`|Asigna uno o varios caracteres que no sean un espacio en blanco al grupo de captura con nombre `1`.|  
  
## <a name="match-result-class"></a>Clase de resultado Match  
 Los resultados de la búsqueda se almacenan en la <xref:System.Text.RegularExpressions.Match> (clase), que proporciona acceso a todas las subcadenas extraídas por la búsqueda. Esta clase recuerda también la cadena buscada y la expresión regular que se va a utilizar, por lo que puede llamar a la <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> método para realizar otra búsqueda, que comenzará donde finalizó la última de ellas.  
  
## <a name="explicitly-named-captures"></a>Capturas con nombre explícito  
 En las expresiones regulares tradicionales, los paréntesis de captura se numeran secuencialmente de forma automática. Esto origina dos problemas. En primer lugar, si se modifica una expresión regular al insertar o quitar un conjunto de paréntesis, se debe reescribir todo el código que hace referencia a las capturas numeradas para reflejar la nueva numeración. En segundo lugar, puesto que a menudo se usan diferentes conjuntos de paréntesis para proporcionar expresiones alternativas para una coincidencia aceptable, puede resultar difícil determinar cuál de las dos expresiones devolvió realmente un resultado.  
  
 Para resolver estos problemas, el <xref:System.Text.RegularExpressions.Regex> clase es compatible con la sintaxis `(?<name>…)` para capturar una coincidencia en una ranura especificada (un nombre a la ranura utilizando una cadena o un entero recordar enteros pueden recuperarse más rápidamente). Así, las coincidencias alternativas para la misma cadena se pueden dirigir todas al mismo lugar. En caso de conflicto, la última coincidencia situada en la ranura es la coincidencia correcta. (Pero está disponible una lista completa de varias coincidencias para una única ranura. Consulte la <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> colección para obtener más información.)  
  
## <a name="see-also"></a>Vea también  
 [Expresiones regulares de .NET](../../../docs/standard/base-types/regular-expressions.md)

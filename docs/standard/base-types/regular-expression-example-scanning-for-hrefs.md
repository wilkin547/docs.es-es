---
title: "Ejemplo de expresiones regulares: Buscar etiquetas HREF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "buscar con expresiones regulares, ejemplos"
  - "analizar texto con expresiones regulares, ejemplos"
  - "expresiones regulares, ejemplos"
  - "expresiones regulares de .NET Framework, ejemplos"
  - "expresiones regulares [.NET Framework], ejemplos"
  - "coincidencia de patrones con expresiones regulares, ejemplos"
ms.assetid: fae2c15b-7adf-4b15-b118-58eb3906994f
caps.latest.revision: 24
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 24
---
# Ejemplo de expresiones regulares: Buscar etiquetas HREF
El ejemplo siguiente busca una cadena de entrada y muestra todo el href\=”…” valores y sus posiciones en la cadena.  
  
## El objeto Regex  
 Puesto que el método `DumpHRefs` puede invocarse varias veces desde el código de usuario, se emplea el método `static` \(`Shared` en Visual Basic\) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=fullName>.  De este modo, el motor de expresiones regulares puede almacenar en memoria caché la expresión regular y evitar la sobrecarga que supone crear una instancia de un nuevo objeto <xref:System.Text.RegularExpressions.Regex> cada vez que se llama al método.  A continuación, se utiliza un objeto <xref:System.Text.RegularExpressions.Match> para recorrer en iteración todas las coincidencias de la cadena.  
  
 [!code-csharp[RegularExpressions.Examples.HREF#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#1)]
 [!code-vb[RegularExpressions.Examples.HREF#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#1)]  
  
 En el siguiente ejemplo se muestra una llamada al método `DumpHRefs`.  
  
 [!code-csharp[RegularExpressions.Examples.HREF#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#2)]
 [!code-vb[RegularExpressions.Examples.HREF#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#2)]  
  
 El patrón de expresión regular `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` se interpreta como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`href`|Busca coincidencias con la cadena literal "href".  La búsqueda no distingue entre mayúsculas y minúsculas.|  
|`\s*`|Busca coincidencias con cero o más caracteres de espacio en blanco.|  
|`=`|Busca coincidencias con el signo de igualdad.|  
|`\s*`|Busca coincidencias con cero o más caracteres de espacio en blanco.|  
|`(?:["'](?<1>[^"']*)"&#124;(?<1>\S+))`|Busca coincidencias con uno de los siguientes elementos sin asignar el resultado a un grupo capturado:<br /><br /> -   Una comilla o apóstrofo, seguido de cero o más apariciones de cualquier carácter que no sea una comilla o un apóstrofo, seguido por una comilla o un apóstrofo.  Este modelo incluye el grupo denominado `1`.<br />-   Uno o más caracteres que no sean un espacio en blanco.  Este modelo incluye el grupo denominado `1`.|  
|`(?<1>[^"']*)`|Asigna cero o más apariciones de cualquier carácter distinto de una comilla o un apóstrofo al grupo de captura denominado `1`.|  
|`"(?<1>\S+)`|Asigna uno o más caracteres que no sean un espacio en blanco al grupo de captura denominado `1`.|  
  
## Clase de resultados Match  
 Los resultados de una búsqueda se almacenan en la clase <xref:System.Text.RegularExpressions.Match>, que proporciona acceso a todas las subcadenas extraídas por la búsqueda.  Esta clase también recuerda la cadena buscada y la expresión regular utilizada, por lo que puede llamar al método <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=fullName> para realizar otra búsqueda, que comenzará donde terminó la última.  
  
## Capturas con nombre explícito  
 En las expresiones regulares tradicionales, los paréntesis de captura se numeran automáticamente de forma secuencial.  Esto implica dos problemas.  En primer lugar, si se modifica una expresión regular al insertar o quitar un grupo de paréntesis, todo el código que hace referencia a las capturas numeradas debe reescribirse para que la nueva numeración quede reflejada.  En segundo lugar, dado que a menudo se utilizan grupos de paréntesis distintos con el fin de proporcionar expresiones alternativas para la búsqueda de una coincidencia aceptable, puede resultar difícil determinar cual de las dos expresiones ha devuelto en realidad un resultado.  
  
 Para solucionar estos problemas, la clase <xref:System.Text.RegularExpressions.Regex> admite la sintaxis `(?<name>…)` para capturar una coincidencia en una ranura especificada \(puede asignarle un nombre a la ranura usando una cadena o un entero, aunque resulta más sencillo recordar enteros\).  De esta forma, todas las coincidencias alternativas de la misma cadena pueden dirigirse al mismo lugar.  En caso de conflicto, la última coincidencia situada en una ranura es la coincidencia correcta. Sin embargo, se puede disponer de una lista completa de varias coincidencias para una única ranura.  Vea la colección <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=fullName> para obtener información detallada.  
  
## Vea también  
 [Expresiones regulares de .NET Framework](../../../docs/standard/base-types/regular-expressions.md)
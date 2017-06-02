---
title: "Ejemplo de expresiones regulares: Cambiar formatos de fecha | Microsoft Docs"
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
ms.assetid: 5fcc75a5-09d7-45ae-a4c0-9ad6085ac83d
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Ejemplo de expresiones regulares: Cambiar formatos de fecha
El ejemplo de código siguiente se utiliza el método de <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=fullName> para reemplazar fechas con el formato *mm*\/*dd*\/*yy* por fechas con el formato *dd*\-*mm*\-*yy*.  
  
## Ejemplo  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#1)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#1)]  
  
 En el código siguiente se muestra cómo se puede llamar al método `MDYToDMY` en una aplicación.  
  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#2)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#2)]  
  
## Comentarios  
 El modelo de expresión regular `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` se interpreta tal y como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`\b`|Comienza la búsqueda de coincidencias en un límite de palabras.|  
|`(?<month>\d{1,2})`|Buscar coincidencias con uno o dos dígitos decimales.  Éste es el grupo capturado `month`.|  
|`/`|Buscar coincidencias con una barra diagonal.|  
|`(?<day>\d{1,2})`|Buscar coincidencias con uno o dos dígitos decimales.  Este es el grupo capturado `day`.|  
|`/`|Buscar coincidencias con una barra diagonal.|  
|`(?<year>\d{2,4})`|Busca coincidencias con dos a cuatro dígitos decimales.  Este es el grupo capturado `year`.|  
|`\b`|Finaliza la búsqueda de coincidencias en un límite de palabras.|  
  
 El modelo `${day}-${month}-${year}` define cómo se muestra la cadena de reemplazo en la siguiente tabla.  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`$(day)`|Agregar la cadena capturada por el grupo de captura `day`.|  
|`-`|Agregar un guión.|  
|`$(month)`|Agregar la cadena capturada por el grupo de captura `month`.|  
|`-`|Agregar un guión.|  
|`$(year)`|Agregar la cadena capturada por el grupo de captura `year`.|  
  
## Vea también  
 [Expresiones regulares de .NET Framework](../../../docs/standard/base-types/regular-expressions.md)
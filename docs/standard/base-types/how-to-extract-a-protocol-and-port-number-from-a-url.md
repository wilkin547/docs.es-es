---
title: "C&#243;mo: Extraer un protocolo y un n&#250;mero de puerto de una direcci&#243;n URL | Microsoft Docs"
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
  - "expresiones regulares de .NET Framework, ejemplos"
  - "analizar texto con expresiones regulares, ejemplos"
  - "coincidencia de patrones con expresiones regulares, ejemplos"
  - "expresiones regulares [.NET Framework], ejemplos"
  - "expresiones regulares, ejemplos"
  - "buscar con expresiones regulares, ejemplos"
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Extraer un protocolo y un n&#250;mero de puerto de una direcci&#243;n URL
En el ejemplo siguiente se extrae un protocolo y un número de puerto de una dirección URL.  
  
## Ejemplo  
 En el ejemplo se usa el método <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=fullName> para devolver el protocolo seguido por un signo de dos puntos y seguido a su vez por el número de puerto.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 El modelo de expresión regular `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` se puede interpretar como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`^`|Comenzar la búsqueda de coincidencia al principio de la cadena.|  
|`(?<proto>\w+)`|Coincide con uno o varios caracteres que se usan para formar palabras.  Denominar a este grupo `proto`.|  
|`://`|Buscar una coincidencia con un signo dos puntos seguido por dos barras diagonales.|  
|`[^/]+?`|Buscar una coincidencia con una o más apariciones \(pero las mínimas posibles\) de cualquier carácter distinto de una barra diagonal.|  
|`(?<port>:\d+)?`|Buscar una coincidencia con cero o una aparición de un signo de dos puntos seguida por uno o más caracteres de dígito.  Denominar a este grupo `port`.|  
|`/`|Buscar una coincidencia con una barra diagonal.|  
  
 El método <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=fullName> expande la secuencia de reemplazo `${proto}${port}`, que concatena el valor de los dos grupos con nombre capturados en el modelo de expresión regular.  Se trata de una alternativa adecuada a concatenar explícitamente las cadenas recuperadas del objeto de colección devueltas por la propiedad <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=fullName>.  
  
 En el ejemplo, se utiliza el método <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=fullName> con dos sustituciones, `${proto}` y `${port}`, para incluir los grupos capturados en la cadena de salida.  Los grupos capturados se pueden recuperar del objeto <xref:System.Text.RegularExpressions.GroupCollection> de la coincidencia, tal y como se muestra en el siguiente código.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## Vea también  
 [Expresiones regulares de .NET Framework](../../../docs/standard/base-types/regular-expressions.md)
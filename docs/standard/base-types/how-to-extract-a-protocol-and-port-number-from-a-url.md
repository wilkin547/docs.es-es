---
title: "Cómo: Extraer un protocolo y un número de puerto de una dirección URL"
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
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10ab05ac8b24c0658be2f27809137c6b0bd4834f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a>Cómo: Extraer un protocolo y un número de puerto de una dirección URL
En los siguientes ejemplos se extrae un protocolo y un número de puerto de una dirección URL.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo se utiliza la <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> método para devolver el protocolo seguido de dos puntos seguido del número de puerto.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 El patrón de la expresión regular `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` puede interpretarse como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`^`|Comenzar la búsqueda de coincidencia al principio de la cadena.|  
|`(?<proto>\w+)`|Buscar coincidencias con uno o más caracteres alfabéticos. Este grupo se denomina `proto`.|  
|`://`|Buscar coincidencias con un signo de dos puntos seguido por dos barras diagonales.|  
|`[^/]+?`|Buscar coincidencias con una o más apariciones (pero el menor número posible) de cualquier carácter que no sea una barra diagonal.|  
|`(?<port>:\d+)?`|Buscar una coincidencia con cero o una aparición de una coma seguida de uno o más caracteres decimales. Este grupo se denomina `port`.|  
|`/`|Buscar una coincidencia con una barra diagonal.|  
  
 El <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> método expande el `${proto}${port}` secuencia de reemplazo, que concatena el valor de los dos grupos con nombre capturados en el patrón de expresión regular. Es una alternativa cómoda a concatenar explícitamente las cadenas que se recuperan de la colección devuelta por la <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> propiedad.  
  
 El ejemplo se utiliza la <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> método con dos sustituciones, `${proto}` y `${port}`, para incluir los grupos capturados en la cadena de salida. Puede recuperar los grupos capturados de la búsqueda de coincidencias <xref:System.Text.RegularExpressions.GroupCollection> en su lugar, como se muestra en el siguiente código de objeto.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 [Expresiones regulares de .NET](../../../docs/standard/base-types/regular-expressions.md)

---
title: "Cómo: extraer un protocolo y un número de puerto de una dirección URL"
description: "Cómo extraer un protocolo y un número de puerto de una dirección URL"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: d2462fb4-6d61-44ab-8466-73f1f06c3058
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 72e0c9401406dcac4eb693b056b88a531f2a0748

---

# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a>Cómo: extraer un protocolo y un número de puerto de una dirección URL

En los siguientes ejemplos se extrae un protocolo y un número de puerto de una dirección URL. 

## <a name="example"></a>Ejemplo

El ejemplo usa el método [Match.Result](xref:System.Text.RegularExpressions.Match.Result(System.String)) para devolver el protocolo seguido de dos puntos y del número de puerto. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string url = "http://www.contoso.com:8080/letters/readme";

      Regex r = new Regex(@"^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/",
                          RegexOptions.None, TimeSpan.FromMilliseconds(150));
      Match m = r.Match(url);
      if (m.Success)
         Console.WriteLine(r.Match(url).Result("${proto}${port}")); 
   }
}
// The example displays the following output:
//       http:8080
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim url As String = "http://www.contoso.com:8080/letters/readme.html" 
      Dim r As New Regex("^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/",
                         RegexOptions.None, TimeSpan.FromMilliseconds(150))

      Dim m As Match = r.Match(url)
      If m.Success Then
         Console.WriteLine(r.Match(url).Result("${proto}${port}"))
      End If   
   End Sub
End Module
' The example displays the following output:
'       http:8080
```

El patrón de la expresión regular `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` puede interpretarse como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`^` | Comenzar la búsqueda de coincidencia al principio de la cadena.
`(?<proto>\w+)` | Buscar coincidencias con uno o más caracteres alfabéticos. Poner nombre al proto de este grupo.
`://` | Buscar coincidencias con un signo de dos puntos seguido por dos barras diagonales.
`[^/]+?` | Buscar coincidencias con una o más apariciones (pero el menor número posible) de cualquier carácter que no sea una barra diagonal.
`(?<port>:\d+)?` | Buscar una coincidencia con cero o una aparición de una coma seguida de uno o más caracteres decimales. Poner nombre al puerto de este grupo.
`/` | Buscar una coincidencia con una barra diagonal.
 
El método [Match.Result](xref:System.Text.RegularExpressions.Match.Result(System.String)) expande la secuencia de reemplazo `${proto}${port}`, que concatena el valor de los dos grupos con nombre capturados en el patrón de expresión regular. Resulta cómodo concatenar explícitamente las cadenas recuperadas del objeto de la colección devueltas por la propiedad [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups).

El ejemplo usa el método [Match.Result](xref:System.Text.RegularExpressions.Match.Result(System.String)) con dos sustituciones, `${proto}` y `${port}`, para incluir los grupos capturados en la cadena de salida. En su lugar, puede recuperar los grupos capturados del objeto de coincidencia [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection), como se muestra en el siguiente código.

```csharp
Console.WriteLine(m.Groups["proto"].Value + m.Groups["port"].Value); 
```

```vb
Console.WriteLine(m.Groups("proto").Value + m.Groups("port").Value)
```

## <a name="see-also"></a>Vea también

[Expresiones regulares de .NET](regular-expressions.md)

[Ejemplos de expresiones regulares](regex-examples.md)



<!--HONumber=Nov16_HO3-->



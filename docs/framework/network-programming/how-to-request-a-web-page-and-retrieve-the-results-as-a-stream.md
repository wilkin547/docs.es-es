---
title: 'Cómo: solicitar una página web y recuperar los resultados como una secuencia'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2ceaa7cbaf2035276a0ba0105f3969f0249c6132
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2018
ms.locfileid: "47402609"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a>Cómo: solicitar una página web y recuperar los resultados como una secuencia
En este ejemplo se muestra cómo solicitar una página web y recuperar los resultados en una secuencia.  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
WebClient myClient = new WebClient();  
Stream response = myClient.OpenRead("http://www.contoso.com/index.htm");  
// The stream data is used here.  
response.Close();  
```  
  
```vb  
Dim myClient As WebClient = New WebClient()  
Dim response As Stream = myClient.OpenRead("http://www.contoso.com/index.htm")  
' The stream data is used here.  
response.Close()  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los espacios de nombres <xref:System.IO> y <xref:System.Net>.  
  
## <a name="see-also"></a>Vea también  
 [Solicitud de datos](../../../docs/framework/network-programming/requesting-data.md)

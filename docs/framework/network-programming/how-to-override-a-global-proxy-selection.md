---
title: Procedimiento para reemplazar una selección del proxy global
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 6973503f12e0e60ee139c5cd7da09ab319d70218
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592129"
---
# <a name="how-to-override-a-global-proxy-selection"></a>Procedimiento para reemplazar una selección del proxy global
Este ejemplo envía una **WebRequest** a `www.contoso.com` que reemplaza la selección global de proxy con un servidor proxy denominado `alternateproxy` en el puerto 80.  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una [directiva `using`](~/docs/csharp/language-reference/keywords/using-directive.md) para el espacio de nombres **System.Net**.  
  
## <a name="see-also"></a>Vea también
- [Usar protocolos de aplicaciones](../../../docs/framework/network-programming/using-application-protocols.md)
- [Acceso a Internet a través de un proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)

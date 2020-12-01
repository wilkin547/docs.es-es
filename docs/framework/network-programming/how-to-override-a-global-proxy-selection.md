---
title: Procedimiento para reemplazar una selección del proxy global
description: Siga este ejemplo para invalidar la selección de proxy global mediante el envío de una solicitud WebRequest a una dirección URL, lo que invalida la selección con un servidor proxy.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 8931cdc471b957447277c333ba482a0cec0e6aa5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265744"
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
  
- Una [directiva `using`](../../csharp/language-reference/keywords/using-directive.md) para el espacio de nombres **System.Net**.  
  
## <a name="see-also"></a>Vea también

- [Usar protocolos de aplicaciones](using-application-protocols.md)
- [Acceso a Internet a través de un proxy](accessing-the-internet-through-a-proxy.md)

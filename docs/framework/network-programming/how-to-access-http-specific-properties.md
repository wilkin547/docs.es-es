---
description: 'Más información acerca de: Procedimiento: para acceder a propiedades específicas de HTTP'
title: 'Cómo: obtener acceso a propiedades específicas de HTTP'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8848c7e-f5c5-4d42-b86d-9951ff8f4146
ms.openlocfilehash: a54ef247b479cf6cdec8dc28732304cf03b0b202
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729307"
---
# <a name="how-to-access-http-specific-properties"></a>Procedimiento para acceder a propiedades específicas de HTTP

En este ejemplo se muestra cómo desactivar el comportamiento de **conexión persistente** HTTP y obtener el número de versión del protocolo de servidor web.  
  
## <a name="example"></a>Ejemplo  
  
```vb  
Dim HttpWReq As HttpWebRequest= _  
    CType(WebRequest.Create("http://www.contoso.com"), HttpWebRequest)  
' Turn off connection keep-alives.  
HttpWReq.KeepAlive = False  
  
Dim HttpWResp As HttpWebResponse = _  
    CType(HttpWReq.GetResponse(), HttpWebResponse)  
  
' Get the HTTP protocol version number returned by the server.  
Dim ver As String = HttpWResp.ProtocolVersion.ToString()  
HttpWResp.Close()  
```  
  
```csharp  
HttpWebRequest HttpWReq =
    (HttpWebRequest)WebRequest.Create("http://www.contoso.com");  
// Turn off connection keep-alives.  
HttpWReq.KeepAlive = false;  
  
HttpWebResponse HttpWResp = (HttpWebResponse)HttpWReq.GetResponse();  
  
// Get the HTTP protocol version number returned by the server.  
String ver = HttpWResp.ProtocolVersion.ToString();  
HttpWResp.Close();  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  

 Para este ejemplo se necesita:  
  
- Referencias al espacio de nombres **System.Net**.  
  
## <a name="see-also"></a>Vea también

- [Acceso a Internet a través de un proxy](accessing-the-internet-through-a-proxy.md)
- [Usar protocolos de aplicaciones](using-application-protocols.md)
- [HTTP](http.md)

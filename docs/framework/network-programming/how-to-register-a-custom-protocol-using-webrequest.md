---
title: 'Cómo: registrar un protocolo personalizado mediante WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e6902adeac04d95d576ae72469624a5b4f8aa0c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a>Cómo: registrar un protocolo personalizado mediante WebRequest
En este ejemplo se muestra cómo registrar una clase específica del protocolo que se define en otro lugar. En este ejemplo, `CustomWebRequestCreator` es el objeto implementado por el usuario que implementa el método **Create** que devuelve el objeto `CustomWebRequest`. El ejemplo del código presupone que ha escrito el código `CustomWebRequest` que implementa el protocolo personalizado.  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
 Referencias al espacio de nombres <xref:System.Net>.  
  
## <a name="see-also"></a>Vea también  
 [Programming Pluggable Protocols (Programar protocolos acoplables)](../../../docs/framework/network-programming/programming-pluggable-protocols.md)

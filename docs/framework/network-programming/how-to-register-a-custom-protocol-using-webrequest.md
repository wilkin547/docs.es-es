---
description: 'Más información acerca de: Procedimiento: para registrar un protocolo personalizado mediante WebRequest'
title: 'Cómo: registrar un protocolo personalizado mediante WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: 7415017f20c0c6ed80570992e249fb8121907de2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785762"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a>Procedimiento para registrar un protocolo personalizado mediante WebRequest

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

- [Programming Pluggable Protocols (Programar protocolos acoplables)](programming-pluggable-protocols.md)

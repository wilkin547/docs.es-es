---
title: Administrar conexiones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, connections
- HTTP, classes for connecting
- requesting data from Internet, connections
- sending data, connections
- receiving data, connections
- ServicePoint class, about ServicePoint class
- response to Internet request, connections
- connections [.NET Framework], classes
- network resources, connections
- downloading Internet resources, connections
- ServicePointManager class, about ServicePointManager class
ms.assetid: 9b3d3de7-189f-4f7d-81ae-9c29c441aaaa
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f3a8900aca9ebfa14fbf49d4d3634bc486793c0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="managing-connections"></a>Administrar conexiones
Las aplicaciones que usan HTTP para conectarse a los recursos de datos pueden usar las clases <xref:System.Net.ServicePoint> y <xref:System.Net.ServicePointManager> de .NET Framework para administrar las conexiones a Internet y lograr una escala y un rendimiento óptimos.  
  
 La clase **ServicePoint** proporciona una aplicación con un punto de conexión al que la aplicación puede conectarse para tener acceso a recursos de Internet. Cada **ServicePoint** contiene información que ayuda a optimizar las conexiones con un servidor de Internet mediante el uso compartido de información de optimización entre las conexiones para mejorar el rendimiento.  
  
 Cada **ServicePoint** se identifica mediante un identificador uniforme de recursos (URI) y se clasifica por categorías según el identificador de esquema y los fragmentos de host del URI. Por ejemplo, la propia instancia **ServicePoint** proporcionaría solicitudes a las direcciones http://www.contoso.com/index.htm y http://www.contoso.com/news.htm?date=today del URI, ya que tienen el mismo identificador de esquema (http) y fragmentos de host (www.contoso.com). Si la aplicación ya tiene una conexión persistente con el servidor www.contoso.com, usa esa conexión para recuperar ambas solicitudes, con lo que evita la necesidad de crear dos conexiones.  
  
 **ServicePointManager** es una clase estática que administra la creación y la destrucción de instancias **ServicePoint**. **ServicePointManager** crea una instancia **ServicePoint** cuando la aplicación solicita un recurso de Internet que no se encuentra en la colección de las instancias **ServicePoint** existentes. Las instancias **ServicePoint** se destruyen cuando han superado su tiempo de inactividad máximo o cuando el número de instancias **ServicePoint** existentes supera el número máximo de instancias **ServicePoint** para la aplicación. Para controlar el tiempo de inactividad máximo predeterminado y el número máximo de instancias **ServicePoint**, establezca las propiedades <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> y <xref:System.Net.ServicePointManager.MaxServicePoints%2A> en **ServicePointManager**.  
  
 El número de conexiones entre un cliente y un servidor puede afectar considerablemente al rendimiento de la aplicación. De forma predeterminada, una aplicación que usa la clase <xref:System.Net.HttpWebRequest> emplea un máximo de dos conexiones persistentes con un servidor determinado, pero es posible establecer el número máximo de conexiones según la aplicación.  
  
> [!NOTE]
>  La especificación HTTP/1.1 limita el número de conexiones desde una aplicación a dos conexiones por servidor.  
  
 El número óptimo de conexiones depende de las condiciones reales en las que se ejecuta la aplicación. Si aumenta el número de conexiones disponibles para la aplicación, el rendimiento de la aplicación podría no verse afectado. Para determinar el impacto de más conexiones, ejecute pruebas de rendimiento al variar el número de conexiones. Puede cambiar el número de conexiones que usa una aplicación. Para ello, cambie la propiedad estática <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> en la clase **ServicePointManager** durante la inicialización de la aplicación, como se muestra en el ejemplo de código siguiente.  
  
```csharp  
// Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4;  
```  
  
```vb  
' Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4  
```  
  
 El hecho de cambiar la propiedad **ServicePointManager.DefaultConnectionLimit** no afecta a las instancias **ServicePoint** ya inicializadas. En el código siguiente se muestra cómo cambiar el límite de conexiones en una instancia **ServicePoint** existente para el servidor http://www.contoso.com al valor almacenado en `newLimit`.  
  
```csharp  
Uri uri = new Uri("http://www.contoso.com/");  
ServicePoint sp = ServicePointManager.FindServicePoint(uri);  
sp.ConnectionLimit = newLimit;  
```  
  
```vb  
Dim uri As New Uri("http://www.contoso.com/")  
Dim sp As ServicePoint = ServicePointManager.FindServicePoint(uri)  
sp.ConnectionLimit = newLimit  
```  
  
## <a name="see-also"></a>Vea también  
 [Agrupación de conexiones](../../../docs/framework/network-programming/connection-grouping.md)  
 [Usar protocolos de aplicaciones](../../../docs/framework/network-programming/using-application-protocols.md)

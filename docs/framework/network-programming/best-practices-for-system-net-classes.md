---
title: Procedimientos recomendados para las clases System.Net
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sending data, best practices
- requesting data from Internet, best practices
- WebRequest class, best practices
- data requests, best practices
- WebResponse class, best practices
- best practices, data requests
- receiving data, best practices
ms.assetid: 716decc6-5952-47b7-9c5a-ba6fc5698684
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e50df22f66d4d55298aad5f3cc501dfb39ffcd9a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="best-practices-for-systemnet-classes"></a>Procedimientos recomendados para las clases System.Net
Las siguientes recomendaciones le ayudarán a usar las clases incluidas en <xref:System.Net> para su beneficio:  
  
-   Use <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> siempre que sea posible en lugar de la conversión de tipos en clases descendientes. Las aplicaciones que usan **WebRequest** y **WebResponse** pueden aprovechar los nuevos protocolos de Internet sin necesidad de grandes cambios de código.  
  
-   Al escribir aplicaciones ASP.NET que se ejecutan en un servidor mediante las clases **System.Net**, a menudo es mejor, desde la perspectiva del rendimiento, usar los métodos asincrónicos de <xref:System.Net.WebRequest.GetResponse%2A> y <xref:System.Net.WebResponse.GetResponseStream%2A>.  
  
-   El número de conexiones abiertas a un recurso de Internet puede tener un impacto considerable en el rendimiento de red. **System.Net** usa dos conexiones por aplicación y por host de forma predeterminada. El establecimiento de la propiedad <xref:System.Net.ServicePoint.ConnectionLimit%2A> en el <xref:System.Net.ServicePoint> de la aplicación puede aumentar este número para un host determinado. El establecimiento de la propiedad <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=nameWithType> puede aumentar este valor predeterminado para todos los hosts.  
  
-   Cuando escriba protocolos de nivel de socket, procure usar <xref:System.Net.Sockets.TcpClient> o <xref:System.Net.Sockets.UdpClient> siempre que sea posible en lugar de escribir directamente en un <xref:System.Net.Sockets.Socket>. Estas dos clases de cliente encapsulan la creación de sockets TCP y UDP sin que sea necesario controlar los detalles de la conexión.  
  
-   Al acceder a sitios que requieren credenciales, use la clase <xref:System.Net.CredentialCache> para crear una memoria caché de credenciales en lugar de proporcionarlas con cada solicitud. La clase **CredentialCache** busca en la memoria caché para encontrar la credencial adecuada que debe presentar con una solicitud, lo cual elimina la responsabilidad de crear y presentar credenciales según la dirección URL.  
  
## <a name="see-also"></a>Vea también  
 [Programación para redes en .NET Framework](../../../docs/framework/network-programming/index.md)

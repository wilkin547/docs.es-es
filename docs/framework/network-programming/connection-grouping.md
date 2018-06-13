---
title: Agrupación de conexiones
ms.date: 03/30/2017
helpviewer_keywords:
- Internet, connections
- connections [.NET Framework], grouping
- WebRequest class, connection grouping
- network resources, connections
- connection pooling
ms.assetid: 2ec502e8-4ba0-4c22-9410-f28eaf4eee63
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bbf34f1e653e95ea30a3e9945fc74c99cfdc3a45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395052"
---
# <a name="connection-grouping"></a>Agrupación de conexiones
La agrupación de conexiones asocia solicitudes específicas de una aplicación individual a un grupo de conexiones definido. Esto puede ser exigido por una aplicación de nivel intermedio que se conecta a un servidor back-end en nombre de un usuario y usa un protocolo de autenticación que admite la delegación, como Kerberos, o por una aplicación de nivel medio que proporciona sus propias credenciales, como en el ejemplo siguiente. Por ejemplo, imagine que un usuario, Juan, visita un sitio web interno que muestra información de su nómina. Después de autenticar a Juan, el servidor de aplicación de nivel intermedio usa las credenciales de Juan para conectarse al servidor back-end a fin de recuperar la información de su nómina. Luego Susana visita el sitio y solicita información de su nómina. Dado que la aplicación de nivel intermedio ya ha realizado una conexión con las credenciales de Juan, el servidor back-end responde con la información de Juan. Pero si la aplicación asigna cada solicitud enviada al servidor back-end a un grupo de conexiones formado a partir del nombre de usuario, cada usuario pertenece a un grupo de conexiones independiente y no puede compartir accidentalmente la información de autenticación con otro usuario.  
  
 Para asignar una solicitud a un grupo de conexiones concreto, debe asignar un nombre a la propiedad <xref:System.Net.WebRequest.ConnectionGroupName%2A> de <xref:System.Net.WebRequest> antes de realizar la solicitud.  
  
## <a name="see-also"></a>Vea también  
 [Administración de conexiones](../../../docs/framework/network-programming/managing-connections.md)  
 [Cómo: asignar la información de usuario para agrupar conexiones](../../../docs/framework/network-programming/how-to-assign-user-information-to-group-connections.md)

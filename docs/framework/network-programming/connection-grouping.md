---
description: 'Más información acerca de: Agrupación de conexiones'
title: Agrupación de conexiones
ms.date: 03/30/2017
helpviewer_keywords:
- Internet, connections
- connections [.NET Framework], grouping
- WebRequest class, connection grouping
- network resources, connections
- connection pooling
ms.assetid: 2ec502e8-4ba0-4c22-9410-f28eaf4eee63
ms.openlocfilehash: 08e917b555da918ad4386a77938aeb57bc4e4ced
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791574"
---
# <a name="connection-grouping"></a>Agrupación de conexiones

La agrupación de conexiones asocia solicitudes específicas de una aplicación individual a un grupo de conexiones definido. Esto puede ser exigido por una aplicación de nivel intermedio que se conecta a un servidor back-end en nombre de un usuario y usa un protocolo de autenticación que admite la delegación, como Kerberos, o por una aplicación de nivel medio que proporciona sus propias credenciales, como en el ejemplo siguiente. Por ejemplo, imagine que un usuario, Juan, visita un sitio web interno que muestra información de su nómina. Después de autenticar a Juan, el servidor de aplicación de nivel intermedio usa las credenciales de Juan para conectarse al servidor back-end a fin de recuperar la información de su nómina. Luego Susana visita el sitio y solicita información de su nómina. Dado que la aplicación de nivel intermedio ya ha realizado una conexión con las credenciales de Juan, el servidor back-end responde con la información de Juan. Pero si la aplicación asigna cada solicitud enviada al servidor back-end a un grupo de conexiones formado a partir del nombre de usuario, cada usuario pertenece a un grupo de conexiones independiente y no puede compartir accidentalmente la información de autenticación con otro usuario.  
  
 Para asignar una solicitud a un grupo de conexiones concreto, debe asignar un nombre a la propiedad <xref:System.Net.WebRequest.ConnectionGroupName%2A> de <xref:System.Net.WebRequest> antes de realizar la solicitud.  
  
## <a name="see-also"></a>Vea también

- [Administrar conexiones](managing-connections.md)
- [Cómo: Asignar la información de usuario para agrupar conexiones](how-to-assign-user-information-to-group-connections.md)

---
description: Más información sobre cómo convertir una aplicación NetTcpBinding en una aplicación de canal del mismo nivel
title: Conversión de una aplicación NetTcpBinding en una aplicación de canal del mismo nivel
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: 828ffce38fb05acff851c9fe5a6fbb38fffad6aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780419"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a>Conversión de una aplicación NetTcpBinding en una aplicación de canal del mismo nivel

Puede crear conexiones entre clientes mediante WinFX mediante el uso de enlaces que describen los parámetros de la conexión. La conversión de una aplicación .NET Framework para usar conexiones punto a punto requiere un enlace que admita esta tecnología al establecer conexiones de cliente. El canal del mismo nivel proporciona un enlace denominado <xref:System.ServiceModel.NetPeerTcpBinding> que puede usar de una manera similar a <xref:System.ServiceModel.NetTcpBinding>. Las diferencias de clave son especificar un servicio de resolución y definir la configuración de seguridad.  
  
 Si una aplicación usa la resolución y configuración de seguridad predeterminadas, convertir una aplicación normal basada en cliente-servidor para que use el canal del mismo nivel supone cambiar el nombre del enlace de "NetTcpBinding" a "NetPeerTcpBinding" en el archivo de configuración de la aplicación. No tiene que cambiar la base del código de aplicación.  
  
## <a name="see-also"></a>Vea también

- [Creación de una aplicación de canal del mismo nivel](building-a-peer-channel-application.md)
- [Enlaces proporcionados por el sistema](../system-provided-bindings.md)

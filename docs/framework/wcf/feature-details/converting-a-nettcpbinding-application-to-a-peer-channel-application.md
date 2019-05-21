---
title: Conversión de una aplicación NetTcpBinding en una aplicación de canal del mismo nivel
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: 362945959a781fac360c42475148fee1e47a1183
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960128"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a>Conversión de una aplicación NetTcpBinding en una aplicación de canal del mismo nivel
Puede crear conexiones entre los clientes que usan el WinFX mediante el uso de enlaces que describen los parámetros de la conexión. Conversión de una aplicación de .NET Framework para utilizar conexiones de punto a punto, requiere un enlace que admita esta tecnología cuando se realizan las conexiones de cliente. El canal del mismo nivel proporciona un enlace denominado <xref:System.ServiceModel.NetPeerTcpBinding> que puede usar de una manera similar a <xref:System.ServiceModel.NetTcpBinding>. Las diferencias de clave son especificar un servicio de resolución y definir la configuración de seguridad.  
  
 Si una aplicación usa la resolución y configuración de seguridad predeterminadas, convertir una aplicación normal basada en cliente-servidor para que use el canal del mismo nivel supone cambiar el nombre del enlace de "NetTcpBinding" a "NetPeerTcpBinding" en el archivo de configuración de la aplicación. No tiene que cambiar la base del código de aplicación.  
  
## <a name="see-also"></a>Vea también

- [Creación de una aplicación de canal del mismo nivel](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
- [Enlaces proporcionados por el sistema](../../../../docs/framework/wcf/system-provided-bindings.md)

---
title: Conversión de una aplicación NetTcpBinding en una aplicación de canal del mismo nivel
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: 42266d8c7c04e2d8f3f1e4734d9a05181c3f1ea3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595562"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a>Conversión de una aplicación NetTcpBinding en una aplicación de canal del mismo nivel
Puede crear conexiones entre clientes mediante WinFX mediante el uso de enlaces que describen los parámetros de la conexión. La conversión de una aplicación .NET Framework para usar conexiones punto a punto requiere un enlace que admita esta tecnología al establecer conexiones de cliente. El canal del mismo nivel proporciona un enlace denominado <xref:System.ServiceModel.NetPeerTcpBinding> que puede usar de una manera similar a <xref:System.ServiceModel.NetTcpBinding>. Las diferencias de clave son especificar un servicio de resolución y definir la configuración de seguridad.  
  
 Si una aplicación usa la resolución y configuración de seguridad predeterminadas, convertir una aplicación normal basada en cliente-servidor para que use el canal del mismo nivel supone cambiar el nombre del enlace de "NetTcpBinding" a "NetPeerTcpBinding" en el archivo de configuración de la aplicación. No tiene que cambiar la base del código de aplicación.  
  
## <a name="see-also"></a>Vea también

- [Creación de una aplicación de canal del mismo nivel](building-a-peer-channel-application.md)
- [Enlaces proporcionados por el sistema](../system-provided-bindings.md)

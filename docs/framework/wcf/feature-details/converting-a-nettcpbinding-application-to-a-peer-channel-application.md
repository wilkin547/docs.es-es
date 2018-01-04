---
title: "Conversión de una aplicación NetTcpBinding en una aplicación de canal del mismo nivel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ee46e34aea14c4ee9ce23c807170104173f2704
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a>Conversión de una aplicación NetTcpBinding en una aplicación de canal del mismo nivel
Puede crear conexiones entre clientes mediante [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] con enlaces que describen los parámetros de la conexión. Convertir una aplicación [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para utilizar las conexiones punto a punto requiere un enlace que admita esta tecnología cuando se realicen las conexiones de clientes. El canal del mismo nivel proporciona un enlace denominado <xref:System.ServiceModel.NetPeerTcpBinding> que puede usar de una manera similar a <xref:System.ServiceModel.NetTcpBinding>. Las diferencias de clave son especificar un servicio de resolución y definir la configuración de seguridad.  
  
 Si una aplicación usa la resolución y configuración de seguridad predeterminadas, convertir una aplicación normal basada en cliente-servidor para que use el canal del mismo nivel supone cambiar el nombre del enlace de "NetTcpBinding" a "NetPeerTcpBinding" en el archivo de configuración de la aplicación. No tiene que cambiar la base del código de aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Creación de una aplicación de canal del mismo nivel](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)  
 [Enlaces proporcionados por el sistema](../../../../docs/framework/wcf/system-provided-bindings.md)

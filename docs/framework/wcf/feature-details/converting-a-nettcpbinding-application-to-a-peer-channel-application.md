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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 532171dfeba965ae30dc92f31448cf38964fc695
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a><span data-ttu-id="94912-102">Conversión de una aplicación NetTcpBinding en una aplicación de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="94912-102">Converting a NetTcpBinding Application to a Peer Channel Application</span></span>
<span data-ttu-id="94912-103">Puede crear conexiones entre clientes mediante [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] con enlaces que describen los parámetros de la conexión.</span><span class="sxs-lookup"><span data-stu-id="94912-103">You can create connections between clients using the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] by using bindings that describe the parameters of the connection.</span></span> <span data-ttu-id="94912-104">Convertir una aplicación [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para utilizar las conexiones punto a punto requiere un enlace que admita esta tecnología cuando se realicen las conexiones de clientes.</span><span class="sxs-lookup"><span data-stu-id="94912-104">Converting a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] application to use peer-to-peer connections requires a binding that supports this technology when making client connections.</span></span> <span data-ttu-id="94912-105">El canal del mismo nivel proporciona un enlace denominado <xref:System.ServiceModel.NetPeerTcpBinding> que puede usar de una manera similar a <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="94912-105">Peer Channel provides a binding called <xref:System.ServiceModel.NetPeerTcpBinding>, which you can use in a similar way to the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="94912-106">Las diferencias de clave son especificar un servicio de resolución y definir la configuración de seguridad.</span><span class="sxs-lookup"><span data-stu-id="94912-106">Key differences include specifying a resolver service and defining security settings.</span></span>  
  
 <span data-ttu-id="94912-107">Si una aplicación usa la resolución y configuración de seguridad predeterminadas, convertir una aplicación normal basada en cliente-servidor para que use el canal del mismo nivel supone cambiar el nombre del enlace de "NetTcpBinding" a "NetPeerTcpBinding" en el archivo de configuración de la aplicación. No tiene que cambiar la base del código de aplicación.</span><span class="sxs-lookup"><span data-stu-id="94912-107">If an application is using the default resolver and security settings, converting a normal client/server-based application to use Peer Channel entails changing the name of the binding from "NetTcpBinding" to "NetPeerTcpBinding" in the application’s configuration file—you do not have to change the application code base.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94912-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="94912-108">See Also</span></span>  
 [<span data-ttu-id="94912-109">Creación de una aplicación de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="94912-109">Building a Peer Channel Application</span></span>](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)  
 [<span data-ttu-id="94912-110">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="94912-110">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)

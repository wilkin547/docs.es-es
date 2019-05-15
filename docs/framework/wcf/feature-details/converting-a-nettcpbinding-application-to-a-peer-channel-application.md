---
title: Conversión de una aplicación NetTcpBinding en una aplicación de canal del mismo nivel
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: b89afbe59b73288ba357fa55ec5d55c1fb18352b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582790"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a><span data-ttu-id="e913e-102">Conversión de una aplicación NetTcpBinding en una aplicación de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="e913e-102">Converting a NetTcpBinding Application to a Peer Channel Application</span></span>
<span data-ttu-id="e913e-103">Puede crear conexiones entre clientes mediante [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] con enlaces que describen los parámetros de la conexión.</span><span class="sxs-lookup"><span data-stu-id="e913e-103">You can create connections between clients using the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] by using bindings that describe the parameters of the connection.</span></span> <span data-ttu-id="e913e-104">Conversión de una aplicación de .NET Framework para utilizar conexiones de punto a punto, requiere un enlace que admita esta tecnología cuando se realizan las conexiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="e913e-104">Converting a .NET Framework application to use peer-to-peer connections requires a binding that supports this technology when making client connections.</span></span> <span data-ttu-id="e913e-105">El canal del mismo nivel proporciona un enlace denominado <xref:System.ServiceModel.NetPeerTcpBinding> que puede usar de una manera similar a <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="e913e-105">Peer Channel provides a binding called <xref:System.ServiceModel.NetPeerTcpBinding>, which you can use in a similar way to the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="e913e-106">Las diferencias de clave son especificar un servicio de resolución y definir la configuración de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e913e-106">Key differences include specifying a resolver service and defining security settings.</span></span>  
  
 <span data-ttu-id="e913e-107">Si una aplicación usa la resolución y configuración de seguridad predeterminadas, convertir una aplicación normal basada en cliente-servidor para que use el canal del mismo nivel supone cambiar el nombre del enlace de "NetTcpBinding" a "NetPeerTcpBinding" en el archivo de configuración de la aplicación. No tiene que cambiar la base del código de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e913e-107">If an application is using the default resolver and security settings, converting a normal client/server-based application to use Peer Channel entails changing the name of the binding from "NetTcpBinding" to "NetPeerTcpBinding" in the application’s configuration file—you do not have to change the application code base.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e913e-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="e913e-108">See also</span></span>

- [<span data-ttu-id="e913e-109">Creación de una aplicación de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="e913e-109">Building a Peer Channel Application</span></span>](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
- [<span data-ttu-id="e913e-110">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="e913e-110">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)

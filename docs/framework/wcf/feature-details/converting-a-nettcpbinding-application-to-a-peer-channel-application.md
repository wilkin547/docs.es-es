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
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a><span data-ttu-id="27a45-103">Conversión de una aplicación NetTcpBinding en una aplicación de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="27a45-103">Converting a NetTcpBinding Application to a Peer Channel Application</span></span>

<span data-ttu-id="27a45-104">Puede crear conexiones entre clientes mediante WinFX mediante el uso de enlaces que describen los parámetros de la conexión.</span><span class="sxs-lookup"><span data-stu-id="27a45-104">You can create connections between clients using the WinFX by using bindings that describe the parameters of the connection.</span></span> <span data-ttu-id="27a45-105">La conversión de una aplicación .NET Framework para usar conexiones punto a punto requiere un enlace que admita esta tecnología al establecer conexiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="27a45-105">Converting a .NET Framework application to use peer-to-peer connections requires a binding that supports this technology when making client connections.</span></span> <span data-ttu-id="27a45-106">El canal del mismo nivel proporciona un enlace denominado <xref:System.ServiceModel.NetPeerTcpBinding> que puede usar de una manera similar a <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="27a45-106">Peer Channel provides a binding called <xref:System.ServiceModel.NetPeerTcpBinding>, which you can use in a similar way to the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="27a45-107">Las diferencias de clave son especificar un servicio de resolución y definir la configuración de seguridad.</span><span class="sxs-lookup"><span data-stu-id="27a45-107">Key differences include specifying a resolver service and defining security settings.</span></span>  
  
 <span data-ttu-id="27a45-108">Si una aplicación usa la resolución y configuración de seguridad predeterminadas, convertir una aplicación normal basada en cliente-servidor para que use el canal del mismo nivel supone cambiar el nombre del enlace de "NetTcpBinding" a "NetPeerTcpBinding" en el archivo de configuración de la aplicación. No tiene que cambiar la base del código de aplicación.</span><span class="sxs-lookup"><span data-stu-id="27a45-108">If an application is using the default resolver and security settings, converting a normal client/server-based application to use Peer Channel entails changing the name of the binding from "NetTcpBinding" to "NetPeerTcpBinding" in the application’s configuration file—you do not have to change the application code base.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27a45-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="27a45-109">See also</span></span>

- [<span data-ttu-id="27a45-110">Creación de una aplicación de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="27a45-110">Building a Peer Channel Application</span></span>](building-a-peer-channel-application.md)
- [<span data-ttu-id="27a45-111">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="27a45-111">System-Provided Bindings</span></span>](../system-provided-bindings.md)

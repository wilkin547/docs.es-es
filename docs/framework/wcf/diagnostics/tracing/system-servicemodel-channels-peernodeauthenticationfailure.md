---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b09d7fc476d5eed7f7c534fdde46cb18eeac30d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a><span data-ttu-id="d81b8-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span><span class="sxs-lookup"><span data-stu-id="d81b8-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span></span>
<span data-ttu-id="d81b8-103">El protocolo de enlace de seguridad con un vecino potencial no tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="d81b8-103">The security handshake with a potential neighbor was not successful.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d81b8-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="d81b8-104">Description</span></span>  
 <span data-ttu-id="d81b8-105">Este seguimiento produce intentando establecer una conexión de vecino segura.</span><span class="sxs-lookup"><span data-stu-id="d81b8-105">This trace occurs while attempting to establish a secure neighbor connection.</span></span> <span data-ttu-id="d81b8-106">Esto puede suceder debido a unas credenciales insuficientes o incorrectas.</span><span class="sxs-lookup"><span data-stu-id="d81b8-106">This can happen due to insufficient or incorrect credentials.</span></span>  
  
 <span data-ttu-id="d81b8-107">PeerChannel reconoce un tipo de token único para una identificación fuerte, los certificados X.509, que proporcionan un modelo de identidad fuerte basados en el tipo de autenticación y autorización que se puede implementar.</span><span class="sxs-lookup"><span data-stu-id="d81b8-107">PeerChannel recognizes a single token type for strong identification, X.509 certificates, which provide a strong identity model based on the type of authentication and authorization that can be implemented.</span></span> <span data-ttu-id="d81b8-108">PeerChannel también proporciona compatibilidad para aplicaciones simples a través del uso de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="d81b8-108">PeerChannel also provides support for simple applications through the use of passwords.</span></span> <span data-ttu-id="d81b8-109">Las contraseñas solo se pueden utilizar para permitir la entrada a la sesión; no se pueden utilizar para realizar la autenticación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d81b8-109">Passwords can be used only to allow entry to the session; they cannot be used to perform message authentication.</span></span> <span data-ttu-id="d81b8-110">Esto se debe a que es difícil e inadecuado utilizar un token simétrico que un grupo de iguales comparten para la autenticación de origen.</span><span class="sxs-lookup"><span data-stu-id="d81b8-110">This is because a symmetric token that a group of peers share is difficult and inappropriate to use for source authentication.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="d81b8-111">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="d81b8-111">Troubleshooting</span></span>  
 <span data-ttu-id="d81b8-112">Asegúrese de que todos los vecinos tienen las credenciales de seguridad adecuadas.</span><span class="sxs-lookup"><span data-stu-id="d81b8-112">Ensure that all neighbors have the appropriate security credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d81b8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d81b8-113">See Also</span></span>  
 [<span data-ttu-id="d81b8-114">Seguridad del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="d81b8-114">Peer Channel Security</span></span>](../../../../../docs/framework/wcf/feature-details/peer-channel-security.md)  
 [<span data-ttu-id="d81b8-115">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="d81b8-115">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="d81b8-116">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="d81b8-116">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="d81b8-117">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d81b8-117">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)

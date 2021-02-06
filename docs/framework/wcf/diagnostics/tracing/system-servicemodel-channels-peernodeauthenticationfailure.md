---
description: 'Más información sobre: System. ServiceModel. Channels. PeerNodeAuthenticationFailure'
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.date: 03/30/2017
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
ms.openlocfilehash: 751202abd3e199a03fc4ee0bf1252d4a8027e0cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99634939"
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a><span data-ttu-id="a75e3-103">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span><span class="sxs-lookup"><span data-stu-id="a75e3-103">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span></span>

<span data-ttu-id="a75e3-104">El protocolo de enlace de seguridad con un vecino potencial no tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="a75e3-104">The security handshake with a potential neighbor was not successful.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a75e3-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="a75e3-105">Description</span></span>  

 <span data-ttu-id="a75e3-106">Este seguimiento produce intentando establecer una conexión de vecino segura.</span><span class="sxs-lookup"><span data-stu-id="a75e3-106">This trace occurs while attempting to establish a secure neighbor connection.</span></span> <span data-ttu-id="a75e3-107">Esto puede suceder debido a unas credenciales insuficientes o incorrectas.</span><span class="sxs-lookup"><span data-stu-id="a75e3-107">This can happen due to insufficient or incorrect credentials.</span></span>  
  
 <span data-ttu-id="a75e3-108">PeerChannel reconoce un tipo de token único para una identificación fuerte, los certificados X.509, que proporcionan un modelo de identidad fuerte basados en el tipo de autenticación y autorización que se puede implementar.</span><span class="sxs-lookup"><span data-stu-id="a75e3-108">PeerChannel recognizes a single token type for strong identification, X.509 certificates, which provide a strong identity model based on the type of authentication and authorization that can be implemented.</span></span> <span data-ttu-id="a75e3-109">PeerChannel también proporciona compatibilidad para aplicaciones simples a través del uso de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="a75e3-109">PeerChannel also provides support for simple applications through the use of passwords.</span></span> <span data-ttu-id="a75e3-110">Las contraseñas solo se pueden utilizar para permitir la entrada a la sesión; no se pueden utilizar para realizar la autenticación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a75e3-110">Passwords can be used only to allow entry to the session; they cannot be used to perform message authentication.</span></span> <span data-ttu-id="a75e3-111">Esto se debe a que es difícil e inadecuado utilizar un token simétrico que un grupo de iguales comparten para la autenticación de origen.</span><span class="sxs-lookup"><span data-stu-id="a75e3-111">This is because a symmetric token that a group of peers share is difficult and inappropriate to use for source authentication.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="a75e3-112">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="a75e3-112">Troubleshooting</span></span>  

 <span data-ttu-id="a75e3-113">Asegúrese de que todos los vecinos tienen las credenciales de seguridad adecuadas.</span><span class="sxs-lookup"><span data-stu-id="a75e3-113">Ensure that all neighbors have the appropriate security credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a75e3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a75e3-114">See also</span></span>

- [<span data-ttu-id="a75e3-115">Seguridad del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="a75e3-115">Peer Channel Security</span></span>](../../feature-details/peer-channel-security.md)
- [<span data-ttu-id="a75e3-116">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="a75e3-116">Tracing</span></span>](index.md)
- [<span data-ttu-id="a75e3-117">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="a75e3-117">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="a75e3-118">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="a75e3-118">Administration and Diagnostics</span></span>](../index.md)

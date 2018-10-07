---
title: Sesiones seguras
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
author: BrucePerlerMS
ms.openlocfilehash: 09c261afb2c64a46fc1f4619c4ec6b2e87b3fbbf
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2018
ms.locfileid: "48847391"
---
# <a name="secure-sessions"></a><span data-ttu-id="2a5d4-102">Sesiones seguras</span><span class="sxs-lookup"><span data-stu-id="2a5d4-102">Secure Sessions</span></span>
<span data-ttu-id="2a5d4-103">Una característica de Windows Communication Foundation (WCF) es las sesiones fiables que garantizan que los mensajes se reciben en el orden en que fueron enviados.</span><span class="sxs-lookup"><span data-stu-id="2a5d4-103">A feature of Windows Communication Foundation (WCF) is reliable sessions that guarantee messages are received in the order they were sent.</span></span> <span data-ttu-id="2a5d4-104">Los temas de esta sección discuten las implicaciones de seguridad a tener en cuenta a la hora de crear una sesión confiable.</span><span class="sxs-lookup"><span data-stu-id="2a5d4-104">The topics in this section discuss the security implications to consider when creating a reliable session.</span></span> <span data-ttu-id="2a5d4-105">Para obtener más información acerca de las sesiones confiables, vea [mediante sesiones](../../../../docs/framework/wcf/using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="2a5d4-105">For more information about reliable sessions, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a5d4-106">Si se requiere la suplantación en Windows XP, utilice una sesión segura sin un token de contexto de seguridad con estado (SCT).</span><span class="sxs-lookup"><span data-stu-id="2a5d4-106">When impersonation is required on Windows XP, use a secure session without a stateful security context token (SCT).</span></span> <span data-ttu-id="2a5d4-107">Cuando se utilizan SCT con estado con suplantación, se produce una <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="2a5d4-107">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="2a5d4-108">Para obtener más información, consulte [escenarios no admitidos](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="2a5d4-108">For more information, see [Unsupported Scenarios](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2a5d4-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2a5d4-109">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="2a5d4-110">Conversaciones y sesiones seguras</span><span class="sxs-lookup"><span data-stu-id="2a5d4-110">Secure Conversations and Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|<span data-ttu-id="2a5d4-111">Las conversaciones seguras y las sesiones seguras hacen referencia al mismo concepto.</span><span class="sxs-lookup"><span data-stu-id="2a5d4-111">Secure conversations and secure sessions are synonymous.</span></span> <span data-ttu-id="2a5d4-112">En este tema se explica la manera en la que funciona una conversación segura, así como cuándo y por qué utilizar el patrón.</span><span class="sxs-lookup"><span data-stu-id="2a5d4-112">This topic explains the way a secure conversation works, and when and why to use the pattern.</span></span>|  
|[<span data-ttu-id="2a5d4-113">Creación de una sesión segura</span><span class="sxs-lookup"><span data-stu-id="2a5d4-113">How to: Create a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|<span data-ttu-id="2a5d4-114">Tutorial sobre los fundamentos de la creación de sesiones seguras.</span><span class="sxs-lookup"><span data-stu-id="2a5d4-114">Walks through of the basics of creating a secure session.</span></span>|  
|[<span data-ttu-id="2a5d4-115">Creación de un token de contexto de seguridad para una sesión segura</span><span class="sxs-lookup"><span data-stu-id="2a5d4-115">How to: Create a Security Context Token for a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|<span data-ttu-id="2a5d4-116">Describe los pasos necesarios para la creación de una batería de servidores web que mantendrán estado y sesiones con clientes.</span><span class="sxs-lookup"><span data-stu-id="2a5d4-116">Walks through the steps of creating a Web farm that will maintain state and sessions with clients.</span></span>|  
|[<span data-ttu-id="2a5d4-117">Consideraciones de seguridad para sesiones seguras</span><span class="sxs-lookup"><span data-stu-id="2a5d4-117">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|<span data-ttu-id="2a5d4-118">Describe consideraciones especiales de las sesiones seguras.</span><span class="sxs-lookup"><span data-stu-id="2a5d4-118">Describes special considerations for secure sessions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="2a5d4-119">Referencia</span><span class="sxs-lookup"><span data-stu-id="2a5d4-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="2a5d4-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="2a5d4-120">Related Sections</span></span>  
 [<span data-ttu-id="2a5d4-121">Sesiones, creación de instancias y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="2a5d4-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [<span data-ttu-id="2a5d4-122">Diseño e implementación de servicios</span><span class="sxs-lookup"><span data-stu-id="2a5d4-122">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="2a5d4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a5d4-123">See Also</span></span>  
 [<span data-ttu-id="2a5d4-124">Habilitar la detección de repetición de mensajes</span><span class="sxs-lookup"><span data-stu-id="2a5d4-124">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 [<span data-ttu-id="2a5d4-125">Ataques por repetición</span><span class="sxs-lookup"><span data-stu-id="2a5d4-125">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 [<span data-ttu-id="2a5d4-126">Creación de un servicio que requiere sesiones</span><span class="sxs-lookup"><span data-stu-id="2a5d4-126">How to: Create a Service That Requires Sessions</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)

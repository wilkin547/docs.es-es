---
description: 'Más información acerca de: sesiones seguras'
title: Sesiones seguras
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: 8a4a2d23d5a27f5066bd5f004582829e499f714c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733078"
---
# <a name="secure-sessions"></a><span data-ttu-id="cb37e-103">Sesiones seguras</span><span class="sxs-lookup"><span data-stu-id="cb37e-103">Secure Sessions</span></span>

<span data-ttu-id="cb37e-104">Una característica de Windows Communication Foundation (WCF) son las sesiones confiables que garantizan que los mensajes se reciben en el orden en que se enviaron.</span><span class="sxs-lookup"><span data-stu-id="cb37e-104">A feature of Windows Communication Foundation (WCF) is reliable sessions that guarantee messages are received in the order they were sent.</span></span> <span data-ttu-id="cb37e-105">Los temas de esta sección discuten las implicaciones de seguridad a tener en cuenta a la hora de crear una sesión confiable.</span><span class="sxs-lookup"><span data-stu-id="cb37e-105">The topics in this section discuss the security implications to consider when creating a reliable session.</span></span> <span data-ttu-id="cb37e-106">Para obtener más información acerca de las sesiones confiables, vea [uso de sesiones](../using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="cb37e-106">For more information about reliable sessions, see [Using Sessions](../using-sessions.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cb37e-107">Si se requiere la suplantación en Windows XP, utilice una sesión segura sin un token de contexto de seguridad con estado (SCT).</span><span class="sxs-lookup"><span data-stu-id="cb37e-107">When impersonation is required on Windows XP, use a secure session without a stateful security context token (SCT).</span></span> <span data-ttu-id="cb37e-108">Cuando se utilizan SCT con estado con suplantación, se produce una <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="cb37e-108">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="cb37e-109">Para obtener más información, vea [escenarios no admitidos](unsupported-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="cb37e-109">For more information, see [Unsupported Scenarios](unsupported-scenarios.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cb37e-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cb37e-110">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="cb37e-111">Conversaciones y sesiones seguras</span><span class="sxs-lookup"><span data-stu-id="cb37e-111">Secure Conversations and Secure Sessions</span></span>](secure-conversations-and-secure-sessions.md)|<span data-ttu-id="cb37e-112">Las conversaciones seguras y las sesiones seguras hacen referencia al mismo concepto.</span><span class="sxs-lookup"><span data-stu-id="cb37e-112">Secure conversations and secure sessions are synonymous.</span></span> <span data-ttu-id="cb37e-113">En este tema se explica la manera en la que funciona una conversación segura, así como cuándo y por qué utilizar el patrón.</span><span class="sxs-lookup"><span data-stu-id="cb37e-113">This topic explains the way a secure conversation works, and when and why to use the pattern.</span></span>|  
|[<span data-ttu-id="cb37e-114">Procedimiento para crear una sesión segura</span><span class="sxs-lookup"><span data-stu-id="cb37e-114">How to: Create a Secure Session</span></span>](how-to-create-a-secure-session.md)|<span data-ttu-id="cb37e-115">Tutorial sobre los fundamentos de la creación de sesiones seguras.</span><span class="sxs-lookup"><span data-stu-id="cb37e-115">Walks through of the basics of creating a secure session.</span></span>|  
|[<span data-ttu-id="cb37e-116">Procedimiento para crear un token de contexto de seguridad para una sesión segura</span><span class="sxs-lookup"><span data-stu-id="cb37e-116">How to: Create a Security Context Token for a Secure Session</span></span>](how-to-create-a-security-context-token-for-a-secure-session.md)|<span data-ttu-id="cb37e-117">Describe los pasos necesarios para la creación de una batería de servidores web que mantendrán estado y sesiones con clientes.</span><span class="sxs-lookup"><span data-stu-id="cb37e-117">Walks through the steps of creating a Web farm that will maintain state and sessions with clients.</span></span>|  
|[<span data-ttu-id="cb37e-118">Consideraciones de seguridad para sesiones seguras</span><span class="sxs-lookup"><span data-stu-id="cb37e-118">Security Considerations for Secure Sessions</span></span>](security-considerations-for-secure-sessions.md)|<span data-ttu-id="cb37e-119">Describe consideraciones especiales de las sesiones seguras.</span><span class="sxs-lookup"><span data-stu-id="cb37e-119">Describes special considerations for secure sessions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="cb37e-120">Referencia</span><span class="sxs-lookup"><span data-stu-id="cb37e-120">Reference</span></span>  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="cb37e-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="cb37e-121">Related Sections</span></span>  

 [<span data-ttu-id="cb37e-122">Sesiones, creación de instancias y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="cb37e-122">Sessions, Instancing, and Concurrency</span></span>](sessions-instancing-and-concurrency.md)  
  
 [<span data-ttu-id="cb37e-123">Diseño e implementación de servicios</span><span class="sxs-lookup"><span data-stu-id="cb37e-123">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="cb37e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb37e-124">See also</span></span>

- [<span data-ttu-id="cb37e-125">Procedimiento para habilitar la detección de repetición de mensajes</span><span class="sxs-lookup"><span data-stu-id="cb37e-125">How to: Enable Message Replay Detection</span></span>](how-to-enable-message-replay-detection.md)
- [<span data-ttu-id="cb37e-126">Ataques por repetición</span><span class="sxs-lookup"><span data-stu-id="cb37e-126">Replay Attacks</span></span>](replay-attacks.md)
- [<span data-ttu-id="cb37e-127">Procedimiento para crear un servicio que requiere sesiones</span><span class="sxs-lookup"><span data-stu-id="cb37e-127">How to: Create a Service That Requires Sessions</span></span>](how-to-create-a-service-that-requires-sessions.md)

---
description: 'Más información sobre: consideraciones de seguridad en WCF'
title: Consideraciones de seguridad en WCF
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
ms.openlocfilehash: d75ff0d6eede4a46a5b795873e83445a04532993
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632482"
---
# <a name="security-considerations-in-wcf"></a><span data-ttu-id="c71c7-103">Consideraciones de seguridad en WCF</span><span class="sxs-lookup"><span data-stu-id="c71c7-103">Security Considerations in WCF</span></span>

<span data-ttu-id="c71c7-104">En los temas de esta sección se enumeran varios elementos relacionados con la seguridad que se deben tener en cuenta al diseñar una aplicación Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c71c7-104">The topics in this section list various security-related items to consider when designing a Windows Communication Foundation (WCF) application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c71c7-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c71c7-105">In This Section</span></span>  

 [<span data-ttu-id="c71c7-106">Divulgación de información</span><span class="sxs-lookup"><span data-stu-id="c71c7-106">Information Disclosure</span></span>](information-disclosure.md)  
 <span data-ttu-id="c71c7-107">Discute las varias maneras en las que se puede divulgar información o en las que se puede atacar a la información y cómo mitigarlo.</span><span class="sxs-lookup"><span data-stu-id="c71c7-107">Discusses the various ways that information can be disclosed or attacked, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="c71c7-108">Elevación de privilegios</span><span class="sxs-lookup"><span data-stu-id="c71c7-108">Elevation of Privilege</span></span>](elevation-of-privilege.md)  
 <span data-ttu-id="c71c7-109">Discute los efectos de proporcionar permisos de autorización a un atacante más allá de aquéllos concedidos inicialmente y cómo mitigarlo.</span><span class="sxs-lookup"><span data-stu-id="c71c7-109">Discusses the effects of giving an attacker authorization permissions beyond those initially granted and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="c71c7-110">Denegación de servicio</span><span class="sxs-lookup"><span data-stu-id="c71c7-110">Denial of Service</span></span>](denial-of-service.md)  
 <span data-ttu-id="c71c7-111">Discute lo que pasa cuando un sistema no puede procesar apropiadamente los mensajes y cómo mitigarlo.</span><span class="sxs-lookup"><span data-stu-id="c71c7-111">Discusses what happens when a system is unable to process messages appropriately and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="c71c7-112">Manipulación</span><span class="sxs-lookup"><span data-stu-id="c71c7-112">Tampering</span></span>](tampering.md)  
 <span data-ttu-id="c71c7-113">Discute la modificación de mensajes o de la entrega de mensajes y cómo mitigarlo.</span><span class="sxs-lookup"><span data-stu-id="c71c7-113">Discusses the altering of messages or the delivery of messages and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="c71c7-114">Ataques por repetición</span><span class="sxs-lookup"><span data-stu-id="c71c7-114">Replay Attacks</span></span>](replay-attacks.md)  
 <span data-ttu-id="c71c7-115">Discute lo que pasa cuando un atacante copia una secuencia de mensajes entre dos usuarios y vuelve a reproducir la secuencia para uno o más de los usuarios, y cómo mitigar esto.</span><span class="sxs-lookup"><span data-stu-id="c71c7-115">Discusses what happens when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="c71c7-116">Consideraciones de seguridad para sesiones seguras</span><span class="sxs-lookup"><span data-stu-id="c71c7-116">Security Considerations for Secure Sessions</span></span>](security-considerations-for-secure-sessions.md)  
 <span data-ttu-id="c71c7-117">Discute los siguientes elementos que afectan a la seguridad al implementar sesiones seguras.</span><span class="sxs-lookup"><span data-stu-id="c71c7-117">Discusses the following items that affect security when implementing secure sessions.</span></span>  
  
 [<span data-ttu-id="c71c7-118">Escenarios no admitidos</span><span class="sxs-lookup"><span data-stu-id="c71c7-118">Unsupported Scenarios</span></span>](unsupported-scenarios.md)  
 <span data-ttu-id="c71c7-119">Hace una lista de varios escenarios que no admiten ningún aspecto determinado de seguridad y que se deberían evitar o tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="c71c7-119">Lists various scenarios that do not support a particular aspect of security and should be avoided or considered.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c71c7-120">Referencia</span><span class="sxs-lookup"><span data-stu-id="c71c7-120">Reference</span></span>  

 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="c71c7-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c71c7-121">Related Sections</span></span>  

 [<span data-ttu-id="c71c7-122">Orientación de seguridad y procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="c71c7-122">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a><span data-ttu-id="c71c7-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c71c7-123">See also</span></span>

- [<span data-ttu-id="c71c7-124">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c71c7-124">Security</span></span>](security.md)

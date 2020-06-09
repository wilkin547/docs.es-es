---
title: Consideraciones de seguridad en WCF
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
ms.openlocfilehash: ed0f018e0151e68afeb9a4747bf8a260faa184b1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601041"
---
# <a name="security-considerations-in-wcf"></a><span data-ttu-id="3f2b0-102">Consideraciones de seguridad en WCF</span><span class="sxs-lookup"><span data-stu-id="3f2b0-102">Security Considerations in WCF</span></span>
<span data-ttu-id="3f2b0-103">En los temas de esta sección se enumeran varios elementos relacionados con la seguridad que se deben tener en cuenta al diseñar una aplicación Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3f2b0-103">The topics in this section list various security-related items to consider when designing a Windows Communication Foundation (WCF) application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3f2b0-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3f2b0-104">In This Section</span></span>  
 [<span data-ttu-id="3f2b0-105">Divulgación de información</span><span class="sxs-lookup"><span data-stu-id="3f2b0-105">Information Disclosure</span></span>](information-disclosure.md)  
 <span data-ttu-id="3f2b0-106">Discute las varias maneras en las que se puede divulgar información o en las que se puede atacar a la información y cómo mitigarlo.</span><span class="sxs-lookup"><span data-stu-id="3f2b0-106">Discusses the various ways that information can be disclosed or attacked, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="3f2b0-107">Elevación de privilegios</span><span class="sxs-lookup"><span data-stu-id="3f2b0-107">Elevation of Privilege</span></span>](elevation-of-privilege.md)  
 <span data-ttu-id="3f2b0-108">Discute los efectos de proporcionar permisos de autorización a un atacante más allá de aquéllos concedidos inicialmente y cómo mitigarlo.</span><span class="sxs-lookup"><span data-stu-id="3f2b0-108">Discusses the effects of giving an attacker authorization permissions beyond those initially granted and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="3f2b0-109">Denegación de servicio</span><span class="sxs-lookup"><span data-stu-id="3f2b0-109">Denial of Service</span></span>](denial-of-service.md)  
 <span data-ttu-id="3f2b0-110">Discute lo que pasa cuando un sistema no puede procesar apropiadamente los mensajes y cómo mitigarlo.</span><span class="sxs-lookup"><span data-stu-id="3f2b0-110">Discusses what happens when a system is unable to process messages appropriately and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="3f2b0-111">Alteración de datos</span><span class="sxs-lookup"><span data-stu-id="3f2b0-111">Tampering</span></span>](tampering.md)  
 <span data-ttu-id="3f2b0-112">Discute la modificación de mensajes o de la entrega de mensajes y cómo mitigarlo.</span><span class="sxs-lookup"><span data-stu-id="3f2b0-112">Discusses the altering of messages or the delivery of messages and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="3f2b0-113">Ataques por repetición</span><span class="sxs-lookup"><span data-stu-id="3f2b0-113">Replay Attacks</span></span>](replay-attacks.md)  
 <span data-ttu-id="3f2b0-114">Discute lo que pasa cuando un atacante copia una secuencia de mensajes entre dos usuarios y vuelve a reproducir la secuencia para uno o más de los usuarios, y cómo mitigar esto.</span><span class="sxs-lookup"><span data-stu-id="3f2b0-114">Discusses what happens when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="3f2b0-115">Consideraciones de seguridad para sesiones seguras</span><span class="sxs-lookup"><span data-stu-id="3f2b0-115">Security Considerations for Secure Sessions</span></span>](security-considerations-for-secure-sessions.md)  
 <span data-ttu-id="3f2b0-116">Discute los siguientes elementos que afectan a la seguridad al implementar sesiones seguras.</span><span class="sxs-lookup"><span data-stu-id="3f2b0-116">Discusses the following items that affect security when implementing secure sessions.</span></span>  
  
 [<span data-ttu-id="3f2b0-117">Escenarios no admitidos</span><span class="sxs-lookup"><span data-stu-id="3f2b0-117">Unsupported Scenarios</span></span>](unsupported-scenarios.md)  
 <span data-ttu-id="3f2b0-118">Hace una lista de varios escenarios que no admiten ningún aspecto determinado de seguridad y que se deberían evitar o tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="3f2b0-118">Lists various scenarios that do not support a particular aspect of security and should be avoided or considered.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3f2b0-119">Referencia</span><span class="sxs-lookup"><span data-stu-id="3f2b0-119">Reference</span></span>  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="3f2b0-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="3f2b0-120">Related Sections</span></span>  
 [<span data-ttu-id="3f2b0-121">Orientación de seguridad y procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="3f2b0-121">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a><span data-ttu-id="3f2b0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f2b0-122">See also</span></span>

- [<span data-ttu-id="3f2b0-123">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3f2b0-123">Security</span></span>](security.md)

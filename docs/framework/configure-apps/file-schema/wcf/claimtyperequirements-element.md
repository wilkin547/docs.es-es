---
title: <claimTypeRequirements> (elemento)
ms.date: 03/30/2017
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
ms.openlocfilehash: 6a4e5da3bd3ef6977d6258190d397130b33eb56c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148976"
---
# <a name="claimtyperequirements-element"></a><span data-ttu-id="068f5-102">Elemento \<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="068f5-102">\<claimTypeRequirements> element</span></span>

<span data-ttu-id="068f5-103">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="068f5-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="068f5-104">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="068f5-104">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="068f5-105">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="068f5-105">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="068f5-106">Cada elemento secundario de esta colección especifica los tipos de notificación necesarios y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="068f5-106">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="068f5-107">Un requisito de tipo de notificación está compuesto del URI del tipo de notificación solicitado en el token emitido junto con un parámetro booleano que indica si ese tipo de demanda se requiere en el token emitido o es opcional.</span><span class="sxs-lookup"><span data-stu-id="068f5-107">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="068f5-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="068f5-108">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="068f5-109">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="068f5-109">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="068f5-110">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="068f5-110">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="068f5-111">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="068f5-111">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="068f5-112">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="068f5-112">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](add-of-claimtyperequirements.md)
- [<span data-ttu-id="068f5-113">Enlaces</span><span class="sxs-lookup"><span data-stu-id="068f5-113">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="068f5-114">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="068f5-114">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="068f5-115">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="068f5-115">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="068f5-116">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="068f5-116">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="068f5-117">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="068f5-117">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)

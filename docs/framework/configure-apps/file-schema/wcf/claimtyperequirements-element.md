---
description: 'Más información acerca de: <claimTypeRequirements> elemento'
title: <claimTypeRequirements> (elemento)
ms.date: 03/30/2017
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
ms.openlocfilehash: 9553c129c246a5f4980d597406bee19ea949bdcc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638917"
---
# <a name="claimtyperequirements-element"></a><span data-ttu-id="f61b8-103">Elemento \<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="f61b8-103">\<claimTypeRequirements> element</span></span>

<span data-ttu-id="f61b8-104">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="f61b8-104">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="f61b8-105">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="f61b8-105">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="f61b8-106">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="f61b8-106">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="f61b8-107">Cada elemento secundario de esta colección especifica los tipos de notificación necesarios y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="f61b8-107">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="f61b8-108">Un requisito de tipo de notificación está compuesto del URI del tipo de notificación solicitado en el token emitido junto con un parámetro booleano que indica si ese tipo de demanda se requiere en el token emitido o es opcional.</span><span class="sxs-lookup"><span data-stu-id="f61b8-108">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f61b8-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="f61b8-109">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f61b8-110">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="f61b8-110">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f61b8-111">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="f61b8-111">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f61b8-112">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="f61b8-112">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="f61b8-113">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="f61b8-113">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](add-of-claimtyperequirements.md)
- [<span data-ttu-id="f61b8-114">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f61b8-114">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f61b8-115">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="f61b8-115">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f61b8-116">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="f61b8-116">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="f61b8-117">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f61b8-117">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="f61b8-118">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="f61b8-118">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)

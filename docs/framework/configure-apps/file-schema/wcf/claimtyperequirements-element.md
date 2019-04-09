---
title: <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
ms.openlocfilehash: 236ae880fff24f7ccbf5d6c9c03c0208d446688f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085849"
---
# <a name="claimtyperequirements-element"></a><span data-ttu-id="db374-102">\<claimTypeRequirements > elemento</span><span class="sxs-lookup"><span data-stu-id="db374-102">\<claimTypeRequirements> element</span></span>
<span data-ttu-id="db374-103">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="db374-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="db374-104">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="db374-104">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="db374-105">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="db374-105">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="db374-106">Cada elemento secundario de esta colección especifica los tipos de notificación necesarios y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="db374-106">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="db374-107">Un requisito de tipo de notificación está compuesto del URI del tipo de notificación solicitado en el token emitido junto con un parámetro booleano que indica si ese tipo de demanda se requiere en el token emitido o es opcional.</span><span class="sxs-lookup"><span data-stu-id="db374-107">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db374-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="db374-108">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="db374-109">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="db374-109">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="db374-110">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="db374-110">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="db374-111">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="db374-111">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="db374-112">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="db374-112">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="db374-113">\<add></span><span class="sxs-lookup"><span data-stu-id="db374-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-claimtyperequirements.md)
- [<span data-ttu-id="db374-114">Enlaces</span><span class="sxs-lookup"><span data-stu-id="db374-114">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="db374-115">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="db374-115">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="db374-116">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="db374-116">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="db374-117">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="db374-117">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="db374-118">Filtrar para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="db374-118">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="db374-119">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="db374-119">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)

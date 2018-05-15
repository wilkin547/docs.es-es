---
title: '&lt;claimTypeRequirements&gt; (elemento)'
ms.date: 03/30/2017
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
ms.openlocfilehash: 3a8bacf4dad2140e3d162cca89c6bd3ecf54b41f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimtyperequirementsgt-element"></a><span data-ttu-id="2458f-102">&lt;claimTypeRequirements&gt; (elemento)</span><span class="sxs-lookup"><span data-stu-id="2458f-102">&lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="2458f-103">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="2458f-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="2458f-104">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="2458f-104">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="2458f-105">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="2458f-105">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="2458f-106">Cada elemento secundario de esta colección especifica los tipos de notificación necesarios y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="2458f-106">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="2458f-107">Un requisito de tipo de notificación está compuesto del URI del tipo de notificación solicitado en el token emitido junto con un parámetro booleano que indica si ese tipo de demanda se requiere en el token emitido o es opcional.</span><span class="sxs-lookup"><span data-stu-id="2458f-107">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2458f-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="2458f-108">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="2458f-109">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="2458f-109">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="2458f-110">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="2458f-110">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="2458f-111">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="2458f-111">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="2458f-112">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="2458f-112">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="2458f-113">\<add></span><span class="sxs-lookup"><span data-stu-id="2458f-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-claimtyperequirements.md)  
 [<span data-ttu-id="2458f-114">Enlaces</span><span class="sxs-lookup"><span data-stu-id="2458f-114">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="2458f-115">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="2458f-115">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="2458f-116">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="2458f-116">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="2458f-117">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="2458f-117">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="2458f-118">Creación de un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="2458f-118">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="2458f-119">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="2458f-119">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)

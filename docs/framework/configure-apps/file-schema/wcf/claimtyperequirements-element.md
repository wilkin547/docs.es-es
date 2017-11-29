---
title: '&lt;claimTypeRequirements&gt; (elemento)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0146250c12c9c12e1f204c467a9a454b90e9f47a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltclaimtyperequirementsgt-element"></a><span data-ttu-id="606e1-102">&lt;claimTypeRequirements&gt; (elemento)</span><span class="sxs-lookup"><span data-stu-id="606e1-102">&lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="606e1-103">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="606e1-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="606e1-104">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="606e1-104">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="606e1-105">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="606e1-105">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="606e1-106">Cada elemento secundario de esta colección especifica los tipos de notificación necesarios y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="606e1-106">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="606e1-107">Un requisito de tipo de notificación está compuesto del URI del tipo de notificación solicitado en el token emitido junto con un parámetro booleano que indica si ese tipo de demanda se requiere en el token emitido o es opcional.</span><span class="sxs-lookup"><span data-stu-id="606e1-107">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="606e1-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="606e1-108">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="606e1-109">Autenticación e identidad de servicio</span><span class="sxs-lookup"><span data-stu-id="606e1-109">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="606e1-110">Federación y Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="606e1-110">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="606e1-111">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="606e1-111">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="606e1-112">Federación y Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="606e1-112">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="606e1-113">\<add></span><span class="sxs-lookup"><span data-stu-id="606e1-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-claimtyperequirements.md)  
 [<span data-ttu-id="606e1-114">Enlaces</span><span class="sxs-lookup"><span data-stu-id="606e1-114">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="606e1-115">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="606e1-115">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="606e1-116">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="606e1-116">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="606e1-117">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="606e1-117">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="606e1-118">Cómo: crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="606e1-118">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="606e1-119">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="606e1-119">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)

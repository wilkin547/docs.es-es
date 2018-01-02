---
title: '&lt;issuer&gt; de &lt;issuedTokenParameters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b31214f5552283c40cdc93e6e72a374bbfef9997
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltissuergt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="341e1-102">&lt;issuer&gt; de &lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="341e1-102">&lt;issuer&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="341e1-103">Especifica el servicio de token de seguridad (STS) que emite los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="341e1-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="341e1-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="341e1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="341e1-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="341e1-105">\<bindings></span></span>  
<span data-ttu-id="341e1-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="341e1-106">\<customBinding></span></span>  
<span data-ttu-id="341e1-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="341e1-107">\<binding></span></span>  
<span data-ttu-id="341e1-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="341e1-108">\<security></span></span>  
<span data-ttu-id="341e1-109">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="341e1-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="341e1-110">\<emisor ></span><span class="sxs-lookup"><span data-stu-id="341e1-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="341e1-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="341e1-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="341e1-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="341e1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="341e1-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="341e1-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="341e1-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="341e1-114">Attributes</span></span>  
  
|<span data-ttu-id="341e1-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="341e1-115">Attribute</span></span>|<span data-ttu-id="341e1-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="341e1-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="341e1-117">address</span><span class="sxs-lookup"><span data-stu-id="341e1-117">address</span></span>|<span data-ttu-id="341e1-118">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="341e1-118">Required string.</span></span> <span data-ttu-id="341e1-119">La dirección URL del STS.</span><span class="sxs-lookup"><span data-stu-id="341e1-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="341e1-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="341e1-120">Child Elements</span></span>  
  
|<span data-ttu-id="341e1-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="341e1-121">Element</span></span>|<span data-ttu-id="341e1-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="341e1-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="341e1-123">\<encabezados ></span><span class="sxs-lookup"><span data-stu-id="341e1-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="341e1-124">Una colección de encabezados de dirección para los puntos de conexión que el generador puede crear.</span><span class="sxs-lookup"><span data-stu-id="341e1-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="341e1-125">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="341e1-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="341e1-126">Al utilizar un token emitido, especifica valores que permiten al cliente autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="341e1-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="341e1-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="341e1-127">Parent Elements</span></span>  
  
|<span data-ttu-id="341e1-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="341e1-128">Element</span></span>|<span data-ttu-id="341e1-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="341e1-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="341e1-130">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="341e1-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="341e1-131">Especifica el token emitido actual.</span><span class="sxs-lookup"><span data-stu-id="341e1-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="341e1-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="341e1-132">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="341e1-133">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="341e1-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="341e1-134">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="341e1-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="341e1-135">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="341e1-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="341e1-136">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="341e1-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="341e1-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="341e1-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="341e1-138">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="341e1-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="341e1-139">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="341e1-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="341e1-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="341e1-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="341e1-141">Creación de un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="341e1-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="341e1-142">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="341e1-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)

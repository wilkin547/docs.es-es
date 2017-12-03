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
ms.openlocfilehash: 82e73a571ce7179518d380c0c63c9161b2ad5c55
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuergt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="a1467-102">&lt;issuer&gt; de &lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="a1467-102">&lt;issuer&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="a1467-103">Especifica el servicio de token de seguridad (STS) que emite los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a1467-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="a1467-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a1467-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a1467-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="a1467-105">\<bindings></span></span>  
<span data-ttu-id="a1467-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a1467-106">\<customBinding></span></span>  
<span data-ttu-id="a1467-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="a1467-107">\<binding></span></span>  
<span data-ttu-id="a1467-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="a1467-108">\<security></span></span>  
<span data-ttu-id="a1467-109">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="a1467-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="a1467-110">\<emisor ></span><span class="sxs-lookup"><span data-stu-id="a1467-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1467-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1467-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1467-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a1467-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a1467-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a1467-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1467-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="a1467-114">Attributes</span></span>  
  
|<span data-ttu-id="a1467-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="a1467-115">Attribute</span></span>|<span data-ttu-id="a1467-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1467-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a1467-117">address</span><span class="sxs-lookup"><span data-stu-id="a1467-117">address</span></span>|<span data-ttu-id="a1467-118">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="a1467-118">Required string.</span></span> <span data-ttu-id="a1467-119">La dirección URL del STS.</span><span class="sxs-lookup"><span data-stu-id="a1467-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1467-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a1467-120">Child Elements</span></span>  
  
|<span data-ttu-id="a1467-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="a1467-121">Element</span></span>|<span data-ttu-id="a1467-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1467-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1467-123">\<encabezados ></span><span class="sxs-lookup"><span data-stu-id="a1467-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="a1467-124">Una colección de encabezados de dirección para los puntos de conexión que el generador puede crear.</span><span class="sxs-lookup"><span data-stu-id="a1467-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="a1467-125">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="a1467-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="a1467-126">Al utilizar un token emitido, especifica valores que permiten al cliente autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="a1467-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a1467-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a1467-127">Parent Elements</span></span>  
  
|<span data-ttu-id="a1467-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="a1467-128">Element</span></span>|<span data-ttu-id="a1467-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1467-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1467-130">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="a1467-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="a1467-131">Especifica el token emitido actual.</span><span class="sxs-lookup"><span data-stu-id="a1467-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a1467-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1467-132">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="a1467-133">Autenticación e identidad de servicio</span><span class="sxs-lookup"><span data-stu-id="a1467-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="a1467-134">Federación y Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="a1467-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="a1467-135">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="a1467-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="a1467-136">Federación y Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="a1467-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="a1467-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a1467-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a1467-138">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="a1467-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="a1467-139">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="a1467-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="a1467-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a1467-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="a1467-141">Cómo: crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="a1467-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="a1467-142">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="a1467-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)

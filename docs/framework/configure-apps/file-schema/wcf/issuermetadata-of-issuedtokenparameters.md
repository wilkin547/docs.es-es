---
title: '&lt;issuerMetadata&gt; de &lt;issuedTokenParameters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ccd0417aeebbaf08d28457dd94a4d1698882c79e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuermetadatagt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="9de87-102">&lt;issuerMetadata&gt; de &lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="9de87-102">&lt;issuerMetadata&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="9de87-103">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="9de87-103">\<system.serviceModel></span></span>  
<span data-ttu-id="9de87-104">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="9de87-104">\<bindings></span></span>  
<span data-ttu-id="9de87-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="9de87-105">\<customBinding></span></span>  
<span data-ttu-id="9de87-106">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="9de87-106">\<binding></span></span>  
<span data-ttu-id="9de87-107">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="9de87-107">\<security></span></span>  
<span data-ttu-id="9de87-108">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="9de87-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="9de87-109">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="9de87-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9de87-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9de87-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address=String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9de87-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9de87-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9de87-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9de87-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9de87-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="9de87-113">Attributes</span></span>  
  
|<span data-ttu-id="9de87-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="9de87-114">Attribute</span></span>|<span data-ttu-id="9de87-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="9de87-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9de87-116">address</span><span class="sxs-lookup"><span data-stu-id="9de87-116">address</span></span>|<span data-ttu-id="9de87-117">Requerido.</span><span class="sxs-lookup"><span data-stu-id="9de87-117">Required.</span></span> <span data-ttu-id="9de87-118">Cadena que especifica la dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="9de87-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="9de87-119">La dirección debe ser un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="9de87-119">The address must be an absolute URI.</span></span> <span data-ttu-id="9de87-120">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="9de87-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9de87-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9de87-121">Child Elements</span></span>  
  
|<span data-ttu-id="9de87-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="9de87-122">Element</span></span>|<span data-ttu-id="9de87-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="9de87-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9de87-124">\<encabezados ></span><span class="sxs-lookup"><span data-stu-id="9de87-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="9de87-125">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="9de87-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="9de87-126">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="9de87-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="9de87-127">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="9de87-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9de87-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9de87-128">Parent Elements</span></span>  
  
|<span data-ttu-id="9de87-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="9de87-129">Element</span></span>|<span data-ttu-id="9de87-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="9de87-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9de87-131">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="9de87-131">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="9de87-132">Especifica los parámetros para un símbolo (token) de seguridad emitido en un escenario de seguridad aliado.</span><span class="sxs-lookup"><span data-stu-id="9de87-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9de87-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="9de87-133">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="9de87-134">Autenticación e identidad de servicio</span><span class="sxs-lookup"><span data-stu-id="9de87-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="9de87-135">Federación y Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="9de87-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="9de87-136">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="9de87-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="9de87-137">Federación y Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="9de87-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="9de87-138">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9de87-138">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="9de87-139">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="9de87-139">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="9de87-140">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="9de87-140">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="9de87-141">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="9de87-141">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="9de87-142">Cómo: crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9de87-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="9de87-143">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="9de87-143">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)

---
title: '&lt;issuer&gt; de &lt;issuedTokenParameters&gt;'
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: 459f2f43d3ef9426fbce7e0a0dd067250eb2cc4b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltissuergt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="f90c4-102">&lt;issuer&gt; de &lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="f90c4-102">&lt;issuer&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="f90c4-103">Especifica el servicio de token de seguridad (STS) que emite los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f90c4-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="f90c4-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f90c4-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f90c4-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="f90c4-105">\<bindings></span></span>  
<span data-ttu-id="f90c4-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="f90c4-106">\<customBinding></span></span>  
<span data-ttu-id="f90c4-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="f90c4-107">\<binding></span></span>  
<span data-ttu-id="f90c4-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="f90c4-108">\<security></span></span>  
<span data-ttu-id="f90c4-109">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="f90c4-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="f90c4-110">\<emisor ></span><span class="sxs-lookup"><span data-stu-id="f90c4-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f90c4-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f90c4-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f90c4-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f90c4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f90c4-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f90c4-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f90c4-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="f90c4-114">Attributes</span></span>  
  
|<span data-ttu-id="f90c4-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="f90c4-115">Attribute</span></span>|<span data-ttu-id="f90c4-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="f90c4-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f90c4-117">address</span><span class="sxs-lookup"><span data-stu-id="f90c4-117">address</span></span>|<span data-ttu-id="f90c4-118">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="f90c4-118">Required string.</span></span> <span data-ttu-id="f90c4-119">La dirección URL del STS.</span><span class="sxs-lookup"><span data-stu-id="f90c4-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f90c4-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f90c4-120">Child Elements</span></span>  
  
|<span data-ttu-id="f90c4-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="f90c4-121">Element</span></span>|<span data-ttu-id="f90c4-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="f90c4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f90c4-123">\<encabezados ></span><span class="sxs-lookup"><span data-stu-id="f90c4-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="f90c4-124">Una colección de encabezados de dirección para los puntos de conexión que el generador puede crear.</span><span class="sxs-lookup"><span data-stu-id="f90c4-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="f90c4-125">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="f90c4-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="f90c4-126">Al utilizar un token emitido, especifica valores que permiten al cliente autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="f90c4-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f90c4-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f90c4-127">Parent Elements</span></span>  
  
|<span data-ttu-id="f90c4-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="f90c4-128">Element</span></span>|<span data-ttu-id="f90c4-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="f90c4-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f90c4-130">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="f90c4-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="f90c4-131">Especifica el token emitido actual.</span><span class="sxs-lookup"><span data-stu-id="f90c4-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f90c4-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="f90c4-132">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="f90c4-133">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="f90c4-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="f90c4-134">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="f90c4-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="f90c4-135">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="f90c4-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="f90c4-136">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="f90c4-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="f90c4-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f90c4-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="f90c4-138">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="f90c4-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="f90c4-139">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="f90c4-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="f90c4-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="f90c4-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="f90c4-141">Creación de un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f90c4-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="f90c4-142">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="f90c4-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)

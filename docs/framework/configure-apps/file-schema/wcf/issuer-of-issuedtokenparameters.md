---
title: <issuer> de <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: 77ed9534ce872e805a6a6ea2c21a38710e6bc0fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925265"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="d1fc6-102">\<> del emisor de \<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="d1fc6-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="d1fc6-103">Especifica el servicio de token de seguridad (STS) que emite los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d1fc6-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="d1fc6-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d1fc6-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d1fc6-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d1fc6-105">\<bindings></span></span>  
<span data-ttu-id="d1fc6-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d1fc6-106">\<customBinding></span></span>  
<span data-ttu-id="d1fc6-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="d1fc6-107">\<binding></span></span>  
<span data-ttu-id="d1fc6-108">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="d1fc6-108">\<security></span></span>  
<span data-ttu-id="d1fc6-109">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="d1fc6-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="d1fc6-110">\<issuer></span><span class="sxs-lookup"><span data-stu-id="d1fc6-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1fc6-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1fc6-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1fc6-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d1fc6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d1fc6-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d1fc6-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1fc6-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="d1fc6-114">Attributes</span></span>  
  
|<span data-ttu-id="d1fc6-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="d1fc6-115">Attribute</span></span>|<span data-ttu-id="d1fc6-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d1fc6-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d1fc6-117">dirección</span><span class="sxs-lookup"><span data-stu-id="d1fc6-117">address</span></span>|<span data-ttu-id="d1fc6-118">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="d1fc6-118">Required string.</span></span> <span data-ttu-id="d1fc6-119">La dirección URL del STS.</span><span class="sxs-lookup"><span data-stu-id="d1fc6-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1fc6-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d1fc6-120">Child Elements</span></span>  
  
|<span data-ttu-id="d1fc6-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d1fc6-121">Element</span></span>|<span data-ttu-id="d1fc6-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d1fc6-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1fc6-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="d1fc6-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="d1fc6-124">Una colección de encabezados de dirección para los puntos de conexión que el generador puede crear.</span><span class="sxs-lookup"><span data-stu-id="d1fc6-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="d1fc6-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="d1fc6-125">\<identity></span></span>](identity.md)|<span data-ttu-id="d1fc6-126">Al utilizar un token emitido, especifica valores que permiten al cliente autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="d1fc6-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d1fc6-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d1fc6-127">Parent Elements</span></span>  
  
|<span data-ttu-id="d1fc6-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="d1fc6-128">Element</span></span>|<span data-ttu-id="d1fc6-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d1fc6-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1fc6-130">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="d1fc6-130">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="d1fc6-131">Especifica el token emitido actual.</span><span class="sxs-lookup"><span data-stu-id="d1fc6-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1fc6-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1fc6-132">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="d1fc6-133">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="d1fc6-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d1fc6-134">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="d1fc6-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d1fc6-135">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="d1fc6-135">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="d1fc6-136">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="d1fc6-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d1fc6-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="d1fc6-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d1fc6-138">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="d1fc6-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d1fc6-139">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="d1fc6-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="d1fc6-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d1fc6-140">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="d1fc6-141">Cómo: Crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d1fc6-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="d1fc6-142">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="d1fc6-142">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)

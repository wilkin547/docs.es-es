---
title: '&lt;issuerMetadata&gt; de &lt;issuedTokenParameters&gt;'
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: 82c04fe71ec67b2c539dae9c41eb35350c72d923
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746519"
---
# <a name="ltissuermetadatagt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="a0a78-102">&lt;issuerMetadata&gt; de &lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="a0a78-102">&lt;issuerMetadata&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="a0a78-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a0a78-103">\<system.serviceModel></span></span>  
<span data-ttu-id="a0a78-104">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="a0a78-104">\<bindings></span></span>  
<span data-ttu-id="a0a78-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a0a78-105">\<customBinding></span></span>  
<span data-ttu-id="a0a78-106">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="a0a78-106">\<binding></span></span>  
<span data-ttu-id="a0a78-107">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="a0a78-107">\<security></span></span>  
<span data-ttu-id="a0a78-108">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="a0a78-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="a0a78-109">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="a0a78-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0a78-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0a78-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address=String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0a78-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a0a78-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a0a78-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a0a78-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0a78-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="a0a78-113">Attributes</span></span>  
  
|<span data-ttu-id="a0a78-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="a0a78-114">Attribute</span></span>|<span data-ttu-id="a0a78-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0a78-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a0a78-116">address</span><span class="sxs-lookup"><span data-stu-id="a0a78-116">address</span></span>|<span data-ttu-id="a0a78-117">Requerido.</span><span class="sxs-lookup"><span data-stu-id="a0a78-117">Required.</span></span> <span data-ttu-id="a0a78-118">Cadena que especifica la dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="a0a78-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="a0a78-119">La dirección debe ser un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="a0a78-119">The address must be an absolute URI.</span></span> <span data-ttu-id="a0a78-120">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="a0a78-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0a78-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a0a78-121">Child Elements</span></span>  
  
|<span data-ttu-id="a0a78-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0a78-122">Element</span></span>|<span data-ttu-id="a0a78-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0a78-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0a78-124">\<encabezados ></span><span class="sxs-lookup"><span data-stu-id="a0a78-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="a0a78-125">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="a0a78-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="a0a78-126">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="a0a78-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="a0a78-127">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="a0a78-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0a78-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a0a78-128">Parent Elements</span></span>  
  
|<span data-ttu-id="a0a78-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0a78-129">Element</span></span>|<span data-ttu-id="a0a78-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0a78-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0a78-131">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="a0a78-131">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="a0a78-132">Especifica los parámetros para un símbolo (token) de seguridad emitido en un escenario de seguridad aliado.</span><span class="sxs-lookup"><span data-stu-id="a0a78-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0a78-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0a78-133">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="a0a78-134">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="a0a78-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="a0a78-135">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="a0a78-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="a0a78-136">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="a0a78-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="a0a78-137">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="a0a78-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="a0a78-138">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a0a78-138">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a0a78-139">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="a0a78-139">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="a0a78-140">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="a0a78-140">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="a0a78-141">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a0a78-141">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="a0a78-142">Creación de un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="a0a78-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="a0a78-143">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="a0a78-143">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)

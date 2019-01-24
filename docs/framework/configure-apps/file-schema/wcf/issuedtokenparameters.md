---
title: '&lt;issuedTokenParameters&gt;'
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: d3770764e75b3bfd1345ac6a44761861595309d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627465"
---
# <a name="ltissuedtokenparametersgt"></a><span data-ttu-id="2f9ca-102">&lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="2f9ca-102">&lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="2f9ca-103">Especifica los parámetros para un token de seguridad emitido en un escenario de seguridad aliado.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-103">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="2f9ca-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2f9ca-104">\<system.serviceModel></span></span>  
<span data-ttu-id="2f9ca-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="2f9ca-105">\<bindings></span></span>  
<span data-ttu-id="2f9ca-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2f9ca-106">\<customBinding></span></span>  
<span data-ttu-id="2f9ca-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="2f9ca-107">\<binding></span></span>  
<span data-ttu-id="2f9ca-108">\<security></span><span class="sxs-lookup"><span data-stu-id="2f9ca-108">\<security></span></span>  
<span data-ttu-id="2f9ca-109">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="2f9ca-109">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f9ca-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f9ca-110">Syntax</span></span>  
  
```xml  
<issuedTokenParameters defaultMessageSecurityVersion="System.ServiceModel.MessageSecurityVersion"
                       inclusionMode="AlwaysToInitiator/AlwaysToRecipient/Never/Once"
                       keySize="Integer"
                       keyType="AsymmetricKey/BearerKey/SymmetricKey"
                       tokenType="String">
  <additionalRequestParameters />
  <claimTypeRequirements>
    <add claimType="URI"
         isOptional="Boolean" />
  </claimTypeRequirements>
  <issuer address="String"
          binding="" />
  <issuerMetadata address="String" />
</issuedTokenParameters>
```  
  
## <a name="type"></a><span data-ttu-id="2f9ca-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="2f9ca-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f9ca-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2f9ca-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2f9ca-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f9ca-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="2f9ca-114">Attributes</span></span>  
  
|<span data-ttu-id="2f9ca-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="2f9ca-115">Attribute</span></span>|<span data-ttu-id="2f9ca-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f9ca-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2f9ca-117">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="2f9ca-117">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="2f9ca-118">Especifica las versiones de las especificaciones de seguridad, (WS-Security, WS-Trust, WS-Secure Conversation y WS-Security Policy) que debe admitir el enlace.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-118">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="2f9ca-119">Este valor es del tipo <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-119">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="2f9ca-120">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="2f9ca-120">inclusionMode</span></span>|<span data-ttu-id="2f9ca-121">Especifica los requisitos de inclusión del token.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-121">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="2f9ca-122">Este atributo es del tipo <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-122">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="2f9ca-123">keySize</span><span class="sxs-lookup"><span data-stu-id="2f9ca-123">keySize</span></span>|<span data-ttu-id="2f9ca-124">Un entero que especifica el tamaño de la clave del token.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-124">An integer that specifies the token key size.</span></span> <span data-ttu-id="2f9ca-125">El valor predeterminado es 256.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-125">The default value is 256.</span></span>|  
|<span data-ttu-id="2f9ca-126">keyType</span><span class="sxs-lookup"><span data-stu-id="2f9ca-126">keyType</span></span>|<span data-ttu-id="2f9ca-127">Una valor válido de <xref:System.IdentityModel.Tokens.SecurityKeyType> que especifica el tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-127">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="2f9ca-128">De manera predeterminada, es `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-128">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="2f9ca-129">tokenType</span><span class="sxs-lookup"><span data-stu-id="2f9ca-129">tokenType</span></span>|<span data-ttu-id="2f9ca-130">Una cadena que representa el tipo de token.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-130">A string that specifies the token type.</span></span> <span data-ttu-id="2f9ca-131">El valor predeterminado es "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span><span class="sxs-lookup"><span data-stu-id="2f9ca-131">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f9ca-132">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2f9ca-132">Child Elements</span></span>  
  
|<span data-ttu-id="2f9ca-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f9ca-133">Element</span></span>|<span data-ttu-id="2f9ca-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f9ca-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f9ca-135">\<additionalRequestParameters></span><span class="sxs-lookup"><span data-stu-id="2f9ca-135">\<additionalRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|<span data-ttu-id="2f9ca-136">Una colección de elementos de configuración que especifican los parámetros de solicitud adicionales.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-136">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="2f9ca-137">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="2f9ca-137">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="2f9ca-138">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-138">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="2f9ca-139">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="2f9ca-140">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="2f9ca-141">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-141">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="2f9ca-142">\<issuer></span><span class="sxs-lookup"><span data-stu-id="2f9ca-142">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|<span data-ttu-id="2f9ca-143">Un elemento de configuración que especifica el punto de conexión que emite el token actual.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-143">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="2f9ca-144">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="2f9ca-144">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="2f9ca-145">Un elemento de configuración que especifica la dirección del punto de conexión de los metadatos del emisor del token.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-145">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2f9ca-146">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2f9ca-146">Parent Elements</span></span>  
  
|<span data-ttu-id="2f9ca-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f9ca-147">Element</span></span>|<span data-ttu-id="2f9ca-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f9ca-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f9ca-149">\<secureConversationBootstrap></span><span class="sxs-lookup"><span data-stu-id="2f9ca-149">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="2f9ca-150">Especifica los valores predeterminados usados para iniciar un servicio de conversación seguro.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-150">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="2f9ca-151">\<security></span><span class="sxs-lookup"><span data-stu-id="2f9ca-151">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="2f9ca-152">Especifica las opciones de seguridad de un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="2f9ca-152">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2f9ca-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f9ca-153">See also</span></span>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="2f9ca-154">Enlaces</span><span class="sxs-lookup"><span data-stu-id="2f9ca-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="2f9ca-155">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="2f9ca-155">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2f9ca-156">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="2f9ca-156">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="2f9ca-157">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2f9ca-157">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="2f9ca-158">Cómo: Crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="2f9ca-158">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="2f9ca-159">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="2f9ca-159">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="2f9ca-160">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="2f9ca-160">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2f9ca-161">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="2f9ca-161">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2f9ca-162">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="2f9ca-162">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="2f9ca-163">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="2f9ca-163">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)

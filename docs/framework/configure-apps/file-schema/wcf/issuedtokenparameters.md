---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 6bdf56e3d2084dec8d44e1c4d3f0c1e50b711b92
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153145"
---
# <a name="issuedtokenparameters"></a><span data-ttu-id="57a5d-101">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="57a5d-101">\<issuedTokenParameters></span></span>
<span data-ttu-id="57a5d-102">Especifica los parámetros para un token de seguridad emitido en un escenario de seguridad aliado.</span><span class="sxs-lookup"><span data-stu-id="57a5d-102">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="57a5d-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="57a5d-103">\<system.serviceModel></span></span>  
<span data-ttu-id="57a5d-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="57a5d-104">\<bindings></span></span>  
<span data-ttu-id="57a5d-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="57a5d-105">\<customBinding></span></span>  
<span data-ttu-id="57a5d-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="57a5d-106">\<binding></span></span>  
<span data-ttu-id="57a5d-107">\<security></span><span class="sxs-lookup"><span data-stu-id="57a5d-107">\<security></span></span>  
<span data-ttu-id="57a5d-108">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="57a5d-108">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57a5d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57a5d-109">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="57a5d-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="57a5d-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57a5d-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="57a5d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="57a5d-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="57a5d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57a5d-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="57a5d-113">Attributes</span></span>  
  
|<span data-ttu-id="57a5d-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="57a5d-114">Attribute</span></span>|<span data-ttu-id="57a5d-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="57a5d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="57a5d-116">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="57a5d-116">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="57a5d-117">Especifica las versiones de las especificaciones de seguridad, (WS-Security, WS-Trust, WS-Secure Conversation y WS-Security Policy) que debe admitir el enlace.</span><span class="sxs-lookup"><span data-stu-id="57a5d-117">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="57a5d-118">Este valor es del tipo <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="57a5d-118">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="57a5d-119">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="57a5d-119">inclusionMode</span></span>|<span data-ttu-id="57a5d-120">Especifica los requisitos de inclusión del token.</span><span class="sxs-lookup"><span data-stu-id="57a5d-120">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="57a5d-121">Este atributo es del tipo <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="57a5d-121">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="57a5d-122">keySize</span><span class="sxs-lookup"><span data-stu-id="57a5d-122">keySize</span></span>|<span data-ttu-id="57a5d-123">Un entero que especifica el tamaño de la clave del token.</span><span class="sxs-lookup"><span data-stu-id="57a5d-123">An integer that specifies the token key size.</span></span> <span data-ttu-id="57a5d-124">El valor predeterminado es 256.</span><span class="sxs-lookup"><span data-stu-id="57a5d-124">The default value is 256.</span></span>|  
|<span data-ttu-id="57a5d-125">keyType</span><span class="sxs-lookup"><span data-stu-id="57a5d-125">keyType</span></span>|<span data-ttu-id="57a5d-126">Una valor válido de <xref:System.IdentityModel.Tokens.SecurityKeyType> que especifica el tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="57a5d-126">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="57a5d-127">De manera predeterminada, es `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="57a5d-127">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="57a5d-128">tokenType</span><span class="sxs-lookup"><span data-stu-id="57a5d-128">tokenType</span></span>|<span data-ttu-id="57a5d-129">Una cadena que representa el tipo de token.</span><span class="sxs-lookup"><span data-stu-id="57a5d-129">A string that specifies the token type.</span></span> <span data-ttu-id="57a5d-130">El valor predeterminado es "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span><span class="sxs-lookup"><span data-stu-id="57a5d-130">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57a5d-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="57a5d-131">Child Elements</span></span>  
  
|<span data-ttu-id="57a5d-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="57a5d-132">Element</span></span>|<span data-ttu-id="57a5d-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="57a5d-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57a5d-134">\<additionalRequestParameters></span><span class="sxs-lookup"><span data-stu-id="57a5d-134">\<additionalRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|<span data-ttu-id="57a5d-135">Una colección de elementos de configuración que especifican los parámetros de solicitud adicionales.</span><span class="sxs-lookup"><span data-stu-id="57a5d-135">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="57a5d-136">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="57a5d-136">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="57a5d-137">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="57a5d-137">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="57a5d-138">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="57a5d-138">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="57a5d-139">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="57a5d-139">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="57a5d-140">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="57a5d-140">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="57a5d-141">\<issuer></span><span class="sxs-lookup"><span data-stu-id="57a5d-141">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|<span data-ttu-id="57a5d-142">Un elemento de configuración que especifica el punto de conexión que emite el token actual.</span><span class="sxs-lookup"><span data-stu-id="57a5d-142">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="57a5d-143">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="57a5d-143">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="57a5d-144">Un elemento de configuración que especifica la dirección del punto de conexión de los metadatos del emisor del token.</span><span class="sxs-lookup"><span data-stu-id="57a5d-144">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="57a5d-145">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="57a5d-145">Parent Elements</span></span>  
  
|<span data-ttu-id="57a5d-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="57a5d-146">Element</span></span>|<span data-ttu-id="57a5d-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="57a5d-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57a5d-148">\<secureConversationBootstrap></span><span class="sxs-lookup"><span data-stu-id="57a5d-148">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="57a5d-149">Especifica los valores predeterminados usados para iniciar un servicio de conversación seguro.</span><span class="sxs-lookup"><span data-stu-id="57a5d-149">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="57a5d-150">\<security></span><span class="sxs-lookup"><span data-stu-id="57a5d-150">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="57a5d-151">Especifica las opciones de seguridad de un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="57a5d-151">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="57a5d-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="57a5d-152">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="57a5d-153">Enlaces</span><span class="sxs-lookup"><span data-stu-id="57a5d-153">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="57a5d-154">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="57a5d-154">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="57a5d-155">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="57a5d-155">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="57a5d-156">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="57a5d-156">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="57a5d-157">Filtrar para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="57a5d-157">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="57a5d-158">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="57a5d-158">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="57a5d-159">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="57a5d-159">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="57a5d-160">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="57a5d-160">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="57a5d-161">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="57a5d-161">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="57a5d-162">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="57a5d-162">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)

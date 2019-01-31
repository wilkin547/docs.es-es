---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 6b40bd6edd27f4c3b4b530387417311e1f93a921
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283600"
---
# <a name="issuedtokenparameters"></a><span data-ttu-id="2ed6f-101">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="2ed6f-101">\<issuedTokenParameters></span></span>
<span data-ttu-id="2ed6f-102">Especifica los parámetros para un token de seguridad emitido en un escenario de seguridad aliado.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-102">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="2ed6f-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2ed6f-103">\<system.serviceModel></span></span>  
<span data-ttu-id="2ed6f-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="2ed6f-104">\<bindings></span></span>  
<span data-ttu-id="2ed6f-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2ed6f-105">\<customBinding></span></span>  
<span data-ttu-id="2ed6f-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="2ed6f-106">\<binding></span></span>  
<span data-ttu-id="2ed6f-107">\<security></span><span class="sxs-lookup"><span data-stu-id="2ed6f-107">\<security></span></span>  
<span data-ttu-id="2ed6f-108">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="2ed6f-108">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ed6f-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ed6f-109">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="2ed6f-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="2ed6f-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ed6f-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2ed6f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2ed6f-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ed6f-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="2ed6f-113">Attributes</span></span>  
  
|<span data-ttu-id="2ed6f-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="2ed6f-114">Attribute</span></span>|<span data-ttu-id="2ed6f-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ed6f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ed6f-116">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="2ed6f-116">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="2ed6f-117">Especifica las versiones de las especificaciones de seguridad, (WS-Security, WS-Trust, WS-Secure Conversation y WS-Security Policy) que debe admitir el enlace.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-117">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="2ed6f-118">Este valor es del tipo <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-118">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="2ed6f-119">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="2ed6f-119">inclusionMode</span></span>|<span data-ttu-id="2ed6f-120">Especifica los requisitos de inclusión del token.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-120">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="2ed6f-121">Este atributo es del tipo <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-121">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="2ed6f-122">keySize</span><span class="sxs-lookup"><span data-stu-id="2ed6f-122">keySize</span></span>|<span data-ttu-id="2ed6f-123">Un entero que especifica el tamaño de la clave del token.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-123">An integer that specifies the token key size.</span></span> <span data-ttu-id="2ed6f-124">El valor predeterminado es 256.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-124">The default value is 256.</span></span>|  
|<span data-ttu-id="2ed6f-125">keyType</span><span class="sxs-lookup"><span data-stu-id="2ed6f-125">keyType</span></span>|<span data-ttu-id="2ed6f-126">Una valor válido de <xref:System.IdentityModel.Tokens.SecurityKeyType> que especifica el tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-126">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="2ed6f-127">De manera predeterminada, es `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-127">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="2ed6f-128">tokenType</span><span class="sxs-lookup"><span data-stu-id="2ed6f-128">tokenType</span></span>|<span data-ttu-id="2ed6f-129">Una cadena que representa el tipo de token.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-129">A string that specifies the token type.</span></span> <span data-ttu-id="2ed6f-130">El valor predeterminado es "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span><span class="sxs-lookup"><span data-stu-id="2ed6f-130">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ed6f-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2ed6f-131">Child Elements</span></span>  
  
|<span data-ttu-id="2ed6f-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="2ed6f-132">Element</span></span>|<span data-ttu-id="2ed6f-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ed6f-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ed6f-134">\<additionalRequestParameters></span><span class="sxs-lookup"><span data-stu-id="2ed6f-134">\<additionalRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|<span data-ttu-id="2ed6f-135">Una colección de elementos de configuración que especifican los parámetros de solicitud adicionales.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-135">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="2ed6f-136">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="2ed6f-136">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="2ed6f-137">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-137">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="2ed6f-138">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-138">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="2ed6f-139">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-139">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="2ed6f-140">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-140">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="2ed6f-141">\<issuer></span><span class="sxs-lookup"><span data-stu-id="2ed6f-141">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|<span data-ttu-id="2ed6f-142">Un elemento de configuración que especifica el punto de conexión que emite el token actual.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-142">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="2ed6f-143">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="2ed6f-143">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="2ed6f-144">Un elemento de configuración que especifica la dirección del punto de conexión de los metadatos del emisor del token.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-144">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ed6f-145">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2ed6f-145">Parent Elements</span></span>  
  
|<span data-ttu-id="2ed6f-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="2ed6f-146">Element</span></span>|<span data-ttu-id="2ed6f-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ed6f-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ed6f-148">\<secureConversationBootstrap></span><span class="sxs-lookup"><span data-stu-id="2ed6f-148">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="2ed6f-149">Especifica los valores predeterminados usados para iniciar un servicio de conversación seguro.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-149">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="2ed6f-150">\<security></span><span class="sxs-lookup"><span data-stu-id="2ed6f-150">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="2ed6f-151">Especifica las opciones de seguridad de un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="2ed6f-151">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ed6f-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ed6f-152">See also</span></span>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="2ed6f-153">Enlaces</span><span class="sxs-lookup"><span data-stu-id="2ed6f-153">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="2ed6f-154">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="2ed6f-154">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2ed6f-155">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="2ed6f-155">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="2ed6f-156">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2ed6f-156">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="2ed6f-157">Cómo: Crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="2ed6f-157">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="2ed6f-158">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="2ed6f-158">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="2ed6f-159">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="2ed6f-159">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2ed6f-160">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="2ed6f-160">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2ed6f-161">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="2ed6f-161">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="2ed6f-162">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="2ed6f-162">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)

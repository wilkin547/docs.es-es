---
title: '&lt;IssuedTokenParameters&gt;'
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 2060f98e94cec9e656420ac073204a82bc592b92
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149246"
---
# <a name="ltissuedtokenparametersgt"></a><span data-ttu-id="4d99b-102">&lt;IssuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="4d99b-102">&lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="4d99b-103">Especifica los parámetros para un token de seguridad emitido en un escenario de seguridad aliado.</span><span class="sxs-lookup"><span data-stu-id="4d99b-103">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="4d99b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4d99b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="4d99b-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="4d99b-105">\<bindings></span></span>  
<span data-ttu-id="4d99b-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="4d99b-106">\<customBinding></span></span>  
<span data-ttu-id="4d99b-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="4d99b-107">\<binding></span></span>  
<span data-ttu-id="4d99b-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="4d99b-108">\<security></span></span>  
<span data-ttu-id="4d99b-109">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="4d99b-109">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d99b-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d99b-110">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="4d99b-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="4d99b-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d99b-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4d99b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4d99b-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4d99b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d99b-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="4d99b-114">Attributes</span></span>  
  
|<span data-ttu-id="4d99b-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="4d99b-115">Attribute</span></span>|<span data-ttu-id="4d99b-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d99b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d99b-117">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="4d99b-117">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="4d99b-118">Especifica las versiones de las especificaciones de seguridad, (WS-Security, WS-Trust, WS-Secure Conversation y WS-Security Policy) que debe admitir el enlace.</span><span class="sxs-lookup"><span data-stu-id="4d99b-118">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="4d99b-119">Este valor es del tipo <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="4d99b-119">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="4d99b-120">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="4d99b-120">inclusionMode</span></span>|<span data-ttu-id="4d99b-121">Especifica los requisitos de inclusión del token.</span><span class="sxs-lookup"><span data-stu-id="4d99b-121">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="4d99b-122">Este atributo es del tipo <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="4d99b-122">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="4d99b-123">keySize</span><span class="sxs-lookup"><span data-stu-id="4d99b-123">keySize</span></span>|<span data-ttu-id="4d99b-124">Un entero que especifica el tamaño de la clave del token.</span><span class="sxs-lookup"><span data-stu-id="4d99b-124">An integer that specifies the token key size.</span></span> <span data-ttu-id="4d99b-125">El valor predeterminado es 256.</span><span class="sxs-lookup"><span data-stu-id="4d99b-125">The default value is 256.</span></span>|  
|<span data-ttu-id="4d99b-126">keyType</span><span class="sxs-lookup"><span data-stu-id="4d99b-126">keyType</span></span>|<span data-ttu-id="4d99b-127">Una valor válido de <xref:System.IdentityModel.Tokens.SecurityKeyType> que especifica el tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="4d99b-127">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="4d99b-128">De manera predeterminada, es `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="4d99b-128">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="4d99b-129">tokenType</span><span class="sxs-lookup"><span data-stu-id="4d99b-129">tokenType</span></span>|<span data-ttu-id="4d99b-130">Una cadena que representa el tipo de token.</span><span class="sxs-lookup"><span data-stu-id="4d99b-130">A string that specifies the token type.</span></span> <span data-ttu-id="4d99b-131">El valor predeterminado es "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span><span class="sxs-lookup"><span data-stu-id="4d99b-131">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d99b-132">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4d99b-132">Child Elements</span></span>  
  
|<span data-ttu-id="4d99b-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d99b-133">Element</span></span>|<span data-ttu-id="4d99b-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d99b-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d99b-135">\<additionalRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="4d99b-135">\<additionalRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|<span data-ttu-id="4d99b-136">Una colección de elementos de configuración que especifican los parámetros de solicitud adicionales.</span><span class="sxs-lookup"><span data-stu-id="4d99b-136">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="4d99b-137">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="4d99b-137">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="4d99b-138">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="4d99b-138">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="4d99b-139">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="4d99b-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="4d99b-140">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="4d99b-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="4d99b-141">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="4d99b-141">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="4d99b-142">\<emisor ></span><span class="sxs-lookup"><span data-stu-id="4d99b-142">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|<span data-ttu-id="4d99b-143">Un elemento de configuración que especifica el punto de conexión que emite el token actual.</span><span class="sxs-lookup"><span data-stu-id="4d99b-143">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="4d99b-144">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="4d99b-144">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="4d99b-145">Un elemento de configuración que especifica la dirección del punto de conexión de los metadatos del emisor del token.</span><span class="sxs-lookup"><span data-stu-id="4d99b-145">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4d99b-146">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4d99b-146">Parent Elements</span></span>  
  
|<span data-ttu-id="4d99b-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d99b-147">Element</span></span>|<span data-ttu-id="4d99b-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d99b-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d99b-149">\<secureConversationBootstrap ></span><span class="sxs-lookup"><span data-stu-id="4d99b-149">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="4d99b-150">Especifica los valores predeterminados usados para iniciar un servicio de conversación seguro.</span><span class="sxs-lookup"><span data-stu-id="4d99b-150">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="4d99b-151">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="4d99b-151">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="4d99b-152">Especifica las opciones de seguridad de un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="4d99b-152">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d99b-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d99b-153">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="4d99b-154">Enlaces</span><span class="sxs-lookup"><span data-stu-id="4d99b-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4d99b-155">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="4d99b-155">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="4d99b-156">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="4d99b-156">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="4d99b-157">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="4d99b-157">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="4d99b-158">Cómo: Crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="4d99b-158">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="4d99b-159">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="4d99b-159">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)  
 [<span data-ttu-id="4d99b-160">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="4d99b-160">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="4d99b-161">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="4d99b-161">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="4d99b-162">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="4d99b-162">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="4d99b-163">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="4d99b-163">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)

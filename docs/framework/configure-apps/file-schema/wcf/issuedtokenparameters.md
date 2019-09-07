---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 8432463ff62e4b5e54a491b574cc6a5285efe220
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397954"
---
# <a name="issuedtokenparameters"></a><span data-ttu-id="c2706-101">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="c2706-101">\<issuedTokenParameters></span></span>
<span data-ttu-id="c2706-102">Especifica los parámetros para un token de seguridad emitido en un escenario de seguridad aliado.</span><span class="sxs-lookup"><span data-stu-id="c2706-102">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
<span data-ttu-id="c2706-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c2706-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c2706-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c2706-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c2706-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c2706-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="c2706-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="c2706-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="c2706-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="c2706-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c2706-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguridad**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="c2706-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="c2706-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> issuedTokenParameters**</span><span class="sxs-lookup"><span data-stu-id="c2706-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenParameters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2706-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2706-110">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="c2706-111">Type</span><span class="sxs-lookup"><span data-stu-id="c2706-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2706-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c2706-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c2706-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c2706-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2706-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="c2706-114">Attributes</span></span>  
  
|<span data-ttu-id="c2706-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="c2706-115">Attribute</span></span>|<span data-ttu-id="c2706-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c2706-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c2706-117">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="c2706-117">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="c2706-118">Especifica las versiones de las especificaciones de seguridad, (WS-Security, WS-Trust, WS-Secure Conversation y WS-Security Policy) que debe admitir el enlace.</span><span class="sxs-lookup"><span data-stu-id="c2706-118">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="c2706-119">Este valor es del tipo <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="c2706-119">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="c2706-120">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="c2706-120">inclusionMode</span></span>|<span data-ttu-id="c2706-121">Especifica los requisitos de inclusión del token.</span><span class="sxs-lookup"><span data-stu-id="c2706-121">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="c2706-122">Este atributo es del tipo <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="c2706-122">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="c2706-123">keySize</span><span class="sxs-lookup"><span data-stu-id="c2706-123">keySize</span></span>|<span data-ttu-id="c2706-124">Un entero que especifica el tamaño de la clave del token.</span><span class="sxs-lookup"><span data-stu-id="c2706-124">An integer that specifies the token key size.</span></span> <span data-ttu-id="c2706-125">El valor predeterminado es 256.</span><span class="sxs-lookup"><span data-stu-id="c2706-125">The default value is 256.</span></span>|  
|<span data-ttu-id="c2706-126">keyType</span><span class="sxs-lookup"><span data-stu-id="c2706-126">keyType</span></span>|<span data-ttu-id="c2706-127">Una valor válido de <xref:System.IdentityModel.Tokens.SecurityKeyType> que especifica el tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="c2706-127">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="c2706-128">El valor predeterminado es `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="c2706-128">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="c2706-129">tokenType</span><span class="sxs-lookup"><span data-stu-id="c2706-129">tokenType</span></span>|<span data-ttu-id="c2706-130">Una cadena que representa el tipo de token.</span><span class="sxs-lookup"><span data-stu-id="c2706-130">A string that specifies the token type.</span></span> <span data-ttu-id="c2706-131">El valor predeterminado es "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span><span class="sxs-lookup"><span data-stu-id="c2706-131">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c2706-132">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c2706-132">Child Elements</span></span>  
  
|<span data-ttu-id="c2706-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="c2706-133">Element</span></span>|<span data-ttu-id="c2706-134">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c2706-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2706-135">\<additionalRequestParameters></span><span class="sxs-lookup"><span data-stu-id="c2706-135">\<additionalRequestParameters></span></span>](additionalrequestparameters-element.md)|<span data-ttu-id="c2706-136">Una colección de elementos de configuración que especifican los parámetros de solicitud adicionales.</span><span class="sxs-lookup"><span data-stu-id="c2706-136">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="c2706-137">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="c2706-137">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="c2706-138">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="c2706-138">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="c2706-139">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="c2706-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="c2706-140">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="c2706-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="c2706-141">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="c2706-141">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="c2706-142">\<issuer></span><span class="sxs-lookup"><span data-stu-id="c2706-142">\<issuer></span></span>](issuer-of-issuedtokenparameters.md)|<span data-ttu-id="c2706-143">Un elemento de configuración que especifica el punto de conexión que emite el token actual.</span><span class="sxs-lookup"><span data-stu-id="c2706-143">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="c2706-144">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="c2706-144">\<issuerMetadata></span></span>](issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="c2706-145">Un elemento de configuración que especifica la dirección del punto de conexión de los metadatos del emisor del token.</span><span class="sxs-lookup"><span data-stu-id="c2706-145">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c2706-146">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c2706-146">Parent Elements</span></span>  
  
|<span data-ttu-id="c2706-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="c2706-147">Element</span></span>|<span data-ttu-id="c2706-148">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c2706-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2706-149">\<secureConversationBootstrap></span><span class="sxs-lookup"><span data-stu-id="c2706-149">\<secureConversationBootstrap></span></span>](secureconversationbootstrap.md)|<span data-ttu-id="c2706-150">Especifica los valores predeterminados usados para iniciar un servicio de conversación seguro.</span><span class="sxs-lookup"><span data-stu-id="c2706-150">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="c2706-151">\<security></span><span class="sxs-lookup"><span data-stu-id="c2706-151">\<security></span></span>](security-of-custombinding.md)|<span data-ttu-id="c2706-152">Especifica las opciones de seguridad de un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="c2706-152">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2706-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2706-153">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c2706-154">Enlaces</span><span class="sxs-lookup"><span data-stu-id="c2706-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c2706-155">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="c2706-155">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c2706-156">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="c2706-156">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c2706-157">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c2706-157">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="c2706-158">Procedimientos: Crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="c2706-158">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="c2706-159">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="c2706-159">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="c2706-160">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="c2706-160">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c2706-161">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="c2706-161">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c2706-162">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="c2706-162">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="c2706-163">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="c2706-163">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)

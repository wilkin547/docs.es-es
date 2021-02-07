---
description: 'Más información acerca de: <issuedTokenParameters>'
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 92c8f5aa25ddb71561eb702ba3eb0396456008a6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725667"
---
# \<issuedTokenParameters>

<span data-ttu-id="9ecf6-102">Especifica los parámetros para un token de seguridad emitido en un escenario de seguridad aliado.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-102">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenParameters>**  
  
## <a name="syntax"></a><span data-ttu-id="9ecf6-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ecf6-103">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="9ecf6-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="9ecf6-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ecf6-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9ecf6-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9ecf6-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ecf6-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="9ecf6-107">Attributes</span></span>  
  
|<span data-ttu-id="9ecf6-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="9ecf6-108">Attribute</span></span>|<span data-ttu-id="9ecf6-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ecf6-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ecf6-110">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="9ecf6-110">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="9ecf6-111">Especifica las versiones de las especificaciones de seguridad, (WS-Security, WS-Trust, WS-Secure Conversation y WS-Security Policy) que debe admitir el enlace.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-111">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="9ecf6-112">Este valor es del tipo <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-112">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="9ecf6-113">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="9ecf6-113">inclusionMode</span></span>|<span data-ttu-id="9ecf6-114">Especifica los requisitos de inclusión del token.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-114">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="9ecf6-115">Este atributo es del tipo <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-115">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="9ecf6-116">keySize</span><span class="sxs-lookup"><span data-stu-id="9ecf6-116">keySize</span></span>|<span data-ttu-id="9ecf6-117">Un entero que especifica el tamaño de la clave del token.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-117">An integer that specifies the token key size.</span></span> <span data-ttu-id="9ecf6-118">El valor predeterminado es 256.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-118">The default value is 256.</span></span>|  
|<span data-ttu-id="9ecf6-119">keyType</span><span class="sxs-lookup"><span data-stu-id="9ecf6-119">keyType</span></span>|<span data-ttu-id="9ecf6-120">Una valor válido de <xref:System.IdentityModel.Tokens.SecurityKeyType> que especifica el tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-120">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="9ecf6-121">De manera predeterminada, es `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-121">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="9ecf6-122">tokenType</span><span class="sxs-lookup"><span data-stu-id="9ecf6-122">tokenType</span></span>|<span data-ttu-id="9ecf6-123">Una cadena que representa el tipo de token.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-123">A string that specifies the token type.</span></span> <span data-ttu-id="9ecf6-124">El valor predeterminado es "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span><span class="sxs-lookup"><span data-stu-id="9ecf6-124">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ecf6-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9ecf6-125">Child Elements</span></span>  
  
|<span data-ttu-id="9ecf6-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ecf6-126">Element</span></span>|<span data-ttu-id="9ecf6-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ecf6-127">Description</span></span>|  
|-------------|-----------------|  
|[\<additionalRequestParameters>](additionalrequestparameters-element.md)|<span data-ttu-id="9ecf6-128">Una colección de elementos de configuración que especifican los parámetros de solicitud adicionales.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-128">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="9ecf6-129">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-129">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="9ecf6-130">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-130">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="9ecf6-131">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-131">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="9ecf6-132">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-132">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[\<issuer>](issuer-of-issuedtokenparameters.md)|<span data-ttu-id="9ecf6-133">Un elemento de configuración que especifica el punto de conexión que emite el token actual.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-133">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[\<issuerMetadata>](issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="9ecf6-134">Un elemento de configuración que especifica la dirección del punto de conexión de los metadatos del emisor del token.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-134">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ecf6-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9ecf6-135">Parent Elements</span></span>  
  
|<span data-ttu-id="9ecf6-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ecf6-136">Element</span></span>|<span data-ttu-id="9ecf6-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ecf6-137">Description</span></span>|  
|-------------|-----------------|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|<span data-ttu-id="9ecf6-138">Especifica los valores predeterminados usados para iniciar un servicio de conversación seguro.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-138">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="9ecf6-139">Especifica las opciones de seguridad de un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="9ecf6-139">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ecf6-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ecf6-140">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="9ecf6-141">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9ecf6-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9ecf6-142">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="9ecf6-142">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="9ecf6-143">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="9ecf6-143">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="9ecf6-144">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9ecf6-144">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="9ecf6-145">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="9ecf6-145">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="9ecf6-146">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="9ecf6-146">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="9ecf6-147">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="9ecf6-147">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="9ecf6-148">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="9ecf6-148">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="9ecf6-149">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="9ecf6-149">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)

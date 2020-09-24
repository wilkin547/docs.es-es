---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: c90024a0629f39d160967ca00434e48f682d8933
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157322"
---
# \<issuedTokenParameters>

<span data-ttu-id="d603e-101">Especifica los parámetros para un token de seguridad emitido en un escenario de seguridad aliado.</span><span class="sxs-lookup"><span data-stu-id="d603e-101">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenParameters>**  
  
## <a name="syntax"></a><span data-ttu-id="d603e-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="d603e-102">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="d603e-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="d603e-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d603e-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d603e-104">Attributes and Elements</span></span>  

 <span data-ttu-id="d603e-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d603e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d603e-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="d603e-106">Attributes</span></span>  
  
|<span data-ttu-id="d603e-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="d603e-107">Attribute</span></span>|<span data-ttu-id="d603e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d603e-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d603e-109">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="d603e-109">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="d603e-110">Especifica las versiones de las especificaciones de seguridad, (WS-Security, WS-Trust, WS-Secure Conversation y WS-Security Policy) que debe admitir el enlace.</span><span class="sxs-lookup"><span data-stu-id="d603e-110">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="d603e-111">Este valor es del tipo <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="d603e-111">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="d603e-112">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="d603e-112">inclusionMode</span></span>|<span data-ttu-id="d603e-113">Especifica los requisitos de inclusión del token.</span><span class="sxs-lookup"><span data-stu-id="d603e-113">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="d603e-114">Este atributo es del tipo <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="d603e-114">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="d603e-115">keySize</span><span class="sxs-lookup"><span data-stu-id="d603e-115">keySize</span></span>|<span data-ttu-id="d603e-116">Un entero que especifica el tamaño de la clave del token.</span><span class="sxs-lookup"><span data-stu-id="d603e-116">An integer that specifies the token key size.</span></span> <span data-ttu-id="d603e-117">El valor predeterminado es 256.</span><span class="sxs-lookup"><span data-stu-id="d603e-117">The default value is 256.</span></span>|  
|<span data-ttu-id="d603e-118">keyType</span><span class="sxs-lookup"><span data-stu-id="d603e-118">keyType</span></span>|<span data-ttu-id="d603e-119">Una valor válido de <xref:System.IdentityModel.Tokens.SecurityKeyType> que especifica el tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="d603e-119">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="d603e-120">El valor predeterminado es `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="d603e-120">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="d603e-121">tokenType</span><span class="sxs-lookup"><span data-stu-id="d603e-121">tokenType</span></span>|<span data-ttu-id="d603e-122">Una cadena que representa el tipo de token.</span><span class="sxs-lookup"><span data-stu-id="d603e-122">A string that specifies the token type.</span></span> <span data-ttu-id="d603e-123">El valor predeterminado es "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span><span class="sxs-lookup"><span data-stu-id="d603e-123">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d603e-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d603e-124">Child Elements</span></span>  
  
|<span data-ttu-id="d603e-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="d603e-125">Element</span></span>|<span data-ttu-id="d603e-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="d603e-126">Description</span></span>|  
|-------------|-----------------|  
|[\<additionalRequestParameters>](additionalrequestparameters-element.md)|<span data-ttu-id="d603e-127">Una colección de elementos de configuración que especifican los parámetros de solicitud adicionales.</span><span class="sxs-lookup"><span data-stu-id="d603e-127">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="d603e-128">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="d603e-128">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="d603e-129">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="d603e-129">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="d603e-130">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="d603e-130">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="d603e-131">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="d603e-131">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[\<issuer>](issuer-of-issuedtokenparameters.md)|<span data-ttu-id="d603e-132">Un elemento de configuración que especifica el punto de conexión que emite el token actual.</span><span class="sxs-lookup"><span data-stu-id="d603e-132">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[\<issuerMetadata>](issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="d603e-133">Un elemento de configuración que especifica la dirección del punto de conexión de los metadatos del emisor del token.</span><span class="sxs-lookup"><span data-stu-id="d603e-133">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d603e-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d603e-134">Parent Elements</span></span>  
  
|<span data-ttu-id="d603e-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="d603e-135">Element</span></span>|<span data-ttu-id="d603e-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="d603e-136">Description</span></span>|  
|-------------|-----------------|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|<span data-ttu-id="d603e-137">Especifica los valores predeterminados usados para iniciar un servicio de conversación seguro.</span><span class="sxs-lookup"><span data-stu-id="d603e-137">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="d603e-138">Especifica las opciones de seguridad de un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="d603e-138">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d603e-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="d603e-139">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="d603e-140">Enlaces</span><span class="sxs-lookup"><span data-stu-id="d603e-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d603e-141">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="d603e-141">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d603e-142">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="d603e-142">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="d603e-143">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d603e-143">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="d603e-144">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="d603e-144">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="d603e-145">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="d603e-145">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d603e-146">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="d603e-146">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d603e-147">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="d603e-147">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="d603e-148">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="d603e-148">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)

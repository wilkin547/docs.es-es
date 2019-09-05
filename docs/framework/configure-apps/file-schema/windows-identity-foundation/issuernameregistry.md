---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: 209e702da80f2569f2b6c068f50f1af4489157f6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251966"
---
# <a name="issuernameregistry"></a><span data-ttu-id="3d6a8-101">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="3d6a8-101">\<issuerNameRegistry></span></span>
<span data-ttu-id="3d6a8-102">Configura el registro de nombres de emisores que usan los controladores de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
<span data-ttu-id="3d6a8-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3d6a8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3d6a8-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="3d6a8-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="3d6a8-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="3d6a8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="3d6a8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="3d6a8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="3d6a8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="3d6a8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="3d6a8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> issuerNameRegistry**</span><span class="sxs-lookup"><span data-stu-id="3d6a8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerNameRegistry>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d6a8-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d6a8-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d6a8-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3d6a8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3d6a8-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d6a8-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="3d6a8-112">Attributes</span></span>  
  
|<span data-ttu-id="3d6a8-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="3d6a8-113">Attribute</span></span>|<span data-ttu-id="3d6a8-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3d6a8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3d6a8-115">type</span><span class="sxs-lookup"><span data-stu-id="3d6a8-115">type</span></span>|<span data-ttu-id="3d6a8-116">Tipo que se deriva de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-116">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="3d6a8-117">Para obtener más información sobre cómo especificar un personalizado `type`, vea [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="3d6a8-117">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d6a8-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3d6a8-118">Child Elements</span></span>  
  
|<span data-ttu-id="3d6a8-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d6a8-119">Element</span></span>|<span data-ttu-id="3d6a8-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3d6a8-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d6a8-121">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="3d6a8-121">\<trustedIssuers></span></span>](trustedissuers.md)|<span data-ttu-id="3d6a8-122">Cuando el `type` atributo especifica el registro del nombre del emisor basado en la configuración <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> (la clase) [ \<](trustedissuers.md) , se debe especificar el elemento > de trustedIssuers.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-122">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="3d6a8-123">El `<add>` `<clear>` [ \<elemento > trustedIssuers](trustedissuers.md) puede tomar los elementos, `<remove>` o como elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-123">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d6a8-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3d6a8-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3d6a8-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d6a8-125">Element</span></span>|<span data-ttu-id="3d6a8-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3d6a8-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d6a8-127">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="3d6a8-127">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="3d6a8-128">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d6a8-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3d6a8-129">Remarks</span></span>  
 <span data-ttu-id="3d6a8-130">Todos los tokens de emisor se validan mediante un registro de nombres de emisor.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-130">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="3d6a8-131">Se trata de un objeto que se deriva de <xref:System.IdentityModel.Tokens.IssuerNameRegistry> la clase.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-131">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="3d6a8-132">El registro de nombres de emisores se usa para asociar un nombre de tecla de cifrado al material criptográfico necesario para comprobar las firmas de los tokens generados por el emisor correspondiente.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-132">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="3d6a8-133">El registro del nombre del emisor mantiene una lista de emisores de confianza para la aplicación de usuario de confianza (RP).</span><span class="sxs-lookup"><span data-stu-id="3d6a8-133">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="3d6a8-134">El tipo de registro del nombre del emisor se especifica mediante el `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-134">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="3d6a8-135">El `<issuerNameRegistry>` elemento puede tener uno o más elementos secundarios que proporcionan la configuración para el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-135">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="3d6a8-136">Proporcione la lógica que procesa estos elementos secundarios invalidando el <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> método.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-136">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="3d6a8-137">WIF proporciona un tipo de registro de nombre de emisor único fuera del cuadro, <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> la clase.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-137">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="3d6a8-138">Esta clase usa un conjunto de certificados de emisor de confianza que se especifican en la configuración.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-138">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="3d6a8-139">Requiere un elemento de configuración secundario, `<trustedIssuers>`, en el que se configura la colección de certificados de emisor de confianza.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-139">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="3d6a8-140">Los certificados de confianza se especifican mediante la forma codificada ASN. 1 de la huella digital del certificado y se agregan o quitan `<clear>`de la `<remove>` colección `<add>`mediante los elementos, o.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-140">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="3d6a8-141">El elemento se representa mediante la <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> clase. `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="3d6a8-141">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d6a8-142">Especificar el `<issuerNameRegistry>` elemento como elemento secundario [ \<](identityconfiguration.md) del elemento de > identityConfiguration está en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-142">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="3d6a8-143">La `<securityTokenHandlerConfiguration>` configuración del elemento invalida la `<identityConfiguration>` del elemento.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d6a8-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d6a8-144">Example</span></span>  
 <span data-ttu-id="3d6a8-145">El siguiente XML muestra cómo especificar el registro de nombres de emisor basado en la configuración.</span><span class="sxs-lookup"><span data-stu-id="3d6a8-145">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d6a8-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d6a8-146">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>

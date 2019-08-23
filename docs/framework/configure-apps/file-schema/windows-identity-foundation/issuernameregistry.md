---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: d0a1f8dd0c29aaee56c2ca1162cc70cc1e5ed106
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942669"
---
# <a name="issuernameregistry"></a><span data-ttu-id="d5dde-101">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="d5dde-101">\<issuerNameRegistry></span></span>
<span data-ttu-id="d5dde-102">Configura el registro de nombres de emisores que usan los controladores de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="d5dde-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="d5dde-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d5dde-103">\<system.identityModel></span></span>  
<span data-ttu-id="d5dde-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d5dde-104">\<identityConfiguration></span></span>  
<span data-ttu-id="d5dde-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d5dde-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="d5dde-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="d5dde-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="d5dde-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="d5dde-107">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5dde-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5dde-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5dde-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d5dde-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d5dde-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d5dde-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5dde-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="d5dde-111">Attributes</span></span>  
  
|<span data-ttu-id="d5dde-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="d5dde-112">Attribute</span></span>|<span data-ttu-id="d5dde-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d5dde-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d5dde-114">type</span><span class="sxs-lookup"><span data-stu-id="d5dde-114">type</span></span>|<span data-ttu-id="d5dde-115">Tipo que se deriva de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="d5dde-115">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="d5dde-116">Para obtener más información sobre cómo especificar un personalizado `type`, vea [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="d5dde-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5dde-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d5dde-117">Child Elements</span></span>  
  
|<span data-ttu-id="d5dde-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="d5dde-118">Element</span></span>|<span data-ttu-id="d5dde-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d5dde-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5dde-120">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="d5dde-120">\<trustedIssuers></span></span>](trustedissuers.md)|<span data-ttu-id="d5dde-121">Cuando el `type` atributo especifica el registro del nombre del emisor basado en la configuración <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> (la clase) [ \<](trustedissuers.md) , se debe especificar el elemento > de trustedIssuers.</span><span class="sxs-lookup"><span data-stu-id="d5dde-121">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="d5dde-122">El `<add>` `<clear>` [ \<elemento > trustedIssuers](trustedissuers.md) puede tomar los elementos, `<remove>` o como elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="d5dde-122">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d5dde-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d5dde-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d5dde-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="d5dde-124">Element</span></span>|<span data-ttu-id="d5dde-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d5dde-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5dde-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="d5dde-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="d5dde-127">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d5dde-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5dde-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5dde-128">Remarks</span></span>  
 <span data-ttu-id="d5dde-129">Todos los tokens de emisor se validan mediante un registro de nombres de emisor.</span><span class="sxs-lookup"><span data-stu-id="d5dde-129">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="d5dde-130">Se trata de un objeto que se deriva de <xref:System.IdentityModel.Tokens.IssuerNameRegistry> la clase.</span><span class="sxs-lookup"><span data-stu-id="d5dde-130">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="d5dde-131">El registro de nombres de emisores se usa para asociar un nombre de tecla de cifrado al material criptográfico necesario para comprobar las firmas de los tokens generados por el emisor correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d5dde-131">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="d5dde-132">El registro del nombre del emisor mantiene una lista de emisores de confianza para la aplicación de usuario de confianza (RP).</span><span class="sxs-lookup"><span data-stu-id="d5dde-132">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="d5dde-133">El tipo de registro del nombre del emisor se especifica mediante el `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="d5dde-133">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="d5dde-134">El `<issuerNameRegistry>` elemento puede tener uno o más elementos secundarios que proporcionan la configuración para el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="d5dde-134">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="d5dde-135">Proporcione la lógica que procesa estos elementos secundarios invalidando el <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> método.</span><span class="sxs-lookup"><span data-stu-id="d5dde-135">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="d5dde-136">WIF proporciona un tipo de registro de nombre de emisor único fuera del cuadro, <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> la clase.</span><span class="sxs-lookup"><span data-stu-id="d5dde-136">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="d5dde-137">Esta clase usa un conjunto de certificados de emisor de confianza que se especifican en la configuración.</span><span class="sxs-lookup"><span data-stu-id="d5dde-137">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="d5dde-138">Requiere un elemento de configuración secundario, `<trustedIssuers>`, en el que se configura la colección de certificados de emisor de confianza.</span><span class="sxs-lookup"><span data-stu-id="d5dde-138">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="d5dde-139">Los certificados de confianza se especifican mediante la forma codificada ASN. 1 de la huella digital del certificado y se agregan o quitan `<clear>`de la `<remove>` colección `<add>`mediante los elementos, o.</span><span class="sxs-lookup"><span data-stu-id="d5dde-139">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="d5dde-140">El elemento se representa mediante la <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> clase. `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="d5dde-140">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d5dde-141">Especificar el `<issuerNameRegistry>` elemento como elemento secundario [ \<](identityconfiguration.md) del elemento de > identityConfiguration está en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="d5dde-141">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="d5dde-142">La `<securityTokenHandlerConfiguration>` configuración del elemento invalida la `<identityConfiguration>` del elemento.</span><span class="sxs-lookup"><span data-stu-id="d5dde-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5dde-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5dde-143">Example</span></span>  
 <span data-ttu-id="d5dde-144">El siguiente XML muestra cómo especificar el registro de nombres de emisor basado en la configuración.</span><span class="sxs-lookup"><span data-stu-id="d5dde-144">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d5dde-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5dde-145">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>

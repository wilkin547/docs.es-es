---
title: '&lt;issuerNameRegistry&gt;'
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: b695cc6d66e5b9e45bb6a5fd22d594bc22ea3cba
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757533"
---
# <a name="ltissuernameregistrygt"></a><span data-ttu-id="484b3-102">&lt;issuerNameRegistry&gt;</span><span class="sxs-lookup"><span data-stu-id="484b3-102">&lt;issuerNameRegistry&gt;</span></span>
<span data-ttu-id="484b3-103">Configura el registro de nombre de emisor que se usa por los controladores de la colección de controlador de token.</span><span class="sxs-lookup"><span data-stu-id="484b3-103">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="484b3-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="484b3-104">\<system.identityModel></span></span>  
<span data-ttu-id="484b3-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="484b3-105">\<identityConfiguration></span></span>  
<span data-ttu-id="484b3-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="484b3-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="484b3-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="484b3-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="484b3-108">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="484b3-108">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="484b3-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="484b3-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="484b3-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="484b3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="484b3-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="484b3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="484b3-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="484b3-112">Attributes</span></span>  
  
|<span data-ttu-id="484b3-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="484b3-113">Attribute</span></span>|<span data-ttu-id="484b3-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="484b3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="484b3-115">type</span><span class="sxs-lookup"><span data-stu-id="484b3-115">type</span></span>|<span data-ttu-id="484b3-116">Un tipo que deriva de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="484b3-116">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="484b3-117">Para obtener más información acerca de cómo especificar un personalizado `type`, consulte la sección [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="484b3-117">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="484b3-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="484b3-118">Child Elements</span></span>  
  
|<span data-ttu-id="484b3-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="484b3-119">Element</span></span>|<span data-ttu-id="484b3-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="484b3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="484b3-121">\<trustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="484b3-121">\<trustedIssuers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|<span data-ttu-id="484b3-122">Cuando el `type` atributo especifica el registro de nombre de emisor basadas en configuración (la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase), el [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) se debe especificar el elemento.</span><span class="sxs-lookup"><span data-stu-id="484b3-122">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="484b3-123">El [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) puede tardar elemento `<add>`, `<clear>`, o `<remove>` elementos como elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="484b3-123">The [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="484b3-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="484b3-124">Parent Elements</span></span>  
  
|<span data-ttu-id="484b3-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="484b3-125">Element</span></span>|<span data-ttu-id="484b3-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="484b3-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="484b3-127">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="484b3-127">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="484b3-128">Proporciona la configuración para una colección de seguridad controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="484b3-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="484b3-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="484b3-129">Remarks</span></span>  
 <span data-ttu-id="484b3-130">Todos los tokens de emisor se validan mediante un registro de nombre de emisor.</span><span class="sxs-lookup"><span data-stu-id="484b3-130">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="484b3-131">Se trata de un objeto que se deriva de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="484b3-131">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="484b3-132">El registro de nombre de emisor se usa para asociar un nombre de tecla de acceso para el material criptográfico que se necesita para comprobar las firmas de tokens generados por el emisor correspondiente.</span><span class="sxs-lookup"><span data-stu-id="484b3-132">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="484b3-133">El registro de nombre de emisor mantiene una lista de emisores de confianza para la aplicación del usuario (RP) autenticado.</span><span class="sxs-lookup"><span data-stu-id="484b3-133">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="484b3-134">El tipo del registro de nombre de emisor se especifica utilizando el `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="484b3-134">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="484b3-135">El `<issuerNameRegistry>` elemento puede tener uno o varios elementos secundarios que proporcionan la configuración para el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="484b3-135">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="484b3-136">Proporcionar la lógica que procesa estos elementos secundarios invalidando el <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> método.</span><span class="sxs-lookup"><span data-stu-id="484b3-136">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="484b3-137">WIF ofrece un emisor único nombre de tipo de registro de fábrica, el <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="484b3-137">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="484b3-138">Esta clase utiliza un conjunto de certificados de emisor de confianza que se especifican en la configuración.</span><span class="sxs-lookup"><span data-stu-id="484b3-138">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="484b3-139">Requiere un elemento de configuración secundario, `<trustedIssuers>`, en la que se configura la colección de certificados de emisor de confianza.</span><span class="sxs-lookup"><span data-stu-id="484b3-139">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="484b3-140">Confianza de certificados se especifican utilizando el ASN.1 codificado de formulario de la huella digital del certificado y se agregan o quitan de la colección mediante el uso de `<add>`, `<clear>`, o `<remove>` elementos.</span><span class="sxs-lookup"><span data-stu-id="484b3-140">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="484b3-141">El `<issuerNameRegistry>` elemento representado por la <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> clase.</span><span class="sxs-lookup"><span data-stu-id="484b3-141">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="484b3-142">Especificar el `<issuerNameRegistry>` elemento como un elemento secundario de la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento está en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="484b3-142">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="484b3-143">Configuración de la `<securityTokenHandlerConfiguration>` elemento reemplazan a las que en el `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="484b3-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="484b3-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="484b3-144">Example</span></span>  
 <span data-ttu-id="484b3-145">El siguiente XML muestra cómo especificar al emisor de la configuración basada en el registro de nombres.</span><span class="sxs-lookup"><span data-stu-id="484b3-145">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="484b3-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="484b3-146">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>

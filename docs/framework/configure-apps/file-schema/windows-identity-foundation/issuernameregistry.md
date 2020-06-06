---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: 209e702da80f2569f2b6c068f50f1af4489157f6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251966"
---
# \<issuerNameRegistry>
<span data-ttu-id="5db32-101">Configura el registro de nombres de emisores que usan los controladores de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="5db32-101">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerNameRegistry>**  
  
## <a name="syntax"></a><span data-ttu-id="5db32-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5db32-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5db32-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5db32-103">Attributes and Elements</span></span>  
 <span data-ttu-id="5db32-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5db32-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5db32-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="5db32-105">Attributes</span></span>  
  
|<span data-ttu-id="5db32-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="5db32-106">Attribute</span></span>|<span data-ttu-id="5db32-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5db32-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5db32-108">type</span><span class="sxs-lookup"><span data-stu-id="5db32-108">type</span></span>|<span data-ttu-id="5db32-109">Tipo que se deriva de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="5db32-109">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="5db32-110">Para obtener más información sobre cómo especificar un personalizado `type` , vea [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="5db32-110">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5db32-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5db32-111">Child Elements</span></span>  
  
|<span data-ttu-id="5db32-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="5db32-112">Element</span></span>|<span data-ttu-id="5db32-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5db32-113">Description</span></span>|  
|-------------|-----------------|  
|[\<trustedIssuers>](trustedissuers.md)|<span data-ttu-id="5db32-114">Cuando el `type` atributo especifica el registro del nombre del emisor basado en la configuración (la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase), [\<trustedIssuers>](trustedissuers.md) se debe especificar el elemento.</span><span class="sxs-lookup"><span data-stu-id="5db32-114">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="5db32-115">El [\<trustedIssuers>](trustedissuers.md) elemento puede tomar `<add>` los `<clear>` elementos, o `<remove>` como elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="5db32-115">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5db32-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5db32-116">Parent Elements</span></span>  
  
|<span data-ttu-id="5db32-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="5db32-117">Element</span></span>|<span data-ttu-id="5db32-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="5db32-118">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="5db32-119">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5db32-119">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5db32-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5db32-120">Remarks</span></span>  
 <span data-ttu-id="5db32-121">Todos los tokens de emisor se validan mediante un registro de nombres de emisor.</span><span class="sxs-lookup"><span data-stu-id="5db32-121">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="5db32-122">Se trata de un objeto que se deriva de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="5db32-122">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="5db32-123">El registro de nombres de emisores se usa para asociar un nombre de tecla de cifrado al material criptográfico necesario para comprobar las firmas de los tokens generados por el emisor correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5db32-123">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="5db32-124">El registro del nombre del emisor mantiene una lista de emisores de confianza para la aplicación de usuario de confianza (RP).</span><span class="sxs-lookup"><span data-stu-id="5db32-124">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="5db32-125">El tipo de registro del nombre del emisor se especifica mediante el `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="5db32-125">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="5db32-126">El `<issuerNameRegistry>` elemento puede tener uno o más elementos secundarios que proporcionan la configuración para el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="5db32-126">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="5db32-127">Proporcione la lógica que procesa estos elementos secundarios invalidando el <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> método.</span><span class="sxs-lookup"><span data-stu-id="5db32-127">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="5db32-128">WIF proporciona un tipo de registro de nombre de emisor único fuera del cuadro, la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="5db32-128">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="5db32-129">Esta clase usa un conjunto de certificados de emisor de confianza que se especifican en la configuración.</span><span class="sxs-lookup"><span data-stu-id="5db32-129">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="5db32-130">Requiere un elemento de configuración secundario, `<trustedIssuers>` , en el que se configura la colección de certificados de emisor de confianza.</span><span class="sxs-lookup"><span data-stu-id="5db32-130">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="5db32-131">Los certificados de confianza se especifican mediante la forma codificada ASN. 1 de la huella digital del certificado y se agregan o quitan de la colección mediante `<add>` `<clear>` `<remove>` los elementos, o.</span><span class="sxs-lookup"><span data-stu-id="5db32-131">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="5db32-132">El `<issuerNameRegistry>` elemento se representa mediante la <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> clase.</span><span class="sxs-lookup"><span data-stu-id="5db32-132">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5db32-133">Especificar el `<issuerNameRegistry>` elemento como elemento secundario del [\<identityConfiguration>](identityconfiguration.md) elemento está en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="5db32-133">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="5db32-134">La configuración del `<securityTokenHandlerConfiguration>` elemento invalida la del `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="5db32-134">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5db32-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5db32-135">Example</span></span>  
 <span data-ttu-id="5db32-136">El siguiente XML muestra cómo especificar el registro de nombres de emisor basado en la configuración.</span><span class="sxs-lookup"><span data-stu-id="5db32-136">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5db32-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5db32-137">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>

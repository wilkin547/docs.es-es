---
title: '&lt;trustedIssuers&gt;'
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: f9daea7d6b78e2f6790050b35dde62db6058c60b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="lttrustedissuersgt"></a><span data-ttu-id="e1c6c-102">&lt;trustedIssuers&gt;</span><span class="sxs-lookup"><span data-stu-id="e1c6c-102">&lt;trustedIssuers&gt;</span></span>
<span data-ttu-id="e1c6c-103">Configura la lista de certificados de emisor de confianza utilizado por el registro de nombre de emisor basadas en configuración (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span><span class="sxs-lookup"><span data-stu-id="e1c6c-103">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="e1c6c-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="e1c6c-104">\<system.identityModel></span></span>  
<span data-ttu-id="e1c6c-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e1c6c-105">\<identityConfiguration></span></span>  
<span data-ttu-id="e1c6c-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="e1c6c-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="e1c6c-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e1c6c-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="e1c6c-108">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="e1c6c-108">\<issuerNameRegistry></span></span>  
<span data-ttu-id="e1c6c-109">\<trustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="e1c6c-109">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1c6c-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1c6c-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1c6c-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e1c6c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e1c6c-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1c6c-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="e1c6c-113">Attributes</span></span>  
 <span data-ttu-id="e1c6c-114">Ninguna</span><span class="sxs-lookup"><span data-stu-id="e1c6c-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e1c6c-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e1c6c-115">Child Elements</span></span>  
  
|<span data-ttu-id="e1c6c-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="e1c6c-116">Element</span></span>|<span data-ttu-id="e1c6c-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1c6c-117">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="e1c6c-118">Agrega un certificado a la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-118">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="e1c6c-119">El certificado se especifica con el `thumbprint` atributo.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-119">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="e1c6c-120">Este atributo es necesario y debe contener el formulario ASN.1 codificado la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-120">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="e1c6c-121">El `name` atributo es opcional y puede utilizarse para especificar un nombre descriptivo para el certificado.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-121">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="e1c6c-122">Borra todos los certificados de la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-122">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="e1c6c-123">Quita un certificado de la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-123">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="e1c6c-124">El certificado se especifica con el `thumbprint` atributo.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-124">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="e1c6c-125">Este atributo es necesario.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-125">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e1c6c-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e1c6c-126">Parent Elements</span></span>  
  
|<span data-ttu-id="e1c6c-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="e1c6c-127">Element</span></span>|<span data-ttu-id="e1c6c-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1c6c-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1c6c-129">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="e1c6c-129">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="e1c6c-130">Configura el registro de nombre de emisor.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-130">Configures the issuer name registry.</span></span> <span data-ttu-id="e1c6c-131">**Importante:** el `type` atributo de la `<issuerNameRegistry>` elemento debe hacer referencia a la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> de clases para el `<trustedIssuers>` elemento sea válido.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-131">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1c6c-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e1c6c-132">Remarks</span></span>  
 <span data-ttu-id="e1c6c-133">Windows Identity Foundation (WIF) proporciona una implementación única de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase de fábrica, el <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-133">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="e1c6c-134">El registro de nombre de emisor de configuración mantiene una lista de emisores de confianza que se carga desde la configuración.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-134">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="e1c6c-135">La lista asocia cada nombre del emisor del certificado X.509 que se necesita para verificar la firma de tokens generado por el emisor.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-135">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="e1c6c-136">La lista de certificados de emisor de confianza se especifica en el `<trustedIssuers>` elemento.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-136">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="e1c6c-137">Cada elemento de la lista asocia un nombre de emisor de tecla de acceso con el certificado X.509 que se necesita para verificar la firma de tokens producidos por ese emisor.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-137">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="e1c6c-138">Certificados de confianza se especifican utilizando el ASN.1 codificado formada por la huella digital del certificado y se agregan a la colección mediante `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-138">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="e1c6c-139">Puede borrar o quitar emisores (certificados) de la lista mediante el `<clear>` y `<remove>` elementos.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-139">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="e1c6c-140">El `type` atributo de la `<issuerNameRegistry>` elemento debe hacer referencia a la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> de clases para el `<trustedIssuers>` elemento sea válido.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-140">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1c6c-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1c6c-141">Example</span></span>  
 <span data-ttu-id="e1c6c-142">El siguiente XML muestra cómo especificar al emisor de la configuración basada en el registro de nombres.</span><span class="sxs-lookup"><span data-stu-id="e1c6c-142">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1c6c-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1c6c-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>

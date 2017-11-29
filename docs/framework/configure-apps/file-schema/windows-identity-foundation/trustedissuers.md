---
title: '&lt;trustedIssuers&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 33ef3ca88462595d81d269a92a643b43c9aea025
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="lttrustedissuersgt"></a><span data-ttu-id="d9427-102">&lt;trustedIssuers&gt;</span><span class="sxs-lookup"><span data-stu-id="d9427-102">&lt;trustedIssuers&gt;</span></span>
<span data-ttu-id="d9427-103">Configura la lista de certificados de emisor de confianza utilizado por el registro de nombre de emisor basadas en configuración (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span><span class="sxs-lookup"><span data-stu-id="d9427-103">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="d9427-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="d9427-104">\<system.identityModel></span></span>  
<span data-ttu-id="d9427-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d9427-105">\<identityConfiguration></span></span>  
<span data-ttu-id="d9427-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="d9427-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="d9427-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d9427-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="d9427-108">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="d9427-108">\<issuerNameRegistry></span></span>  
<span data-ttu-id="d9427-109">\<trustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="d9427-109">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9427-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9427-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9427-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d9427-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d9427-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d9427-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9427-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="d9427-113">Attributes</span></span>  
 <span data-ttu-id="d9427-114">Ninguna</span><span class="sxs-lookup"><span data-stu-id="d9427-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d9427-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d9427-115">Child Elements</span></span>  
  
|<span data-ttu-id="d9427-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="d9427-116">Element</span></span>|<span data-ttu-id="d9427-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9427-117">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="d9427-118">Agrega un certificado a la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="d9427-118">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="d9427-119">El certificado se especifica con el `thumbprint` atributo.</span><span class="sxs-lookup"><span data-stu-id="d9427-119">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="d9427-120">Este atributo es necesario y debe contener el formulario ASN.1 codificado la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="d9427-120">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="d9427-121">El `name` atributo es opcional y puede utilizarse para especificar un nombre descriptivo para el certificado.</span><span class="sxs-lookup"><span data-stu-id="d9427-121">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="d9427-122">Borra todos los certificados de la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="d9427-122">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="d9427-123">Quita un certificado de la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="d9427-123">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="d9427-124">El certificado se especifica con el `thumbprint` atributo.</span><span class="sxs-lookup"><span data-stu-id="d9427-124">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="d9427-125">Este atributo es necesario.</span><span class="sxs-lookup"><span data-stu-id="d9427-125">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d9427-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d9427-126">Parent Elements</span></span>  
  
|<span data-ttu-id="d9427-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="d9427-127">Element</span></span>|<span data-ttu-id="d9427-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9427-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9427-129">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="d9427-129">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="d9427-130">Configura el registro de nombre de emisor.</span><span class="sxs-lookup"><span data-stu-id="d9427-130">Configures the issuer name registry.</span></span> <span data-ttu-id="d9427-131">**Importante:** el `type` atributo de la `<issuerNameRegistry>` elemento debe hacer referencia a la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> de clases para el `<trustedIssuers>` elemento sea válido.</span><span class="sxs-lookup"><span data-stu-id="d9427-131">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9427-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9427-132">Remarks</span></span>  
 <span data-ttu-id="d9427-133">Windows Identity Foundation (WIF) proporciona una implementación única de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase de fábrica, el <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="d9427-133">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="d9427-134">El registro de nombre de emisor de configuración mantiene una lista de emisores de confianza que se carga desde la configuración.</span><span class="sxs-lookup"><span data-stu-id="d9427-134">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="d9427-135">La lista asocia cada nombre del emisor del certificado X.509 que se necesita para verificar la firma de tokens generado por el emisor.</span><span class="sxs-lookup"><span data-stu-id="d9427-135">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="d9427-136">La lista de certificados de emisor de confianza se especifica en el `<trustedIssuers>` elemento.</span><span class="sxs-lookup"><span data-stu-id="d9427-136">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="d9427-137">Cada elemento de la lista asocia un nombre de emisor de tecla de acceso con el certificado X.509 que se necesita para verificar la firma de tokens producidos por ese emisor.</span><span class="sxs-lookup"><span data-stu-id="d9427-137">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="d9427-138">Certificados de confianza se especifican utilizando el ASN.1 codificado formada por la huella digital del certificado y se agregan a la colección mediante `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="d9427-138">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="d9427-139">Puede borrar o quitar emisores (certificados) de la lista mediante el `<clear>` y `<remove>` elementos.</span><span class="sxs-lookup"><span data-stu-id="d9427-139">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="d9427-140">El `type` atributo de la `<issuerNameRegistry>` elemento debe hacer referencia a la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> de clases para el `<trustedIssuers>` elemento sea válido.</span><span class="sxs-lookup"><span data-stu-id="d9427-140">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9427-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d9427-141">Example</span></span>  
 <span data-ttu-id="d9427-142">El siguiente XML muestra cómo especificar al emisor de la configuración basada en el registro de nombres.</span><span class="sxs-lookup"><span data-stu-id="d9427-142">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9427-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9427-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>

---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: cebfc2f3598f32f233db6039dfe82076d2ffce46
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790486"
---
# <a name="trustedissuers"></a><span data-ttu-id="6e65d-101">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="6e65d-101">\<trustedIssuers></span></span>
<span data-ttu-id="6e65d-102">Configura la lista de certificados de emisor de confianza utilizado por el registro de nombres de emisores basada en la configuración (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span><span class="sxs-lookup"><span data-stu-id="6e65d-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="6e65d-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="6e65d-103">\<system.identityModel></span></span>  
<span data-ttu-id="6e65d-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6e65d-104">\<identityConfiguration></span></span>  
<span data-ttu-id="6e65d-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="6e65d-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="6e65d-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="6e65d-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="6e65d-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="6e65d-107">\<issuerNameRegistry></span></span>  
<span data-ttu-id="6e65d-108">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="6e65d-108">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e65d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e65d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e65d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6e65d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6e65d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6e65d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e65d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="6e65d-112">Attributes</span></span>  
 <span data-ttu-id="6e65d-113">Ninguna</span><span class="sxs-lookup"><span data-stu-id="6e65d-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6e65d-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6e65d-114">Child Elements</span></span>  
  
|<span data-ttu-id="6e65d-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e65d-115">Element</span></span>|<span data-ttu-id="6e65d-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e65d-116">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="6e65d-117">Agrega un certificado a la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="6e65d-117">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="6e65d-118">El certificado se especifica con el `thumbprint` atributo.</span><span class="sxs-lookup"><span data-stu-id="6e65d-118">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="6e65d-119">Este atributo es necesario y debe contener el formulario ASN.1 codificado la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="6e65d-119">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="6e65d-120">El `name` atributo es opcional y puede utilizarse para especificar un nombre descriptivo para el certificado.</span><span class="sxs-lookup"><span data-stu-id="6e65d-120">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="6e65d-121">Borra todos los certificados de la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="6e65d-121">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="6e65d-122">Quita un certificado de la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="6e65d-122">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="6e65d-123">El certificado se especifica con el `thumbprint` atributo.</span><span class="sxs-lookup"><span data-stu-id="6e65d-123">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="6e65d-124">Este atributo es necesario.</span><span class="sxs-lookup"><span data-stu-id="6e65d-124">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6e65d-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6e65d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="6e65d-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e65d-126">Element</span></span>|<span data-ttu-id="6e65d-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e65d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e65d-128">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="6e65d-128">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="6e65d-129">Configura el registro de nombre del emisor.</span><span class="sxs-lookup"><span data-stu-id="6e65d-129">Configures the issuer name registry.</span></span> <span data-ttu-id="6e65d-130">**Importante:**  El `type` atributo de la `<issuerNameRegistry>` elemento debe hacer referencia a la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> de clases para el `<trustedIssuers>` elemento sea válido.</span><span class="sxs-lookup"><span data-stu-id="6e65d-130">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e65d-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6e65d-131">Remarks</span></span>  
 <span data-ttu-id="6e65d-132">Windows Identity Foundation (WIF) proporciona una implementación única de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase de fábrica, el <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="6e65d-132">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="6e65d-133">El registro de nombre de configuración del emisor mantiene una lista de emisores de confianza que se carga desde la configuración.</span><span class="sxs-lookup"><span data-stu-id="6e65d-133">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="6e65d-134">La lista asocia cada nombre de emisor del certificado X.509 que se necesita para comprobar la firma de tokens generados por el emisor.</span><span class="sxs-lookup"><span data-stu-id="6e65d-134">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="6e65d-135">La lista de certificados de emisor de confianza se especifica en el `<trustedIssuers>` elemento.</span><span class="sxs-lookup"><span data-stu-id="6e65d-135">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="6e65d-136">Cada elemento de la lista asocia un nombre de emisor de tecla de acceso con el certificado X.509 que se necesita para comprobar la firma de tokens generados por ese emisor.</span><span class="sxs-lookup"><span data-stu-id="6e65d-136">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="6e65d-137">Certificados de confianza se especifican utilizando el ASN.1 formato codificado de la huella digital del certificado y se agregan a la colección mediante `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="6e65d-137">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="6e65d-138">Puede borrar o quitar de la lista de emisores (certificados) con el `<clear>` y `<remove>` elementos.</span><span class="sxs-lookup"><span data-stu-id="6e65d-138">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="6e65d-139">El `type` atributo de la `<issuerNameRegistry>` elemento debe hacer referencia a la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> de clases para el `<trustedIssuers>` elemento sea válido.</span><span class="sxs-lookup"><span data-stu-id="6e65d-139">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e65d-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e65d-140">Example</span></span>  
 <span data-ttu-id="6e65d-141">El siguiente XML muestra cómo especificar al emisor de la configuración en función de registro de nombres.</span><span class="sxs-lookup"><span data-stu-id="6e65d-141">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e65d-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e65d-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>

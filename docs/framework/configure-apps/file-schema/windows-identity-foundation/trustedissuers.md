---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 32aad3529ded6d0234b1bcb388ecbbc3b0a11c87
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944269"
---
# <a name="trustedissuers"></a><span data-ttu-id="43177-101">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="43177-101">\<trustedIssuers></span></span>
<span data-ttu-id="43177-102">Configura la lista de certificados de emisor de confianza utilizados por el registro de nombres de emisores basados en la<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>configuración ().</span><span class="sxs-lookup"><span data-stu-id="43177-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="43177-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="43177-103">\<system.identityModel></span></span>  
<span data-ttu-id="43177-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="43177-104">\<identityConfiguration></span></span>  
<span data-ttu-id="43177-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="43177-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="43177-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="43177-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="43177-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="43177-107">\<issuerNameRegistry></span></span>  
<span data-ttu-id="43177-108">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="43177-108">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43177-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43177-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43177-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="43177-110">Attributes and Elements</span></span>  
 <span data-ttu-id="43177-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="43177-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43177-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="43177-112">Attributes</span></span>  
 <span data-ttu-id="43177-113">None</span><span class="sxs-lookup"><span data-stu-id="43177-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="43177-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="43177-114">Child Elements</span></span>  
  
|<span data-ttu-id="43177-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="43177-115">Element</span></span>|<span data-ttu-id="43177-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="43177-116">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="43177-117">Agrega un certificado a la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="43177-117">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="43177-118">El certificado se especifica con el `thumbprint` atributo.</span><span class="sxs-lookup"><span data-stu-id="43177-118">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="43177-119">Este atributo es necesario y debe contener la forma de codificación ASN. 1 de la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="43177-119">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="43177-120">El `name` atributo es opcional y se puede usar para especificar un nombre descriptivo para el certificado.</span><span class="sxs-lookup"><span data-stu-id="43177-120">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="43177-121">Borra todos los certificados de la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="43177-121">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="43177-122">Quita un certificado de la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="43177-122">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="43177-123">El certificado se especifica con el `thumbprint` atributo.</span><span class="sxs-lookup"><span data-stu-id="43177-123">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="43177-124">Este atributo es necesario.</span><span class="sxs-lookup"><span data-stu-id="43177-124">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="43177-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="43177-125">Parent Elements</span></span>  
  
|<span data-ttu-id="43177-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="43177-126">Element</span></span>|<span data-ttu-id="43177-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="43177-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43177-128">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="43177-128">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="43177-129">Configura el registro de nombres de emisores.</span><span class="sxs-lookup"><span data-stu-id="43177-129">Configures the issuer name registry.</span></span> <span data-ttu-id="43177-130">**Importante:**  El `type` atributo <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `<trustedIssuers>` del elemento debe hacer referencia a la clase para que el elemento sea válido. `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="43177-130">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43177-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43177-131">Remarks</span></span>  
 <span data-ttu-id="43177-132">Windows Identity Foundation (WIF) proporciona una implementación única de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase desde el cuadro, la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="43177-132">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="43177-133">El registro de nombres de emisores de configuración mantiene una lista de emisores de confianza que se cargan desde la configuración.</span><span class="sxs-lookup"><span data-stu-id="43177-133">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="43177-134">La lista asocia cada nombre de emisor con el certificado X. 509 necesario para comprobar la firma de los tokens generados por el emisor.</span><span class="sxs-lookup"><span data-stu-id="43177-134">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="43177-135">La lista de certificados de emisor de confianza se especifica en `<trustedIssuers>` el elemento.</span><span class="sxs-lookup"><span data-stu-id="43177-135">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="43177-136">Cada elemento de la lista asocia un nombre de emisor de mnemotécnico con el certificado X. 509 necesario para comprobar la firma de los tokens generados por dicho emisor.</span><span class="sxs-lookup"><span data-stu-id="43177-136">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="43177-137">Los certificados de confianza se especifican con el formato ASN. 1 codificado de la huella digital del certificado y se agregan a la colección mediante `<add>` el elemento.</span><span class="sxs-lookup"><span data-stu-id="43177-137">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="43177-138">Puede borrar o quitar emisores (certificados) de la lista mediante los `<clear>` elementos y. `<remove>`</span><span class="sxs-lookup"><span data-stu-id="43177-138">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="43177-139">El `type` atributo <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `<trustedIssuers>` del elemento debe hacer referencia a la clase para que el elemento sea válido. `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="43177-139">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43177-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43177-140">Example</span></span>  
 <span data-ttu-id="43177-141">El siguiente XML muestra cómo especificar el registro de nombres de emisor basado en la configuración.</span><span class="sxs-lookup"><span data-stu-id="43177-141">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="43177-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="43177-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>

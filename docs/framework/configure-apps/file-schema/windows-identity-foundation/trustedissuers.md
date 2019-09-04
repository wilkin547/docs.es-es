---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 50fc7194823fb0c5c426fb54ffd50b17c3714ed9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251754"
---
# <a name="trustedissuers"></a><span data-ttu-id="10e29-101">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="10e29-101">\<trustedIssuers></span></span>
<span data-ttu-id="10e29-102">Configura la lista de certificados de emisor de confianza utilizados por el registro de nombres de emisores basados en la<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>configuración ().</span><span class="sxs-lookup"><span data-stu-id="10e29-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
<span data-ttu-id="10e29-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="10e29-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="10e29-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="10e29-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="10e29-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="10e29-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="10e29-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="10e29-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="10e29-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="10e29-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="10e29-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuerNameRegistry**](issuernameregistry.md)</span><span class="sxs-lookup"><span data-stu-id="10e29-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerNameRegistry>**](issuernameregistry.md)</span></span>\
<span data-ttu-id="10e29-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> trustedIssuers**</span><span class="sxs-lookup"><span data-stu-id="10e29-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trustedIssuers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10e29-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10e29-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10e29-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="10e29-111">Attributes and Elements</span></span>  
 <span data-ttu-id="10e29-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="10e29-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10e29-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="10e29-113">Attributes</span></span>  
 <span data-ttu-id="10e29-114">None</span><span class="sxs-lookup"><span data-stu-id="10e29-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="10e29-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="10e29-115">Child Elements</span></span>  
  
|<span data-ttu-id="10e29-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="10e29-116">Element</span></span>|<span data-ttu-id="10e29-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="10e29-117">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="10e29-118">Agrega un certificado a la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="10e29-118">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="10e29-119">El certificado se especifica con el `thumbprint` atributo.</span><span class="sxs-lookup"><span data-stu-id="10e29-119">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="10e29-120">Este atributo es necesario y debe contener la forma de codificación ASN. 1 de la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="10e29-120">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="10e29-121">El `name` atributo es opcional y se puede usar para especificar un nombre descriptivo para el certificado.</span><span class="sxs-lookup"><span data-stu-id="10e29-121">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="10e29-122">Borra todos los certificados de la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="10e29-122">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="10e29-123">Quita un certificado de la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="10e29-123">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="10e29-124">El certificado se especifica con el `thumbprint` atributo.</span><span class="sxs-lookup"><span data-stu-id="10e29-124">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="10e29-125">Este atributo es necesario.</span><span class="sxs-lookup"><span data-stu-id="10e29-125">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="10e29-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="10e29-126">Parent Elements</span></span>  
  
|<span data-ttu-id="10e29-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="10e29-127">Element</span></span>|<span data-ttu-id="10e29-128">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="10e29-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10e29-129">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="10e29-129">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="10e29-130">Configura el registro de nombres de emisores.</span><span class="sxs-lookup"><span data-stu-id="10e29-130">Configures the issuer name registry.</span></span> <span data-ttu-id="10e29-131">**Importante:**  El `type` atributo <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `<trustedIssuers>` del elemento debe hacer referencia a la clase para que el elemento sea válido. `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="10e29-131">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10e29-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="10e29-132">Remarks</span></span>  
 <span data-ttu-id="10e29-133">Windows Identity Foundation (WIF) proporciona una implementación única de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase desde el cuadro, la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="10e29-133">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="10e29-134">El registro de nombres de emisores de configuración mantiene una lista de emisores de confianza que se cargan desde la configuración.</span><span class="sxs-lookup"><span data-stu-id="10e29-134">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="10e29-135">La lista asocia cada nombre de emisor con el certificado X. 509 necesario para comprobar la firma de los tokens generados por el emisor.</span><span class="sxs-lookup"><span data-stu-id="10e29-135">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="10e29-136">La lista de certificados de emisor de confianza se especifica en `<trustedIssuers>` el elemento.</span><span class="sxs-lookup"><span data-stu-id="10e29-136">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="10e29-137">Cada elemento de la lista asocia un nombre de emisor de mnemotécnico con el certificado X. 509 necesario para comprobar la firma de los tokens generados por dicho emisor.</span><span class="sxs-lookup"><span data-stu-id="10e29-137">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="10e29-138">Los certificados de confianza se especifican con el formato ASN. 1 codificado de la huella digital del certificado y se agregan a la colección mediante `<add>` el elemento.</span><span class="sxs-lookup"><span data-stu-id="10e29-138">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="10e29-139">Puede borrar o quitar emisores (certificados) de la lista mediante los `<clear>` elementos y. `<remove>`</span><span class="sxs-lookup"><span data-stu-id="10e29-139">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="10e29-140">El `type` atributo <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> `<trustedIssuers>` del elemento debe hacer referencia a la clase para que el elemento sea válido. `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="10e29-140">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10e29-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10e29-141">Example</span></span>  
 <span data-ttu-id="10e29-142">El siguiente XML muestra cómo especificar el registro de nombres de emisor basado en la configuración.</span><span class="sxs-lookup"><span data-stu-id="10e29-142">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="10e29-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="10e29-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>

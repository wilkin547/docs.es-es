---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 50fc7194823fb0c5c426fb54ffd50b17c3714ed9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251754"
---
# \<trustedIssuers>
<span data-ttu-id="5eccb-101">Configura la lista de certificados de emisor de confianza utilizados por el registro de nombres de emisores basados en la configuración ( <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> ).</span><span class="sxs-lookup"><span data-stu-id="5eccb-101">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerNameRegistry>**](issuernameregistry.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trustedIssuers>**  
  
## <a name="syntax"></a><span data-ttu-id="5eccb-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5eccb-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5eccb-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5eccb-103">Attributes and Elements</span></span>  
 <span data-ttu-id="5eccb-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5eccb-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5eccb-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="5eccb-105">Attributes</span></span>  
 <span data-ttu-id="5eccb-106">None</span><span class="sxs-lookup"><span data-stu-id="5eccb-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5eccb-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5eccb-107">Child Elements</span></span>  
  
|<span data-ttu-id="5eccb-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="5eccb-108">Element</span></span>|<span data-ttu-id="5eccb-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="5eccb-109">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="5eccb-110">Agrega un certificado a la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="5eccb-110">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="5eccb-111">El certificado se especifica con el `thumbprint` atributo.</span><span class="sxs-lookup"><span data-stu-id="5eccb-111">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="5eccb-112">Este atributo es necesario y debe contener la forma de codificación ASN. 1 de la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="5eccb-112">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="5eccb-113">El `name` atributo es opcional y se puede usar para especificar un nombre descriptivo para el certificado.</span><span class="sxs-lookup"><span data-stu-id="5eccb-113">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="5eccb-114">Borra todos los certificados de la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="5eccb-114">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="5eccb-115">Quita un certificado de la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="5eccb-115">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="5eccb-116">El certificado se especifica con el `thumbprint` atributo.</span><span class="sxs-lookup"><span data-stu-id="5eccb-116">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="5eccb-117">Este atributo es necesario.</span><span class="sxs-lookup"><span data-stu-id="5eccb-117">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5eccb-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5eccb-118">Parent Elements</span></span>  
  
|<span data-ttu-id="5eccb-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="5eccb-119">Element</span></span>|<span data-ttu-id="5eccb-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="5eccb-120">Description</span></span>|  
|-------------|-----------------|  
|[\<issuerNameRegistry>](issuernameregistry.md)|<span data-ttu-id="5eccb-121">Configura el registro de nombres de emisores.</span><span class="sxs-lookup"><span data-stu-id="5eccb-121">Configures the issuer name registry.</span></span> <span data-ttu-id="5eccb-122">**Importante:**  El `type` atributo del `<issuerNameRegistry>` elemento debe hacer referencia <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> a la clase para `<trustedIssuers>` que el elemento sea válido.</span><span class="sxs-lookup"><span data-stu-id="5eccb-122">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5eccb-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5eccb-123">Remarks</span></span>  
 <span data-ttu-id="5eccb-124">Windows Identity Foundation (WIF) proporciona una implementación única de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase desde el cuadro, la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="5eccb-124">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="5eccb-125">El registro de nombres de emisores de configuración mantiene una lista de emisores de confianza que se cargan desde la configuración.</span><span class="sxs-lookup"><span data-stu-id="5eccb-125">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="5eccb-126">La lista asocia cada nombre de emisor con el certificado X. 509 necesario para comprobar la firma de los tokens generados por el emisor.</span><span class="sxs-lookup"><span data-stu-id="5eccb-126">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="5eccb-127">La lista de certificados de emisor de confianza se especifica en el `<trustedIssuers>` elemento.</span><span class="sxs-lookup"><span data-stu-id="5eccb-127">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="5eccb-128">Cada elemento de la lista asocia un nombre de emisor de mnemotécnico con el certificado X. 509 necesario para comprobar la firma de los tokens generados por dicho emisor.</span><span class="sxs-lookup"><span data-stu-id="5eccb-128">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="5eccb-129">Los certificados de confianza se especifican con el formato ASN. 1 codificado de la huella digital del certificado y se agregan a la colección mediante el `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="5eccb-129">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="5eccb-130">Puede borrar o quitar emisores (certificados) de la lista mediante los `<clear>` `<remove>` elementos y.</span><span class="sxs-lookup"><span data-stu-id="5eccb-130">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="5eccb-131">El `type` atributo del `<issuerNameRegistry>` elemento debe hacer referencia <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> a la clase para `<trustedIssuers>` que el elemento sea válido.</span><span class="sxs-lookup"><span data-stu-id="5eccb-131">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5eccb-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5eccb-132">Example</span></span>  
 <span data-ttu-id="5eccb-133">El siguiente XML muestra cómo especificar el registro de nombres de emisor basado en la configuración.</span><span class="sxs-lookup"><span data-stu-id="5eccb-133">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5eccb-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5eccb-134">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>

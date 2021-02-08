---
description: 'Más información acerca de: <trustedIssuers>'
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 8789eaa38666e22f6a58b3178103aef4408677b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786517"
---
# \<trustedIssuers>

<span data-ttu-id="1a01a-102">Configura la lista de certificados de emisor de confianza utilizados por el registro de nombres de emisores basados en la configuración ( <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> ).</span><span class="sxs-lookup"><span data-stu-id="1a01a-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerNameRegistry>**](issuernameregistry.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trustedIssuers>**  
  
## <a name="syntax"></a><span data-ttu-id="1a01a-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a01a-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a01a-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1a01a-104">Attributes and Elements</span></span>  

 <span data-ttu-id="1a01a-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1a01a-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a01a-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="1a01a-106">Attributes</span></span>  

 <span data-ttu-id="1a01a-107">None</span><span class="sxs-lookup"><span data-stu-id="1a01a-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1a01a-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1a01a-108">Child Elements</span></span>  
  
|<span data-ttu-id="1a01a-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="1a01a-109">Element</span></span>|<span data-ttu-id="1a01a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1a01a-110">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="1a01a-111">Agrega un certificado a la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="1a01a-111">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="1a01a-112">El certificado se especifica con el `thumbprint` atributo.</span><span class="sxs-lookup"><span data-stu-id="1a01a-112">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="1a01a-113">Este atributo es necesario y debe contener la forma de codificación ASN. 1 de la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="1a01a-113">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="1a01a-114">El `name` atributo es opcional y se puede usar para especificar un nombre descriptivo para el certificado.</span><span class="sxs-lookup"><span data-stu-id="1a01a-114">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="1a01a-115">Borra todos los certificados de la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="1a01a-115">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="1a01a-116">Quita un certificado de la colección de emisores de confianza.</span><span class="sxs-lookup"><span data-stu-id="1a01a-116">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="1a01a-117">El certificado se especifica con el `thumbprint` atributo.</span><span class="sxs-lookup"><span data-stu-id="1a01a-117">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="1a01a-118">Este atributo es necesario.</span><span class="sxs-lookup"><span data-stu-id="1a01a-118">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1a01a-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1a01a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1a01a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="1a01a-120">Element</span></span>|<span data-ttu-id="1a01a-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="1a01a-121">Description</span></span>|  
|-------------|-----------------|  
|[\<issuerNameRegistry>](issuernameregistry.md)|<span data-ttu-id="1a01a-122">Configura el registro de nombres de emisores.</span><span class="sxs-lookup"><span data-stu-id="1a01a-122">Configures the issuer name registry.</span></span> <span data-ttu-id="1a01a-123">**Importante:**  El `type` atributo del `<issuerNameRegistry>` elemento debe hacer referencia <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> a la clase para `<trustedIssuers>` que el elemento sea válido.</span><span class="sxs-lookup"><span data-stu-id="1a01a-123">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a01a-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1a01a-124">Remarks</span></span>  

 <span data-ttu-id="1a01a-125">Windows Identity Foundation (WIF) proporciona una implementación única de la <xref:System.IdentityModel.Tokens.IssuerNameRegistry> clase desde el cuadro, la <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> clase.</span><span class="sxs-lookup"><span data-stu-id="1a01a-125">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="1a01a-126">El registro de nombres de emisores de configuración mantiene una lista de emisores de confianza que se cargan desde la configuración.</span><span class="sxs-lookup"><span data-stu-id="1a01a-126">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="1a01a-127">La lista asocia cada nombre de emisor con el certificado X. 509 necesario para comprobar la firma de los tokens generados por el emisor.</span><span class="sxs-lookup"><span data-stu-id="1a01a-127">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="1a01a-128">La lista de certificados de emisor de confianza se especifica en el `<trustedIssuers>` elemento.</span><span class="sxs-lookup"><span data-stu-id="1a01a-128">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="1a01a-129">Cada elemento de la lista asocia un nombre de emisor de mnemotécnico con el certificado X. 509 necesario para comprobar la firma de los tokens generados por dicho emisor.</span><span class="sxs-lookup"><span data-stu-id="1a01a-129">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="1a01a-130">Los certificados de confianza se especifican con el formato ASN. 1 codificado de la huella digital del certificado y se agregan a la colección mediante el `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="1a01a-130">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="1a01a-131">Puede borrar o quitar emisores (certificados) de la lista mediante los `<clear>` `<remove>` elementos y.</span><span class="sxs-lookup"><span data-stu-id="1a01a-131">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="1a01a-132">El `type` atributo del `<issuerNameRegistry>` elemento debe hacer referencia <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> a la clase para `<trustedIssuers>` que el elemento sea válido.</span><span class="sxs-lookup"><span data-stu-id="1a01a-132">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a01a-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1a01a-133">Example</span></span>  

 <span data-ttu-id="1a01a-134">El siguiente XML muestra cómo especificar el registro de nombres de emisor basado en la configuración.</span><span class="sxs-lookup"><span data-stu-id="1a01a-134">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a01a-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a01a-135">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>

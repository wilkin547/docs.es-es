---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: b27f337189a7d0b66ffd38e032b5eb864e5094a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152637"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="5c48e-101">\<> samlSecurityTokenRequirement</span><span class="sxs-lookup"><span data-stu-id="5c48e-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="5c48e-102">Proporciona configuración <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> para la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase, la clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="5c48e-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="5c48e-103">Representado por <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> la clase.</span><span class="sxs-lookup"><span data-stu-id="5c48e-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
<span data-ttu-id="5c48e-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5c48e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5c48e-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="5c48e-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="5c48e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="5c48e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="5c48e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="5c48e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="5c48e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<añadir>**](add.md)</span><span class="sxs-lookup"><span data-stu-id="5c48e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="5c48e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>samlSecurityTokenRequirement**</span><span class="sxs-lookup"><span data-stu-id="5c48e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c48e-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c48e-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c48e-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5c48e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5c48e-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5c48e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c48e-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="5c48e-113">Attributes</span></span>  
  
|<span data-ttu-id="5c48e-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="5c48e-114">Attribute</span></span>|<span data-ttu-id="5c48e-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c48e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c48e-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="5c48e-116">mapToWindows</span></span>|<span data-ttu-id="5c48e-117">Especifica si el controlador de tokens debe asignar el token de validación a una cuenta de Windows mediante la notificación UPN entrante.</span><span class="sxs-lookup"><span data-stu-id="5c48e-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="5c48e-118">El valor predeterminado es "false".</span><span class="sxs-lookup"><span data-stu-id="5c48e-118">The default is "false".</span></span>|  
|<span data-ttu-id="5c48e-119">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="5c48e-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="5c48e-120">Valor <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> que especifica el modo de revocación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="5c48e-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="5c48e-121">El valor predeterminado es "Online".</span><span class="sxs-lookup"><span data-stu-id="5c48e-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="5c48e-122">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="5c48e-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="5c48e-123">Valor <xref:System.ServiceModel.Security.X509CertificateValidationMode> que especifica el modo de validación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="5c48e-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="5c48e-124">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="5c48e-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="5c48e-125">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="5c48e-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="5c48e-126">Valor <xref:System.Security.Cryptography.X509Certificates.StoreLocation> que especifica el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="5c48e-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="5c48e-127">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="5c48e-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="5c48e-128">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="5c48e-128">issuerCertificateValidator</span></span>|<span data-ttu-id="5c48e-129">Un tipo personalizado que <xref:System.IdentityModel.Selectors.X509CertificateValidator>deriva de .</span><span class="sxs-lookup"><span data-stu-id="5c48e-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="5c48e-130">Si `issuerCertificateValidationMode` el atributo es "Custom", se utiliza una instancia de este tipo para la validación del certificado de emisor.</span><span class="sxs-lookup"><span data-stu-id="5c48e-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c48e-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5c48e-131">Child Elements</span></span>  
  
|<span data-ttu-id="5c48e-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c48e-132">Element</span></span>|<span data-ttu-id="5c48e-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c48e-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c48e-134">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="5c48e-134">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="5c48e-135">Establece el tipo de <xref:System.Security.Principal.IIdentity.Name%2A> notificación que especifica la propiedad.</span><span class="sxs-lookup"><span data-stu-id="5c48e-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="5c48e-136">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="5c48e-136">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="5c48e-137">Especifica el tipo de notificación que define <xref:System.Security.Claims.ClaimsIdentity> las notificaciones <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> de tipo de rol en la colección de objetos devueltos por el método del controlador de tokens.</span><span class="sxs-lookup"><span data-stu-id="5c48e-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5c48e-138">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5c48e-138">Parent Elements</span></span>  
  
|<span data-ttu-id="5c48e-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c48e-139">Element</span></span>|<span data-ttu-id="5c48e-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c48e-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c48e-141">\<añadir></span><span class="sxs-lookup"><span data-stu-id="5c48e-141">\<add></span></span>](add.md)|<span data-ttu-id="5c48e-142">Agrega el controlador de token de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="5c48e-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c48e-143">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5c48e-143">Remarks</span></span>  
 <span data-ttu-id="5c48e-144">El `<samlSecurityTokenRequirement>` elemento se representa <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> mediante la clase en el `SamlSecurityTokenRequirement` modelo de <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> objetos y se utiliza para configurar la propiedad en un <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>archivo .</span><span class="sxs-lookup"><span data-stu-id="5c48e-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c48e-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c48e-145">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```

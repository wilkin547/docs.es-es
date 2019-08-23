---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: df259398beb242ea95efb248d6b5140b38ca3c45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942488"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="aa48b-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="aa48b-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="aa48b-102">Proporciona la configuración para <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> la clase, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="aa48b-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="aa48b-103">Se representa mediante <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> la clase.</span><span class="sxs-lookup"><span data-stu-id="aa48b-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="aa48b-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="aa48b-104">\<system.identityModel></span></span>  
<span data-ttu-id="aa48b-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="aa48b-105">\<identityConfiguration></span></span>  
<span data-ttu-id="aa48b-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="aa48b-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="aa48b-107">\<add></span><span class="sxs-lookup"><span data-stu-id="aa48b-107">\<add></span></span>  
<span data-ttu-id="aa48b-108">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="aa48b-108">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa48b-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa48b-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa48b-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="aa48b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="aa48b-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="aa48b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa48b-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="aa48b-112">Attributes</span></span>  
  
|<span data-ttu-id="aa48b-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="aa48b-113">Attribute</span></span>|<span data-ttu-id="aa48b-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="aa48b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa48b-115">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="aa48b-115">mapToWindows</span></span>|<span data-ttu-id="aa48b-116">Especifica si el controlador de token debe asignar el token de validación a una cuenta de Windows mediante la notificaciones de UPN entrantes.</span><span class="sxs-lookup"><span data-stu-id="aa48b-116">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="aa48b-117">El valor predeterminado es "false".</span><span class="sxs-lookup"><span data-stu-id="aa48b-117">The default is "false".</span></span>|  
|<span data-ttu-id="aa48b-118">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="aa48b-118">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="aa48b-119"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Valor que especifica el modo de revocación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="aa48b-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="aa48b-120">El valor predeterminado es "online".</span><span class="sxs-lookup"><span data-stu-id="aa48b-120">The default value is "Online".</span></span>|  
|<span data-ttu-id="aa48b-121">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="aa48b-121">issuerCertificateValidationMode</span></span>|<span data-ttu-id="aa48b-122"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Valor que especifica el modo de validación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="aa48b-122">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="aa48b-123">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="aa48b-123">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="aa48b-124">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="aa48b-124">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="aa48b-125"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valor que especifica el almacén de certificados X. 509.</span><span class="sxs-lookup"><span data-stu-id="aa48b-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="aa48b-126">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="aa48b-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="aa48b-127">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="aa48b-127">issuerCertificateValidator</span></span>|<span data-ttu-id="aa48b-128">Un tipo personalizado que se deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="aa48b-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="aa48b-129">Si el `issuerCertificateValidationMode` atributo es "Custom", se usa una instancia de este tipo para la validación del certificado del emisor.</span><span class="sxs-lookup"><span data-stu-id="aa48b-129">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa48b-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="aa48b-130">Child Elements</span></span>  
  
|<span data-ttu-id="aa48b-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="aa48b-131">Element</span></span>|<span data-ttu-id="aa48b-132">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="aa48b-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa48b-133">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="aa48b-133">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="aa48b-134">Establece el tipo de demanda que especifica <xref:System.Security.Principal.IIdentity.Name%2A> la propiedad.</span><span class="sxs-lookup"><span data-stu-id="aa48b-134">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="aa48b-135">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="aa48b-135">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="aa48b-136">Especifica el tipo de notificación que define las notificaciones de tipo de rol <xref:System.Security.Claims.ClaimsIdentity> en la colección de <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> objetos devuelta por el método del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="aa48b-136">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aa48b-137">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="aa48b-137">Parent Elements</span></span>  
  
|<span data-ttu-id="aa48b-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="aa48b-138">Element</span></span>|<span data-ttu-id="aa48b-139">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="aa48b-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa48b-140">\<add></span><span class="sxs-lookup"><span data-stu-id="aa48b-140">\<add></span></span>](add.md)|<span data-ttu-id="aa48b-141">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="aa48b-141">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa48b-142">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aa48b-142">Remarks</span></span>  
 <span data-ttu-id="aa48b-143">La `<samlSecurityTokenRequirement>` <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> clase representa el elemento en el modelo de objetos y se usa para <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> configurar la `SamlSecurityTokenRequirement` propiedad en o <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="aa48b-143">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa48b-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa48b-144">Example</span></span>  
  
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

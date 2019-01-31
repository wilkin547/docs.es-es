---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: e1b8acd48ee185b3c6c50f70321bb9ca66e8e02b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284627"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="595fc-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="595fc-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="595fc-102">Proporciona la configuración de la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (clase), el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="595fc-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="595fc-103">Representado por la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> clase.</span><span class="sxs-lookup"><span data-stu-id="595fc-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="595fc-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="595fc-104">\<system.identityModel></span></span>  
<span data-ttu-id="595fc-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="595fc-105">\<identityConfiguration></span></span>  
<span data-ttu-id="595fc-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="595fc-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="595fc-107">\<add></span><span class="sxs-lookup"><span data-stu-id="595fc-107">\<add></span></span>  
<span data-ttu-id="595fc-108">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="595fc-108">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="595fc-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="595fc-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="595fc-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="595fc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="595fc-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="595fc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="595fc-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="595fc-112">Attributes</span></span>  
  
|<span data-ttu-id="595fc-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="595fc-113">Attribute</span></span>|<span data-ttu-id="595fc-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="595fc-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="595fc-115">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="595fc-115">mapToWindows</span></span>|<span data-ttu-id="595fc-116">Especifica si el controlador de token debe asignar el token de validación a una cuenta de Windows mediante el uso de la notificación UPN entrante.</span><span class="sxs-lookup"><span data-stu-id="595fc-116">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="595fc-117">El valor predeterminado es "false".</span><span class="sxs-lookup"><span data-stu-id="595fc-117">The default is "false".</span></span>|  
|<span data-ttu-id="595fc-118">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="595fc-118">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="595fc-119">Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valor que especifica el modo de revocación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="595fc-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="595fc-120">El valor predeterminado es "Online".</span><span class="sxs-lookup"><span data-stu-id="595fc-120">The default value is "Online".</span></span>|  
|<span data-ttu-id="595fc-121">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="595fc-121">issuerCertificateValidationMode</span></span>|<span data-ttu-id="595fc-122">Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valor que especifica el modo de validación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="595fc-122">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="595fc-123">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="595fc-123">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="595fc-124">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="595fc-124">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="595fc-125">Un <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valor que especifica el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="595fc-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="595fc-126">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="595fc-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="595fc-127">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="595fc-127">issuerCertificateValidator</span></span>|<span data-ttu-id="595fc-128">Un tipo personalizado que se deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="595fc-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="595fc-129">Si el `issuerCertificateValidationMode` el atributo es "Custom", se utiliza una instancia de este tipo de validación del certificado del emisor.</span><span class="sxs-lookup"><span data-stu-id="595fc-129">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="595fc-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="595fc-130">Child Elements</span></span>  
  
|<span data-ttu-id="595fc-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="595fc-131">Element</span></span>|<span data-ttu-id="595fc-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="595fc-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="595fc-133">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="595fc-133">\<nameClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|<span data-ttu-id="595fc-134">Establece el tipo de notificación que especifica el <xref:System.Security.Principal.IIdentity.Name%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="595fc-134">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="595fc-135">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="595fc-135">\<roleClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|<span data-ttu-id="595fc-136">Especifica el tipo de notificación que define las notificaciones de tipo de rol en la colección de <xref:System.Security.Claims.ClaimsIdentity> los objetos devueltos por la <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="595fc-136">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="595fc-137">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="595fc-137">Parent Elements</span></span>  
  
|<span data-ttu-id="595fc-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="595fc-138">Element</span></span>|<span data-ttu-id="595fc-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="595fc-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="595fc-140">\<add></span><span class="sxs-lookup"><span data-stu-id="595fc-140">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="595fc-141">Agrega el controlador de token de seguridad especificado a la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="595fc-141">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="595fc-142">Comentarios</span><span class="sxs-lookup"><span data-stu-id="595fc-142">Remarks</span></span>  
 <span data-ttu-id="595fc-143">El `<samlSecurityTokenRequirement>` elemento representado por la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> en el modelo de objetos de clase y se usa para configurar el `SamlSecurityTokenRequirement` propiedad en un <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> o un <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="595fc-143">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="595fc-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="595fc-144">Example</span></span>  
  
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

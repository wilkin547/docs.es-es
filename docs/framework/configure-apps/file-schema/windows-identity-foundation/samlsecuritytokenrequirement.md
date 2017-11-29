---
title: '&lt;samlSecurityTokenRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: e0d8d467c2636f5ce95cf5fed189ae00c3ca75fb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltsamlsecuritytokenrequirementgt"></a><span data-ttu-id="6b287-102">&lt;samlSecurityTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="6b287-102">&lt;samlSecurityTokenRequirement&gt;</span></span>
<span data-ttu-id="6b287-103">Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (clase), el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="6b287-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="6b287-104">Representado por la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> clase.</span><span class="sxs-lookup"><span data-stu-id="6b287-104">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="6b287-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="6b287-105">\<system.identityModel></span></span>  
<span data-ttu-id="6b287-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="6b287-106">\<identityConfiguration></span></span>  
<span data-ttu-id="6b287-107">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="6b287-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="6b287-108">\<add></span><span class="sxs-lookup"><span data-stu-id="6b287-108">\<add></span></span>  
<span data-ttu-id="6b287-109">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="6b287-109">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b287-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b287-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b287-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6b287-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6b287-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6b287-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b287-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="6b287-113">Attributes</span></span>  
  
|<span data-ttu-id="6b287-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="6b287-114">Attribute</span></span>|<span data-ttu-id="6b287-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b287-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b287-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="6b287-116">mapToWindows</span></span>|<span data-ttu-id="6b287-117">Especifica si el controlador de token debe asignar el token de validación a una cuenta de Windows mediante la notificación UPN entrante.</span><span class="sxs-lookup"><span data-stu-id="6b287-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="6b287-118">El valor predeterminado es "false".</span><span class="sxs-lookup"><span data-stu-id="6b287-118">The default is "false".</span></span>|  
|<span data-ttu-id="6b287-119">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="6b287-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="6b287-120">Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valor que especifica el modo de revocación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="6b287-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="6b287-121">El valor predeterminado es "Online".</span><span class="sxs-lookup"><span data-stu-id="6b287-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="6b287-122">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="6b287-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="6b287-123">Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valor que especifica el modo de validación que se utilizará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="6b287-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="6b287-124">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="6b287-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="6b287-125">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="6b287-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="6b287-126">Un <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valor que especifica el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="6b287-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="6b287-127">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="6b287-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="6b287-128">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="6b287-128">issuerCertificateValidator</span></span>|<span data-ttu-id="6b287-129">Un tipo personalizado que deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="6b287-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="6b287-130">Si el `issuerCertificateValidationMode` atributo es "Custom", se utiliza una instancia de este tipo de validación de certificados de emisor.</span><span class="sxs-lookup"><span data-stu-id="6b287-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b287-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6b287-131">Child Elements</span></span>  
  
|<span data-ttu-id="6b287-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="6b287-132">Element</span></span>|<span data-ttu-id="6b287-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b287-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b287-134">\<nameClaimType ></span><span class="sxs-lookup"><span data-stu-id="6b287-134">\<nameClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|<span data-ttu-id="6b287-135">Establece el tipo de notificación que especifica la <xref:System.Security.Principal.IIdentity.Name%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="6b287-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="6b287-136">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="6b287-136">\<roleClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|<span data-ttu-id="6b287-137">Especifica el tipo de notificación que define las notificaciones de tipo de rol de la colección de <xref:System.Security.Claims.ClaimsIdentity> objetos devueltos por la <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="6b287-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6b287-138">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6b287-138">Parent Elements</span></span>  
  
|<span data-ttu-id="6b287-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="6b287-139">Element</span></span>|<span data-ttu-id="6b287-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b287-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b287-141">\<add></span><span class="sxs-lookup"><span data-stu-id="6b287-141">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="6b287-142">Agrega el controlador de token de seguridad especificado a la colección de controlador de token.</span><span class="sxs-lookup"><span data-stu-id="6b287-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b287-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6b287-143">Remarks</span></span>  
 <span data-ttu-id="6b287-144">El `<samlSecurityTokenRequirement>` elemento representado por la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> en el modelo de objetos de clase y se usa para configurar la `SamlSecurityTokenRequirement` propiedad en un <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> o un <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="6b287-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b287-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b287-145">Example</span></span>  
  
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

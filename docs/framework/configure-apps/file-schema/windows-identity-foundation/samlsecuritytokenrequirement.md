---
title: '&lt;samlSecurityTokenRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: c9856dae971691baf9dabe845bdecae90cbc8aa5
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2018
ms.locfileid: "49314858"
---
# <a name="ltsamlsecuritytokenrequirementgt"></a><span data-ttu-id="5ffe9-102">&lt;samlSecurityTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="5ffe9-102">&lt;samlSecurityTokenRequirement&gt;</span></span>
<span data-ttu-id="5ffe9-103">Proporciona la configuración de la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (clase), el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="5ffe9-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="5ffe9-104">Representado por la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> clase.</span><span class="sxs-lookup"><span data-stu-id="5ffe9-104">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="5ffe9-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="5ffe9-105">\<system.identityModel></span></span>  
<span data-ttu-id="5ffe9-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="5ffe9-106">\<identityConfiguration></span></span>  
<span data-ttu-id="5ffe9-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="5ffe9-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="5ffe9-108">\<add></span><span class="sxs-lookup"><span data-stu-id="5ffe9-108">\<add></span></span>  
<span data-ttu-id="5ffe9-109">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="5ffe9-109">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ffe9-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ffe9-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ffe9-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5ffe9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5ffe9-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5ffe9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ffe9-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="5ffe9-113">Attributes</span></span>  
  
|<span data-ttu-id="5ffe9-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="5ffe9-114">Attribute</span></span>|<span data-ttu-id="5ffe9-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ffe9-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5ffe9-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="5ffe9-116">mapToWindows</span></span>|<span data-ttu-id="5ffe9-117">Especifica si el controlador de token debe asignar el token de validación a una cuenta de Windows mediante el uso de la notificación UPN entrante.</span><span class="sxs-lookup"><span data-stu-id="5ffe9-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="5ffe9-118">El valor predeterminado es "false".</span><span class="sxs-lookup"><span data-stu-id="5ffe9-118">The default is "false".</span></span>|  
|<span data-ttu-id="5ffe9-119">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="5ffe9-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="5ffe9-120">Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valor que especifica el modo de revocación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="5ffe9-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="5ffe9-121">El valor predeterminado es "Online".</span><span class="sxs-lookup"><span data-stu-id="5ffe9-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="5ffe9-122">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="5ffe9-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="5ffe9-123">Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valor que especifica el modo de validación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="5ffe9-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="5ffe9-124">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="5ffe9-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="5ffe9-125">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="5ffe9-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="5ffe9-126">Un <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valor que especifica el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="5ffe9-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="5ffe9-127">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="5ffe9-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="5ffe9-128">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="5ffe9-128">issuerCertificateValidator</span></span>|<span data-ttu-id="5ffe9-129">Un tipo personalizado que se deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="5ffe9-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="5ffe9-130">Si el `issuerCertificateValidationMode` el atributo es "Custom", se utiliza una instancia de este tipo de validación del certificado del emisor.</span><span class="sxs-lookup"><span data-stu-id="5ffe9-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ffe9-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5ffe9-131">Child Elements</span></span>  
  
|<span data-ttu-id="5ffe9-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="5ffe9-132">Element</span></span>|<span data-ttu-id="5ffe9-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ffe9-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ffe9-134">\<nameClaimType ></span><span class="sxs-lookup"><span data-stu-id="5ffe9-134">\<nameClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|<span data-ttu-id="5ffe9-135">Establece el tipo de notificación que especifica el <xref:System.Security.Principal.IIdentity.Name%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="5ffe9-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="5ffe9-136">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="5ffe9-136">\<roleClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|<span data-ttu-id="5ffe9-137">Especifica el tipo de notificación que define las notificaciones de tipo de rol en la colección de <xref:System.Security.Claims.ClaimsIdentity> los objetos devueltos por la <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="5ffe9-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5ffe9-138">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5ffe9-138">Parent Elements</span></span>  
  
|<span data-ttu-id="5ffe9-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="5ffe9-139">Element</span></span>|<span data-ttu-id="5ffe9-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ffe9-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ffe9-141">\<add></span><span class="sxs-lookup"><span data-stu-id="5ffe9-141">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="5ffe9-142">Agrega el controlador de token de seguridad especificado a la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="5ffe9-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ffe9-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5ffe9-143">Remarks</span></span>  
 <span data-ttu-id="5ffe9-144">El `<samlSecurityTokenRequirement>` elemento representado por la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> en el modelo de objetos de clase y se usa para configurar el `SamlSecurityTokenRequirement` propiedad en un <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> o un <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="5ffe9-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ffe9-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ffe9-145">Example</span></span>  
  
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

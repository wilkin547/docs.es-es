---
description: 'Más información acerca de: <samlSecurityTokenRequirement>'
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: 21e584480aae6f620e0809be77e02789536db426
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786569"
---
# \<samlSecurityTokenRequirement>

<span data-ttu-id="07328-102">Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> clase, la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="07328-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="07328-103">Se representa mediante la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> clase.</span><span class="sxs-lookup"><span data-stu-id="07328-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="07328-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07328-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07328-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="07328-105">Attributes and Elements</span></span>  

 <span data-ttu-id="07328-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="07328-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07328-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="07328-107">Attributes</span></span>  
  
|<span data-ttu-id="07328-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="07328-108">Attribute</span></span>|<span data-ttu-id="07328-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="07328-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="07328-110">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="07328-110">mapToWindows</span></span>|<span data-ttu-id="07328-111">Especifica si el controlador de token debe asignar el token de validación a una cuenta de Windows mediante la notificaciones de UPN entrantes.</span><span class="sxs-lookup"><span data-stu-id="07328-111">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="07328-112">El valor predeterminado es "false".</span><span class="sxs-lookup"><span data-stu-id="07328-112">The default is "false".</span></span>|  
|<span data-ttu-id="07328-113">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="07328-113">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="07328-114"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>Valor que especifica el modo de revocación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="07328-114">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="07328-115">El valor predeterminado es "online".</span><span class="sxs-lookup"><span data-stu-id="07328-115">The default value is "Online".</span></span>|  
|<span data-ttu-id="07328-116">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="07328-116">issuerCertificateValidationMode</span></span>|<span data-ttu-id="07328-117"><xref:System.ServiceModel.Security.X509CertificateValidationMode>Valor que especifica el modo de validación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="07328-117">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="07328-118">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="07328-118">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="07328-119">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="07328-119">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="07328-120"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>Valor que especifica el almacén de certificados X. 509.</span><span class="sxs-lookup"><span data-stu-id="07328-120">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="07328-121">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="07328-121">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="07328-122">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="07328-122">issuerCertificateValidator</span></span>|<span data-ttu-id="07328-123">Un tipo personalizado que se deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator> .</span><span class="sxs-lookup"><span data-stu-id="07328-123">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="07328-124">Si el `issuerCertificateValidationMode` atributo es "Custom", se usa una instancia de este tipo para la validación del certificado del emisor.</span><span class="sxs-lookup"><span data-stu-id="07328-124">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07328-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="07328-125">Child Elements</span></span>  
  
|<span data-ttu-id="07328-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="07328-126">Element</span></span>|<span data-ttu-id="07328-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="07328-127">Description</span></span>|  
|-------------|-----------------|  
|[\<nameClaimType>](nameclaimtype.md)|<span data-ttu-id="07328-128">Establece el tipo de demanda que especifica la <xref:System.Security.Principal.IIdentity.Name%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="07328-128">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[\<roleClaimType>](roleclaimtype.md)|<span data-ttu-id="07328-129">Especifica el tipo de notificación que define las notificaciones de tipo de rol en la colección de <xref:System.Security.Claims.ClaimsIdentity> objetos devuelta por el <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="07328-129">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="07328-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="07328-130">Parent Elements</span></span>  
  
|<span data-ttu-id="07328-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="07328-131">Element</span></span>|<span data-ttu-id="07328-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="07328-132">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="07328-133">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="07328-133">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07328-134">Observaciones</span><span class="sxs-lookup"><span data-stu-id="07328-134">Remarks</span></span>  

 <span data-ttu-id="07328-135">La `<samlSecurityTokenRequirement>` clase representa el elemento <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> en el modelo de objetos y se usa para configurar la `SamlSecurityTokenRequirement` propiedad en <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> o <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> .</span><span class="sxs-lookup"><span data-stu-id="07328-135">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07328-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="07328-136">Example</span></span>  
  
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

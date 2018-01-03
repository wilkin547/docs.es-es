---
title: '&lt;x509SecurityTokenHandlerRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7cb9eb1e7e80837e8036a8241a3a6bd679ed5e11
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltx509securitytokenhandlerrequirementgt"></a><span data-ttu-id="b5dc9-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="b5dc9-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="b5dc9-103">Proporciona una configuración opcional para la <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="b5dc9-103">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="b5dc9-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="b5dc9-104">\<system.identityModel></span></span>  
<span data-ttu-id="b5dc9-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b5dc9-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b5dc9-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="b5dc9-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b5dc9-107">\<add></span><span class="sxs-lookup"><span data-stu-id="b5dc9-107">\<add></span></span>  
<span data-ttu-id="b5dc9-108">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="b5dc9-108">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5dc9-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5dc9-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5dc9-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b5dc9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b5dc9-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b5dc9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5dc9-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b5dc9-112">Attributes</span></span>  
  
|<span data-ttu-id="b5dc9-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="b5dc9-113">Attribute</span></span>|<span data-ttu-id="b5dc9-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5dc9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b5dc9-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="b5dc9-115">certificateValidationMode</span></span>|<span data-ttu-id="b5dc9-116">Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valor que especifica el modo de validación que se utilizará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="b5dc9-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="b5dc9-117">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="b5dc9-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="b5dc9-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="b5dc9-118">mapToWindows</span></span>|<span data-ttu-id="b5dc9-119">Especifica si el controlador de token debe asignar el token de validación a una cuenta de Windows mediante la notificación UPN entrante.</span><span class="sxs-lookup"><span data-stu-id="b5dc9-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="b5dc9-120">El valor predeterminado es "false".</span><span class="sxs-lookup"><span data-stu-id="b5dc9-120">The default is "false".</span></span>|  
|<span data-ttu-id="b5dc9-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="b5dc9-121">revocationMode</span></span>|<span data-ttu-id="b5dc9-122">Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valor que especifica el modo de revocación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="b5dc9-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="b5dc9-123">El valor predeterminado es "Online".</span><span class="sxs-lookup"><span data-stu-id="b5dc9-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="b5dc9-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="b5dc9-124">trustedStoreLocation</span></span>|<span data-ttu-id="b5dc9-125">Un <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valor que especifica el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="b5dc9-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="b5dc9-126">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="b5dc9-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="b5dc9-127">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="b5dc9-127">certificateValidator</span></span>|<span data-ttu-id="b5dc9-128">Un tipo personalizado que deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="b5dc9-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="b5dc9-129">Si el `certificateValidationMode` atributo es "Custom", se utiliza una instancia de este tipo de validación de certificados de emisor.</span><span class="sxs-lookup"><span data-stu-id="b5dc9-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5dc9-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b5dc9-130">Child Elements</span></span>  
 <span data-ttu-id="b5dc9-131">Ninguna</span><span class="sxs-lookup"><span data-stu-id="b5dc9-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b5dc9-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b5dc9-132">Parent Elements</span></span>  
  
|<span data-ttu-id="b5dc9-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="b5dc9-133">Element</span></span>|<span data-ttu-id="b5dc9-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5dc9-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5dc9-135">\<add></span><span class="sxs-lookup"><span data-stu-id="b5dc9-135">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="b5dc9-136">Agrega el controlador de token de seguridad especificado a la colección de controlador de token.</span><span class="sxs-lookup"><span data-stu-id="b5dc9-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b5dc9-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5dc9-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```

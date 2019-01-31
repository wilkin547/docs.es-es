---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 6e8267f170dbb26381564be7b66df5f617156885
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271955"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="53cbc-101">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="53cbc-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="53cbc-102">Proporciona una configuración opcional para la <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="53cbc-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="53cbc-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="53cbc-103">\<system.identityModel></span></span>  
<span data-ttu-id="53cbc-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="53cbc-104">\<identityConfiguration></span></span>  
<span data-ttu-id="53cbc-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="53cbc-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="53cbc-106">\<add></span><span class="sxs-lookup"><span data-stu-id="53cbc-106">\<add></span></span>  
<span data-ttu-id="53cbc-107">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="53cbc-107">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53cbc-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53cbc-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53cbc-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="53cbc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="53cbc-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="53cbc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53cbc-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="53cbc-111">Attributes</span></span>  
  
|<span data-ttu-id="53cbc-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="53cbc-112">Attribute</span></span>|<span data-ttu-id="53cbc-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="53cbc-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53cbc-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="53cbc-114">certificateValidationMode</span></span>|<span data-ttu-id="53cbc-115">Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valor que especifica el modo de validación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="53cbc-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="53cbc-116">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="53cbc-116">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="53cbc-117">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="53cbc-117">mapToWindows</span></span>|<span data-ttu-id="53cbc-118">Especifica si el controlador de token debe asignar el token de validación a una cuenta de Windows mediante el uso de la notificación UPN entrante.</span><span class="sxs-lookup"><span data-stu-id="53cbc-118">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="53cbc-119">El valor predeterminado es "false".</span><span class="sxs-lookup"><span data-stu-id="53cbc-119">The default is "false".</span></span>|  
|<span data-ttu-id="53cbc-120">revocationMode</span><span class="sxs-lookup"><span data-stu-id="53cbc-120">revocationMode</span></span>|<span data-ttu-id="53cbc-121">Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valor que especifica el modo de revocación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="53cbc-121">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="53cbc-122">El valor predeterminado es "Online".</span><span class="sxs-lookup"><span data-stu-id="53cbc-122">The default value is "Online".</span></span>|  
|<span data-ttu-id="53cbc-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="53cbc-123">trustedStoreLocation</span></span>|<span data-ttu-id="53cbc-124">Un <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valor que especifica el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="53cbc-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="53cbc-125">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="53cbc-125">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="53cbc-126">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="53cbc-126">certificateValidator</span></span>|<span data-ttu-id="53cbc-127">Un tipo personalizado que se deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="53cbc-127">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="53cbc-128">Si el `certificateValidationMode` el atributo es "Custom", se utiliza una instancia de este tipo de validación del certificado del emisor.</span><span class="sxs-lookup"><span data-stu-id="53cbc-128">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53cbc-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="53cbc-129">Child Elements</span></span>  
 <span data-ttu-id="53cbc-130">Ninguna</span><span class="sxs-lookup"><span data-stu-id="53cbc-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53cbc-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="53cbc-131">Parent Elements</span></span>  
  
|<span data-ttu-id="53cbc-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="53cbc-132">Element</span></span>|<span data-ttu-id="53cbc-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="53cbc-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53cbc-134">\<add></span><span class="sxs-lookup"><span data-stu-id="53cbc-134">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="53cbc-135">Agrega el controlador de token de seguridad especificado a la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="53cbc-135">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="53cbc-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53cbc-136">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```

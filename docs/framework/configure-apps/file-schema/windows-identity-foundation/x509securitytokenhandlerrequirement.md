---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 6e8267f170dbb26381564be7b66df5f617156885
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790447"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="fe89a-101">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="fe89a-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="fe89a-102">Proporciona una configuración opcional para la <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="fe89a-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="fe89a-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="fe89a-103">\<system.identityModel></span></span>  
<span data-ttu-id="fe89a-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="fe89a-104">\<identityConfiguration></span></span>  
<span data-ttu-id="fe89a-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="fe89a-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="fe89a-106">\<add></span><span class="sxs-lookup"><span data-stu-id="fe89a-106">\<add></span></span>  
<span data-ttu-id="fe89a-107">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="fe89a-107">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe89a-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe89a-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe89a-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fe89a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fe89a-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fe89a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe89a-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="fe89a-111">Attributes</span></span>  
  
|<span data-ttu-id="fe89a-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="fe89a-112">Attribute</span></span>|<span data-ttu-id="fe89a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe89a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fe89a-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="fe89a-114">certificateValidationMode</span></span>|<span data-ttu-id="fe89a-115">Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valor que especifica el modo de validación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="fe89a-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="fe89a-116">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="fe89a-116">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="fe89a-117">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="fe89a-117">mapToWindows</span></span>|<span data-ttu-id="fe89a-118">Especifica si el controlador de token debe asignar el token de validación a una cuenta de Windows mediante el uso de la notificación UPN entrante.</span><span class="sxs-lookup"><span data-stu-id="fe89a-118">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="fe89a-119">El valor predeterminado es "false".</span><span class="sxs-lookup"><span data-stu-id="fe89a-119">The default is "false".</span></span>|  
|<span data-ttu-id="fe89a-120">revocationMode</span><span class="sxs-lookup"><span data-stu-id="fe89a-120">revocationMode</span></span>|<span data-ttu-id="fe89a-121">Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valor que especifica el modo de revocación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="fe89a-121">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="fe89a-122">El valor predeterminado es "Online".</span><span class="sxs-lookup"><span data-stu-id="fe89a-122">The default value is "Online".</span></span>|  
|<span data-ttu-id="fe89a-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="fe89a-123">trustedStoreLocation</span></span>|<span data-ttu-id="fe89a-124">Un <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valor que especifica el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="fe89a-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="fe89a-125">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="fe89a-125">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="fe89a-126">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="fe89a-126">certificateValidator</span></span>|<span data-ttu-id="fe89a-127">Un tipo personalizado que se deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="fe89a-127">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="fe89a-128">Si el `certificateValidationMode` el atributo es "Custom", se utiliza una instancia de este tipo de validación del certificado del emisor.</span><span class="sxs-lookup"><span data-stu-id="fe89a-128">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe89a-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fe89a-129">Child Elements</span></span>  
 <span data-ttu-id="fe89a-130">Ninguna</span><span class="sxs-lookup"><span data-stu-id="fe89a-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fe89a-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fe89a-131">Parent Elements</span></span>  
  
|<span data-ttu-id="fe89a-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="fe89a-132">Element</span></span>|<span data-ttu-id="fe89a-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe89a-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fe89a-134">\<add></span><span class="sxs-lookup"><span data-stu-id="fe89a-134">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="fe89a-135">Agrega el controlador de token de seguridad especificado a la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="fe89a-135">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fe89a-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fe89a-136">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```

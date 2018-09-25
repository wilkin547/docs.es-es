---
title: '&lt;x509SecurityTokenHandlerRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 994677904cada71dbc7cce4b6ca0de1d4dc65014
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47085669"
---
# <a name="ltx509securitytokenhandlerrequirementgt"></a><span data-ttu-id="9fee3-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="9fee3-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="9fee3-103">Proporciona una configuración opcional para la <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="9fee3-103">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="9fee3-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="9fee3-104">\<system.identityModel></span></span>  
<span data-ttu-id="9fee3-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="9fee3-105">\<identityConfiguration></span></span>  
<span data-ttu-id="9fee3-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="9fee3-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="9fee3-107">\<add></span><span class="sxs-lookup"><span data-stu-id="9fee3-107">\<add></span></span>  
<span data-ttu-id="9fee3-108">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="9fee3-108">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fee3-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9fee3-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fee3-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9fee3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9fee3-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9fee3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fee3-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="9fee3-112">Attributes</span></span>  
  
|<span data-ttu-id="9fee3-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="9fee3-113">Attribute</span></span>|<span data-ttu-id="9fee3-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="9fee3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9fee3-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="9fee3-115">certificateValidationMode</span></span>|<span data-ttu-id="9fee3-116">Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valor que especifica el modo de validación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="9fee3-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="9fee3-117">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="9fee3-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="9fee3-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="9fee3-118">mapToWindows</span></span>|<span data-ttu-id="9fee3-119">Especifica si el controlador de token debe asignar el token de validación a una cuenta de Windows mediante el uso de la notificación UPN entrante.</span><span class="sxs-lookup"><span data-stu-id="9fee3-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="9fee3-120">El valor predeterminado es "false".</span><span class="sxs-lookup"><span data-stu-id="9fee3-120">The default is "false".</span></span>|  
|<span data-ttu-id="9fee3-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="9fee3-121">revocationMode</span></span>|<span data-ttu-id="9fee3-122">Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valor que especifica el modo de revocación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="9fee3-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="9fee3-123">El valor predeterminado es "Online".</span><span class="sxs-lookup"><span data-stu-id="9fee3-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="9fee3-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="9fee3-124">trustedStoreLocation</span></span>|<span data-ttu-id="9fee3-125">Un <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valor que especifica el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="9fee3-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="9fee3-126">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="9fee3-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="9fee3-127">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="9fee3-127">certificateValidator</span></span>|<span data-ttu-id="9fee3-128">Un tipo personalizado que se deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="9fee3-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="9fee3-129">Si el `certificateValidationMode` el atributo es "Custom", se utiliza una instancia de este tipo de validación del certificado del emisor.</span><span class="sxs-lookup"><span data-stu-id="9fee3-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9fee3-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9fee3-130">Child Elements</span></span>  
 <span data-ttu-id="9fee3-131">Ninguna</span><span class="sxs-lookup"><span data-stu-id="9fee3-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9fee3-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9fee3-132">Parent Elements</span></span>  
  
|<span data-ttu-id="9fee3-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="9fee3-133">Element</span></span>|<span data-ttu-id="9fee3-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="9fee3-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9fee3-135">\<add></span><span class="sxs-lookup"><span data-stu-id="9fee3-135">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="9fee3-136">Agrega el controlador de token de seguridad especificado a la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="9fee3-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9fee3-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9fee3-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```

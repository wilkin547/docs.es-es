---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 30ce69a35cfdd34e0dfea5c682347eb9187e04ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152455"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="083b6-101">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="083b6-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="083b6-102">Proporciona configuración opcional <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> para la clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="083b6-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="083b6-103">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="083b6-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="083b6-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="083b6-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="083b6-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="083b6-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="083b6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="083b6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="083b6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<añadir>**](add.md)</span><span class="sxs-lookup"><span data-stu-id="083b6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="083b6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**</span><span class="sxs-lookup"><span data-stu-id="083b6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="083b6-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="083b6-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="083b6-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="083b6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="083b6-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="083b6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="083b6-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="083b6-112">Attributes</span></span>  
  
|<span data-ttu-id="083b6-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="083b6-113">Attribute</span></span>|<span data-ttu-id="083b6-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="083b6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="083b6-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="083b6-115">certificateValidationMode</span></span>|<span data-ttu-id="083b6-116">Valor <xref:System.ServiceModel.Security.X509CertificateValidationMode> que especifica el modo de validación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="083b6-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="083b6-117">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="083b6-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="083b6-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="083b6-118">mapToWindows</span></span>|<span data-ttu-id="083b6-119">Especifica si el controlador de tokens debe asignar el token de validación a una cuenta de Windows mediante la notificación UPN entrante.</span><span class="sxs-lookup"><span data-stu-id="083b6-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="083b6-120">El valor predeterminado es "false".</span><span class="sxs-lookup"><span data-stu-id="083b6-120">The default is "false".</span></span>|  
|<span data-ttu-id="083b6-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="083b6-121">revocationMode</span></span>|<span data-ttu-id="083b6-122">Valor <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> que especifica el modo de revocación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="083b6-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="083b6-123">El valor predeterminado es "Online".</span><span class="sxs-lookup"><span data-stu-id="083b6-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="083b6-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="083b6-124">trustedStoreLocation</span></span>|<span data-ttu-id="083b6-125">Valor <xref:System.Security.Cryptography.X509Certificates.StoreLocation> que especifica el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="083b6-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="083b6-126">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="083b6-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="083b6-127">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="083b6-127">certificateValidator</span></span>|<span data-ttu-id="083b6-128">Un tipo personalizado que <xref:System.IdentityModel.Selectors.X509CertificateValidator>deriva de .</span><span class="sxs-lookup"><span data-stu-id="083b6-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="083b6-129">Si `certificateValidationMode` el atributo es "Custom", se utiliza una instancia de este tipo para la validación del certificado de emisor.</span><span class="sxs-lookup"><span data-stu-id="083b6-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="083b6-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="083b6-130">Child Elements</span></span>  
 <span data-ttu-id="083b6-131">None</span><span class="sxs-lookup"><span data-stu-id="083b6-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="083b6-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="083b6-132">Parent Elements</span></span>  
  
|<span data-ttu-id="083b6-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="083b6-133">Element</span></span>|<span data-ttu-id="083b6-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="083b6-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="083b6-135">\<añadir></span><span class="sxs-lookup"><span data-stu-id="083b6-135">\<add></span></span>](add.md)|<span data-ttu-id="083b6-136">Agrega el controlador de token de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="083b6-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="083b6-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="083b6-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```

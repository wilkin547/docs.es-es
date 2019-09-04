---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 76eeea635fd65486a1c16bea15a49018876dae99
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251687"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="5eea8-101">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="5eea8-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="5eea8-102">Proporciona una configuración opcional para <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> la clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="5eea8-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="5eea8-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5eea8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5eea8-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="5eea8-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="5eea8-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="5eea8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="5eea8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="5eea8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="5eea8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Agregar >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="5eea8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="5eea8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> x509SecurityTokenHandlerRequirement**</span><span class="sxs-lookup"><span data-stu-id="5eea8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eea8-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5eea8-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5eea8-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5eea8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5eea8-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5eea8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5eea8-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="5eea8-112">Attributes</span></span>  
  
|<span data-ttu-id="5eea8-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="5eea8-113">Attribute</span></span>|<span data-ttu-id="5eea8-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5eea8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5eea8-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="5eea8-115">certificateValidationMode</span></span>|<span data-ttu-id="5eea8-116"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Valor que especifica el modo de validación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="5eea8-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="5eea8-117">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="5eea8-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="5eea8-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="5eea8-118">mapToWindows</span></span>|<span data-ttu-id="5eea8-119">Especifica si el controlador de token debe asignar el token de validación a una cuenta de Windows mediante la notificaciones de UPN entrantes.</span><span class="sxs-lookup"><span data-stu-id="5eea8-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="5eea8-120">El valor predeterminado es "false".</span><span class="sxs-lookup"><span data-stu-id="5eea8-120">The default is "false".</span></span>|  
|<span data-ttu-id="5eea8-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="5eea8-121">revocationMode</span></span>|<span data-ttu-id="5eea8-122"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Valor que especifica el modo de revocación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="5eea8-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="5eea8-123">El valor predeterminado es "online".</span><span class="sxs-lookup"><span data-stu-id="5eea8-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="5eea8-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="5eea8-124">trustedStoreLocation</span></span>|<span data-ttu-id="5eea8-125"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valor que especifica el almacén de certificados X. 509.</span><span class="sxs-lookup"><span data-stu-id="5eea8-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="5eea8-126">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="5eea8-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="5eea8-127">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="5eea8-127">certificateValidator</span></span>|<span data-ttu-id="5eea8-128">Un tipo personalizado que se deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="5eea8-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="5eea8-129">Si el `certificateValidationMode` atributo es "Custom", se usa una instancia de este tipo para la validación del certificado del emisor.</span><span class="sxs-lookup"><span data-stu-id="5eea8-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5eea8-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5eea8-130">Child Elements</span></span>  
 <span data-ttu-id="5eea8-131">None</span><span class="sxs-lookup"><span data-stu-id="5eea8-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5eea8-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5eea8-132">Parent Elements</span></span>  
  
|<span data-ttu-id="5eea8-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="5eea8-133">Element</span></span>|<span data-ttu-id="5eea8-134">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5eea8-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5eea8-135">\<add></span><span class="sxs-lookup"><span data-stu-id="5eea8-135">\<add></span></span>](add.md)|<span data-ttu-id="5eea8-136">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="5eea8-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5eea8-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5eea8-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```

---
description: 'Más información acerca de: <x509SecurityTokenHandlerRequirement>'
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 21a05cfeee6365bd677a6f35e984cb64fa4dd078
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748978"
---
# \<x509SecurityTokenHandlerRequirement>

<span data-ttu-id="048a0-102">Proporciona una configuración opcional para la <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="048a0-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="048a0-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="048a0-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="048a0-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="048a0-104">Attributes and Elements</span></span>  

 <span data-ttu-id="048a0-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="048a0-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="048a0-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="048a0-106">Attributes</span></span>  
  
|<span data-ttu-id="048a0-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="048a0-107">Attribute</span></span>|<span data-ttu-id="048a0-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="048a0-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="048a0-109">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="048a0-109">certificateValidationMode</span></span>|<span data-ttu-id="048a0-110"><xref:System.ServiceModel.Security.X509CertificateValidationMode>Valor que especifica el modo de validación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="048a0-110">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="048a0-111">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="048a0-111">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="048a0-112">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="048a0-112">mapToWindows</span></span>|<span data-ttu-id="048a0-113">Especifica si el controlador de token debe asignar el token de validación a una cuenta de Windows mediante la notificaciones de UPN entrantes.</span><span class="sxs-lookup"><span data-stu-id="048a0-113">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="048a0-114">El valor predeterminado es "false".</span><span class="sxs-lookup"><span data-stu-id="048a0-114">The default is "false".</span></span>|  
|<span data-ttu-id="048a0-115">revocationMode</span><span class="sxs-lookup"><span data-stu-id="048a0-115">revocationMode</span></span>|<span data-ttu-id="048a0-116"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>Valor que especifica el modo de revocación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="048a0-116">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="048a0-117">El valor predeterminado es "online".</span><span class="sxs-lookup"><span data-stu-id="048a0-117">The default value is "Online".</span></span>|  
|<span data-ttu-id="048a0-118">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="048a0-118">trustedStoreLocation</span></span>|<span data-ttu-id="048a0-119"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>Valor que especifica el almacén de certificados X. 509.</span><span class="sxs-lookup"><span data-stu-id="048a0-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="048a0-120">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="048a0-120">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="048a0-121">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="048a0-121">certificateValidator</span></span>|<span data-ttu-id="048a0-122">Un tipo personalizado que se deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator> .</span><span class="sxs-lookup"><span data-stu-id="048a0-122">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="048a0-123">Si el `certificateValidationMode` atributo es "Custom", se usa una instancia de este tipo para la validación del certificado del emisor.</span><span class="sxs-lookup"><span data-stu-id="048a0-123">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="048a0-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="048a0-124">Child Elements</span></span>  

 <span data-ttu-id="048a0-125">None</span><span class="sxs-lookup"><span data-stu-id="048a0-125">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="048a0-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="048a0-126">Parent Elements</span></span>  
  
|<span data-ttu-id="048a0-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="048a0-127">Element</span></span>|<span data-ttu-id="048a0-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="048a0-128">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="048a0-129">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="048a0-129">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="048a0-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="048a0-130">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```

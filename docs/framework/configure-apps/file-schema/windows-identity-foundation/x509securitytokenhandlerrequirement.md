---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: a6a8185297e1345de9fa20c7d4d0dffbdcd8620f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185397"
---
# \<x509SecurityTokenHandlerRequirement>

<span data-ttu-id="ec342-101">Proporciona una configuración opcional para la <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="ec342-101">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="ec342-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec342-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec342-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ec342-103">Attributes and Elements</span></span>  

 <span data-ttu-id="ec342-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ec342-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec342-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="ec342-105">Attributes</span></span>  
  
|<span data-ttu-id="ec342-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="ec342-106">Attribute</span></span>|<span data-ttu-id="ec342-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec342-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ec342-108">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="ec342-108">certificateValidationMode</span></span>|<span data-ttu-id="ec342-109"><xref:System.ServiceModel.Security.X509CertificateValidationMode>Valor que especifica el modo de validación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="ec342-109">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ec342-110">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="ec342-110">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="ec342-111">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="ec342-111">mapToWindows</span></span>|<span data-ttu-id="ec342-112">Especifica si el controlador de token debe asignar el token de validación a una cuenta de Windows mediante la notificaciones de UPN entrantes.</span><span class="sxs-lookup"><span data-stu-id="ec342-112">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="ec342-113">El valor predeterminado es "false".</span><span class="sxs-lookup"><span data-stu-id="ec342-113">The default is "false".</span></span>|  
|<span data-ttu-id="ec342-114">revocationMode</span><span class="sxs-lookup"><span data-stu-id="ec342-114">revocationMode</span></span>|<span data-ttu-id="ec342-115"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>Valor que especifica el modo de revocación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="ec342-115">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ec342-116">El valor predeterminado es "online".</span><span class="sxs-lookup"><span data-stu-id="ec342-116">The default value is "Online".</span></span>|  
|<span data-ttu-id="ec342-117">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="ec342-117">trustedStoreLocation</span></span>|<span data-ttu-id="ec342-118"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>Valor que especifica el almacén de certificados X. 509.</span><span class="sxs-lookup"><span data-stu-id="ec342-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="ec342-119">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="ec342-119">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="ec342-120">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="ec342-120">certificateValidator</span></span>|<span data-ttu-id="ec342-121">Un tipo personalizado que se deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator> .</span><span class="sxs-lookup"><span data-stu-id="ec342-121">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="ec342-122">Si el `certificateValidationMode` atributo es "Custom", se usa una instancia de este tipo para la validación del certificado del emisor.</span><span class="sxs-lookup"><span data-stu-id="ec342-122">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec342-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ec342-123">Child Elements</span></span>  

 <span data-ttu-id="ec342-124">None</span><span class="sxs-lookup"><span data-stu-id="ec342-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec342-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ec342-125">Parent Elements</span></span>  
  
|<span data-ttu-id="ec342-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="ec342-126">Element</span></span>|<span data-ttu-id="ec342-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec342-127">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="ec342-128">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="ec342-128">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ec342-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec342-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```

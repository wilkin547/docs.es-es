---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: c2d1a5d36cb5616ef06eedc093dd70a68a164a81
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252131"
---
# <a name="certificatevalidation"></a><span data-ttu-id="bdfd2-101">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="bdfd2-101">\<certificateValidation></span></span>
<span data-ttu-id="bdfd2-102">Controla la configuración que usan los controladores de token para validar certificados.</span><span class="sxs-lookup"><span data-stu-id="bdfd2-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="bdfd2-103">Esta configuración se invalida si un controlador concreto se configura con su propio validador.</span><span class="sxs-lookup"><span data-stu-id="bdfd2-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
<span data-ttu-id="bdfd2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bdfd2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bdfd2-105">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="bdfd2-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="bdfd2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="bdfd2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="bdfd2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> certificateValidation**</span><span class="sxs-lookup"><span data-stu-id="bdfd2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdfd2-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bdfd2-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bdfd2-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bdfd2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bdfd2-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bdfd2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdfd2-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="bdfd2-111">Attributes</span></span>  
  
|<span data-ttu-id="bdfd2-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="bdfd2-112">Attribute</span></span>|<span data-ttu-id="bdfd2-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bdfd2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bdfd2-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="bdfd2-114">certificateValidationMode</span></span>|<span data-ttu-id="bdfd2-115"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Valor que especifica el modo de validación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="bdfd2-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="bdfd2-116">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="bdfd2-116">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="bdfd2-117">Para especificar un validador personalizado, establezca este atributo en "Custom" y especifique el validador mediante el elemento [ \<> de certificateValidator](certificatevalidator.md) .</span><span class="sxs-lookup"><span data-stu-id="bdfd2-117">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="bdfd2-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="bdfd2-118">Optional.</span></span>|  
|<span data-ttu-id="bdfd2-119">revocationMode</span><span class="sxs-lookup"><span data-stu-id="bdfd2-119">revocationMode</span></span>|<span data-ttu-id="bdfd2-120"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Valor que especifica el modo de revocación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="bdfd2-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="bdfd2-121">El valor predeterminado es "online".</span><span class="sxs-lookup"><span data-stu-id="bdfd2-121">The default value is "Online".</span></span> <span data-ttu-id="bdfd2-122">Opcional.</span><span class="sxs-lookup"><span data-stu-id="bdfd2-122">Optional.</span></span>|  
|<span data-ttu-id="bdfd2-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="bdfd2-123">trustedStoreLocation</span></span>|<span data-ttu-id="bdfd2-124"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valor que especifica el almacén de certificados X. 509.</span><span class="sxs-lookup"><span data-stu-id="bdfd2-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="bdfd2-125">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="bdfd2-125">The default value is "LocalMachine".</span></span> <span data-ttu-id="bdfd2-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="bdfd2-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bdfd2-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bdfd2-127">Child Elements</span></span>  
  
|<span data-ttu-id="bdfd2-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="bdfd2-128">Element</span></span>|<span data-ttu-id="bdfd2-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bdfd2-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bdfd2-130">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="bdfd2-130">\<certificateValidator></span></span>](certificatevalidator.md)|<span data-ttu-id="bdfd2-131">Especifica un tipo personalizado para la validación del certificado.</span><span class="sxs-lookup"><span data-stu-id="bdfd2-131">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="bdfd2-132">Este tipo solo se utiliza si el `certificateValidationMode` atributo [ \<del elemento > certificateValidation](certificatevalidation.md) se establece en "Custom".</span><span class="sxs-lookup"><span data-stu-id="bdfd2-132">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bdfd2-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bdfd2-133">Parent Elements</span></span>  
  
|<span data-ttu-id="bdfd2-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="bdfd2-134">Element</span></span>|<span data-ttu-id="bdfd2-135">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bdfd2-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bdfd2-136">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="bdfd2-136">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="bdfd2-137">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="bdfd2-137">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="bdfd2-138">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="bdfd2-138">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="bdfd2-139">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bdfd2-139">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdfd2-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bdfd2-140">Remarks</span></span>  
 <span data-ttu-id="bdfd2-141">Un `<certificateValidation>` elemento se puede especificar en el nivel de servicio bajo `<identityConfiguration>` el elemento o en el nivel de colección de controladores de `<securityTokenHandlerConfiguration>` tokens de seguridad bajo el elemento.</span><span class="sxs-lookup"><span data-stu-id="bdfd2-141">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="bdfd2-142">La configuración de una colección de controladores de tokens invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="bdfd2-142">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="bdfd2-143">Algunos controladores de token permiten especificar la configuración de validación de certificados en la configuración.</span><span class="sxs-lookup"><span data-stu-id="bdfd2-143">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="bdfd2-144">La configuración de los controladores de token individuales invalida los especificados tanto en el nivel de servicio como en la colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bdfd2-144">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdfd2-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bdfd2-145">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```

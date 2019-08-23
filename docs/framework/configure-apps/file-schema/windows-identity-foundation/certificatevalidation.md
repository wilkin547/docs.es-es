---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 8185153eb02c5794b0f6ac02a6837806f2073c07
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941921"
---
# <a name="certificatevalidation"></a><span data-ttu-id="c7e6e-101">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="c7e6e-101">\<certificateValidation></span></span>
<span data-ttu-id="c7e6e-102">Controla la configuración que usan los controladores de token para validar certificados.</span><span class="sxs-lookup"><span data-stu-id="c7e6e-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="c7e6e-103">Esta configuración se invalida si un controlador concreto se configura con su propio validador.</span><span class="sxs-lookup"><span data-stu-id="c7e6e-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="c7e6e-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="c7e6e-104">\<system.identityModel></span></span>  
<span data-ttu-id="c7e6e-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c7e6e-105">\<identityConfiguration></span></span>  
<span data-ttu-id="c7e6e-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="c7e6e-106">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7e6e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7e6e-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7e6e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c7e6e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c7e6e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c7e6e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7e6e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="c7e6e-110">Attributes</span></span>  
  
|<span data-ttu-id="c7e6e-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="c7e6e-111">Attribute</span></span>|<span data-ttu-id="c7e6e-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c7e6e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c7e6e-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="c7e6e-113">certificateValidationMode</span></span>|<span data-ttu-id="c7e6e-114"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Valor que especifica el modo de validación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="c7e6e-114">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="c7e6e-115">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="c7e6e-115">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="c7e6e-116">Para especificar un validador personalizado, establezca este atributo en "Custom" y especifique el validador mediante el elemento [ \<> de certificateValidator](certificatevalidator.md) .</span><span class="sxs-lookup"><span data-stu-id="c7e6e-116">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="c7e6e-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c7e6e-117">Optional.</span></span>|  
|<span data-ttu-id="c7e6e-118">revocationMode</span><span class="sxs-lookup"><span data-stu-id="c7e6e-118">revocationMode</span></span>|<span data-ttu-id="c7e6e-119"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Valor que especifica el modo de revocación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="c7e6e-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="c7e6e-120">El valor predeterminado es "online".</span><span class="sxs-lookup"><span data-stu-id="c7e6e-120">The default value is "Online".</span></span> <span data-ttu-id="c7e6e-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c7e6e-121">Optional.</span></span>|  
|<span data-ttu-id="c7e6e-122">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="c7e6e-122">trustedStoreLocation</span></span>|<span data-ttu-id="c7e6e-123"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valor que especifica el almacén de certificados X. 509.</span><span class="sxs-lookup"><span data-stu-id="c7e6e-123">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="c7e6e-124">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="c7e6e-124">The default value is "LocalMachine".</span></span> <span data-ttu-id="c7e6e-125">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c7e6e-125">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7e6e-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c7e6e-126">Child Elements</span></span>  
  
|<span data-ttu-id="c7e6e-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="c7e6e-127">Element</span></span>|<span data-ttu-id="c7e6e-128">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c7e6e-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7e6e-129">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="c7e6e-129">\<certificateValidator></span></span>](certificatevalidator.md)|<span data-ttu-id="c7e6e-130">Especifica un tipo personalizado para la validación del certificado.</span><span class="sxs-lookup"><span data-stu-id="c7e6e-130">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="c7e6e-131">Este tipo solo se utiliza si el `certificateValidationMode` atributo [ \<del elemento > certificateValidation](certificatevalidation.md) se establece en "Custom".</span><span class="sxs-lookup"><span data-stu-id="c7e6e-131">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c7e6e-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c7e6e-132">Parent Elements</span></span>  
  
|<span data-ttu-id="c7e6e-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="c7e6e-133">Element</span></span>|<span data-ttu-id="c7e6e-134">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c7e6e-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7e6e-135">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c7e6e-135">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="c7e6e-136">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="c7e6e-136">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="c7e6e-137">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="c7e6e-137">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="c7e6e-138">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c7e6e-138">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7e6e-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c7e6e-139">Remarks</span></span>  
 <span data-ttu-id="c7e6e-140">Un `<certificateValidation>` elemento se puede especificar en el nivel de servicio bajo `<identityConfiguration>` el elemento o en el nivel de colección de controladores de `<securityTokenHandlerConfiguration>` tokens de seguridad bajo el elemento.</span><span class="sxs-lookup"><span data-stu-id="c7e6e-140">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="c7e6e-141">La configuración de una colección de controladores de tokens invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="c7e6e-141">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="c7e6e-142">Algunos controladores de token permiten especificar la configuración de validación de certificados en la configuración.</span><span class="sxs-lookup"><span data-stu-id="c7e6e-142">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="c7e6e-143">La configuración de los controladores de token individuales invalida los especificados tanto en el nivel de servicio como en la colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c7e6e-143">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7e6e-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7e6e-144">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```

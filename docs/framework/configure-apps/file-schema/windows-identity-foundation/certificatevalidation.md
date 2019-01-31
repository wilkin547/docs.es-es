---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 7b8823d792e3f15846a9483d670994be4b368980
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273902"
---
# <a name="certificatevalidation"></a><span data-ttu-id="6f072-101">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="6f072-101">\<certificateValidation></span></span>
<span data-ttu-id="6f072-102">Controla la configuración que los controladores de token que se usan para validar los certificados.</span><span class="sxs-lookup"><span data-stu-id="6f072-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="6f072-103">Esta configuración se invalida si un controlador específico se configura con su propio validador.</span><span class="sxs-lookup"><span data-stu-id="6f072-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="6f072-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="6f072-104">\<system.identityModel></span></span>  
<span data-ttu-id="6f072-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6f072-105">\<identityConfiguration></span></span>  
<span data-ttu-id="6f072-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="6f072-106">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f072-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f072-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f072-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6f072-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6f072-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6f072-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f072-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6f072-110">Attributes</span></span>  
  
|<span data-ttu-id="6f072-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="6f072-111">Attribute</span></span>|<span data-ttu-id="6f072-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f072-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6f072-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="6f072-113">certificateValidationMode</span></span>|<span data-ttu-id="6f072-114">Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valor que especifica el modo de validación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="6f072-114">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="6f072-115">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="6f072-115">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="6f072-116">Para especificar un validador personalizado, establezca este atributo en "Custom" y especifique el validador con la [ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="6f072-116">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) element.</span></span> <span data-ttu-id="6f072-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6f072-117">Optional.</span></span>|  
|<span data-ttu-id="6f072-118">revocationMode</span><span class="sxs-lookup"><span data-stu-id="6f072-118">revocationMode</span></span>|<span data-ttu-id="6f072-119">Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valor que especifica el modo de revocación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="6f072-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="6f072-120">El valor predeterminado es "Online".</span><span class="sxs-lookup"><span data-stu-id="6f072-120">The default value is "Online".</span></span> <span data-ttu-id="6f072-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6f072-121">Optional.</span></span>|  
|<span data-ttu-id="6f072-122">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="6f072-122">trustedStoreLocation</span></span>|<span data-ttu-id="6f072-123">Un <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valor que especifica el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="6f072-123">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="6f072-124">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="6f072-124">The default value is "LocalMachine".</span></span> <span data-ttu-id="6f072-125">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6f072-125">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f072-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6f072-126">Child Elements</span></span>  
  
|<span data-ttu-id="6f072-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="6f072-127">Element</span></span>|<span data-ttu-id="6f072-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f072-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f072-129">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="6f072-129">\<certificateValidator></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|<span data-ttu-id="6f072-130">Especifica un tipo personalizado para la validación del certificado.</span><span class="sxs-lookup"><span data-stu-id="6f072-130">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="6f072-131">Este tipo se usa únicamente si el `certificateValidationMode` atributo de la [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) está establecida en "Custom".</span><span class="sxs-lookup"><span data-stu-id="6f072-131">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6f072-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6f072-132">Parent Elements</span></span>  
  
|<span data-ttu-id="6f072-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="6f072-133">Element</span></span>|<span data-ttu-id="6f072-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f072-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f072-135">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6f072-135">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="6f072-136">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="6f072-136">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="6f072-137">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="6f072-137">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="6f072-138">Proporciona la configuración para una colección de seguridad controladores de token.</span><span class="sxs-lookup"><span data-stu-id="6f072-138">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f072-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6f072-139">Remarks</span></span>  
 <span data-ttu-id="6f072-140">Un `<certificateValidation>` elemento puede especificarse en el nivel de servicio bajo la `<identityConfiguration>` elemento o en el nivel de colección de controladores de token de seguridad bajo el `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="6f072-140">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="6f072-141">La configuración en una colección de controladores de token invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="6f072-141">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="6f072-142">Algunos controladores de token le permiten especificar la configuración de validación de certificados en la configuración.</span><span class="sxs-lookup"><span data-stu-id="6f072-142">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="6f072-143">La configuración en los controladores de token individuales invalida los especificados en el nivel de servicio y en la colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6f072-143">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f072-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f072-144">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```

---
title: '&lt;certificateValidation&gt;'
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 29881be43f02d275ad135efd97dc8b25a7409beb
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47235460"
---
# <a name="ltcertificatevalidationgt"></a><span data-ttu-id="dceee-102">&lt;certificateValidation&gt;</span><span class="sxs-lookup"><span data-stu-id="dceee-102">&lt;certificateValidation&gt;</span></span>
<span data-ttu-id="dceee-103">Controla la configuración que los controladores de token que se usan para validar los certificados.</span><span class="sxs-lookup"><span data-stu-id="dceee-103">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="dceee-104">Esta configuración se invalida si un controlador específico se configura con su propio validador.</span><span class="sxs-lookup"><span data-stu-id="dceee-104">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="dceee-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="dceee-105">\<system.identityModel></span></span>  
<span data-ttu-id="dceee-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="dceee-106">\<identityConfiguration></span></span>  
<span data-ttu-id="dceee-107">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="dceee-107">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dceee-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dceee-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dceee-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dceee-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dceee-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dceee-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dceee-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="dceee-111">Attributes</span></span>  
  
|<span data-ttu-id="dceee-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="dceee-112">Attribute</span></span>|<span data-ttu-id="dceee-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="dceee-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dceee-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="dceee-114">certificateValidationMode</span></span>|<span data-ttu-id="dceee-115">Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valor que especifica el modo de validación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="dceee-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="dceee-116">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="dceee-116">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="dceee-117">Para especificar un validador personalizado, establezca este atributo en "Custom" y especifique el validador con la [ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="dceee-117">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) element.</span></span> <span data-ttu-id="dceee-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="dceee-118">Optional.</span></span>|  
|<span data-ttu-id="dceee-119">revocationMode</span><span class="sxs-lookup"><span data-stu-id="dceee-119">revocationMode</span></span>|<span data-ttu-id="dceee-120">Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valor que especifica el modo de revocación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="dceee-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="dceee-121">El valor predeterminado es "Online".</span><span class="sxs-lookup"><span data-stu-id="dceee-121">The default value is "Online".</span></span> <span data-ttu-id="dceee-122">Opcional.</span><span class="sxs-lookup"><span data-stu-id="dceee-122">Optional.</span></span>|  
|<span data-ttu-id="dceee-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="dceee-123">trustedStoreLocation</span></span>|<span data-ttu-id="dceee-124">Un <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valor que especifica el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="dceee-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="dceee-125">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="dceee-125">The default value is "LocalMachine".</span></span> <span data-ttu-id="dceee-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="dceee-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dceee-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dceee-127">Child Elements</span></span>  
  
|<span data-ttu-id="dceee-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="dceee-128">Element</span></span>|<span data-ttu-id="dceee-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="dceee-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dceee-130">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="dceee-130">\<certificateValidator></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|<span data-ttu-id="dceee-131">Especifica un tipo personalizado para la validación del certificado.</span><span class="sxs-lookup"><span data-stu-id="dceee-131">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="dceee-132">Este tipo se usa únicamente si el `certificateValidationMode` atributo de la [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) está establecida en "Custom".</span><span class="sxs-lookup"><span data-stu-id="dceee-132">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dceee-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dceee-133">Parent Elements</span></span>  
  
|<span data-ttu-id="dceee-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="dceee-134">Element</span></span>|<span data-ttu-id="dceee-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="dceee-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dceee-136">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="dceee-136">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="dceee-137">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="dceee-137">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="dceee-138">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="dceee-138">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="dceee-139">Proporciona la configuración para una colección de seguridad controladores de token.</span><span class="sxs-lookup"><span data-stu-id="dceee-139">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dceee-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dceee-140">Remarks</span></span>  
 <span data-ttu-id="dceee-141">Un `<certificateValidation>` elemento puede especificarse en el nivel de servicio bajo la `<identityConfiguration>` elemento o en el nivel de colección de controladores de token de seguridad bajo el `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="dceee-141">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="dceee-142">La configuración en una colección de controladores de token invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="dceee-142">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="dceee-143">Algunos controladores de token le permiten especificar la configuración de validación de certificados en la configuración.</span><span class="sxs-lookup"><span data-stu-id="dceee-143">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="dceee-144">La configuración en los controladores de token individuales invalida los especificados en el nivel de servicio y en la colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="dceee-144">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dceee-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dceee-145">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```

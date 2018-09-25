---
title: '&lt;certificateValidation&gt;'
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 29881be43f02d275ad135efd97dc8b25a7409beb
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47074793"
---
# <a name="ltcertificatevalidationgt"></a><span data-ttu-id="04ac1-102">&lt;certificateValidation&gt;</span><span class="sxs-lookup"><span data-stu-id="04ac1-102">&lt;certificateValidation&gt;</span></span>
<span data-ttu-id="04ac1-103">Controla la configuración que los controladores de token que se usan para validar los certificados.</span><span class="sxs-lookup"><span data-stu-id="04ac1-103">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="04ac1-104">Esta configuración se invalida si un controlador específico se configura con su propio validador.</span><span class="sxs-lookup"><span data-stu-id="04ac1-104">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="04ac1-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="04ac1-105">\<system.identityModel></span></span>  
<span data-ttu-id="04ac1-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="04ac1-106">\<identityConfiguration></span></span>  
<span data-ttu-id="04ac1-107">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="04ac1-107">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04ac1-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04ac1-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04ac1-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="04ac1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="04ac1-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="04ac1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04ac1-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="04ac1-111">Attributes</span></span>  
  
|<span data-ttu-id="04ac1-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="04ac1-112">Attribute</span></span>|<span data-ttu-id="04ac1-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="04ac1-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="04ac1-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="04ac1-114">certificateValidationMode</span></span>|<span data-ttu-id="04ac1-115">Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valor que especifica el modo de validación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="04ac1-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="04ac1-116">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="04ac1-116">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="04ac1-117">Para especificar un validador personalizado, establezca este atributo en "Custom" y especifique el validador con la [ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="04ac1-117">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) element.</span></span> <span data-ttu-id="04ac1-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="04ac1-118">Optional.</span></span>|  
|<span data-ttu-id="04ac1-119">revocationMode</span><span class="sxs-lookup"><span data-stu-id="04ac1-119">revocationMode</span></span>|<span data-ttu-id="04ac1-120">Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valor que especifica el modo de revocación que se usará para el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="04ac1-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="04ac1-121">El valor predeterminado es "Online".</span><span class="sxs-lookup"><span data-stu-id="04ac1-121">The default value is "Online".</span></span> <span data-ttu-id="04ac1-122">Opcional.</span><span class="sxs-lookup"><span data-stu-id="04ac1-122">Optional.</span></span>|  
|<span data-ttu-id="04ac1-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="04ac1-123">trustedStoreLocation</span></span>|<span data-ttu-id="04ac1-124">Un <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valor que especifica el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="04ac1-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="04ac1-125">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="04ac1-125">The default value is "LocalMachine".</span></span> <span data-ttu-id="04ac1-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="04ac1-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04ac1-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="04ac1-127">Child Elements</span></span>  
  
|<span data-ttu-id="04ac1-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="04ac1-128">Element</span></span>|<span data-ttu-id="04ac1-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="04ac1-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04ac1-130">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="04ac1-130">\<certificateValidator></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|<span data-ttu-id="04ac1-131">Especifica un tipo personalizado para la validación del certificado.</span><span class="sxs-lookup"><span data-stu-id="04ac1-131">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="04ac1-132">Este tipo se usa únicamente si el `certificateValidationMode` atributo de la [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) está establecida en "Custom".</span><span class="sxs-lookup"><span data-stu-id="04ac1-132">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="04ac1-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="04ac1-133">Parent Elements</span></span>  
  
|<span data-ttu-id="04ac1-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="04ac1-134">Element</span></span>|<span data-ttu-id="04ac1-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="04ac1-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04ac1-136">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="04ac1-136">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="04ac1-137">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="04ac1-137">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="04ac1-138">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="04ac1-138">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="04ac1-139">Proporciona la configuración para una colección de seguridad controladores de token.</span><span class="sxs-lookup"><span data-stu-id="04ac1-139">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04ac1-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04ac1-140">Remarks</span></span>  
 <span data-ttu-id="04ac1-141">Un `<certificateValidation>` elemento puede especificarse en el nivel de servicio bajo la `<identityConfiguration>` elemento o en el nivel de colección de controladores de token de seguridad bajo el `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="04ac1-141">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="04ac1-142">La configuración en una colección de controladores de token invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="04ac1-142">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="04ac1-143">Algunos controladores de token le permiten especificar la configuración de validación de certificados en la configuración.</span><span class="sxs-lookup"><span data-stu-id="04ac1-143">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="04ac1-144">La configuración en los controladores de token individuales invalida los especificados en el nivel de servicio y en la colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="04ac1-144">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04ac1-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04ac1-145">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```

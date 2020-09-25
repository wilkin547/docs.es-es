---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 583fef7eb364c39890b3f9304770b383c1ea6d2a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183512"
---
# \<certificateValidation>

<span data-ttu-id="828d8-101">Controla la configuración que usan los controladores de token para validar certificados.</span><span class="sxs-lookup"><span data-stu-id="828d8-101">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="828d8-102">Esta configuración se invalida si un controlador concreto se configura con su propio validador.</span><span class="sxs-lookup"><span data-stu-id="828d8-102">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**  
  
## <a name="syntax"></a><span data-ttu-id="828d8-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="828d8-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="828d8-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="828d8-104">Attributes and Elements</span></span>  

 <span data-ttu-id="828d8-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="828d8-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="828d8-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="828d8-106">Attributes</span></span>  
  
|<span data-ttu-id="828d8-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="828d8-107">Attribute</span></span>|<span data-ttu-id="828d8-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="828d8-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="828d8-109">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="828d8-109">certificateValidationMode</span></span>|<span data-ttu-id="828d8-110"><xref:System.ServiceModel.Security.X509CertificateValidationMode>Valor que especifica el modo de validación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="828d8-110">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="828d8-111">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="828d8-111">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="828d8-112">Para especificar un validador personalizado, establezca este atributo en "Custom" y especifique el validador mediante el [\<certificateValidator>](certificatevalidator.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="828d8-112">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="828d8-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="828d8-113">Optional.</span></span>|  
|<span data-ttu-id="828d8-114">revocationMode</span><span class="sxs-lookup"><span data-stu-id="828d8-114">revocationMode</span></span>|<span data-ttu-id="828d8-115"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>Valor que especifica el modo de revocación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="828d8-115">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="828d8-116">El valor predeterminado es "online".</span><span class="sxs-lookup"><span data-stu-id="828d8-116">The default value is "Online".</span></span> <span data-ttu-id="828d8-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="828d8-117">Optional.</span></span>|  
|<span data-ttu-id="828d8-118">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="828d8-118">trustedStoreLocation</span></span>|<span data-ttu-id="828d8-119"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>Valor que especifica el almacén de certificados X. 509.</span><span class="sxs-lookup"><span data-stu-id="828d8-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="828d8-120">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="828d8-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="828d8-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="828d8-121">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="828d8-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="828d8-122">Child Elements</span></span>  
  
|<span data-ttu-id="828d8-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="828d8-123">Element</span></span>|<span data-ttu-id="828d8-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="828d8-124">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateValidator>](certificatevalidator.md)|<span data-ttu-id="828d8-125">Especifica un tipo personalizado para la validación del certificado.</span><span class="sxs-lookup"><span data-stu-id="828d8-125">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="828d8-126">Este tipo solo se utiliza si el `certificateValidationMode` atributo del [\<certificateValidation>](certificatevalidation.md) elemento se establece en "Custom".</span><span class="sxs-lookup"><span data-stu-id="828d8-126">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="828d8-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="828d8-127">Parent Elements</span></span>  
  
|<span data-ttu-id="828d8-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="828d8-128">Element</span></span>|<span data-ttu-id="828d8-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="828d8-129">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="828d8-130">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="828d8-130">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="828d8-131">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="828d8-131">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="828d8-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="828d8-132">Remarks</span></span>  

 <span data-ttu-id="828d8-133">Un `<certificateValidation>` elemento se puede especificar en el nivel de servicio bajo el `<identityConfiguration>` elemento o en el nivel de colección de controladores de tokens de seguridad bajo el `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="828d8-133">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="828d8-134">La configuración de una colección de controladores de tokens invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="828d8-134">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="828d8-135">Algunos controladores de token permiten especificar la configuración de validación de certificados en la configuración.</span><span class="sxs-lookup"><span data-stu-id="828d8-135">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="828d8-136">La configuración de los controladores de token individuales invalida los especificados tanto en el nivel de servicio como en la colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="828d8-136">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="828d8-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="828d8-137">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```

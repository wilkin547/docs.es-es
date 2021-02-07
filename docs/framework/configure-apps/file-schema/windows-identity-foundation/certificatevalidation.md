---
description: 'Más información acerca de: <certificateValidation>'
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: a12e46487b4fb2ac8071ba1cf9bc5c6057ded060
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740072"
---
# \<certificateValidation>

<span data-ttu-id="80809-102">Controla la configuración que usan los controladores de token para validar certificados.</span><span class="sxs-lookup"><span data-stu-id="80809-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="80809-103">Esta configuración se invalida si un controlador concreto se configura con su propio validador.</span><span class="sxs-lookup"><span data-stu-id="80809-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**  
  
## <a name="syntax"></a><span data-ttu-id="80809-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80809-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80809-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="80809-105">Attributes and Elements</span></span>  

 <span data-ttu-id="80809-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="80809-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80809-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="80809-107">Attributes</span></span>  
  
|<span data-ttu-id="80809-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="80809-108">Attribute</span></span>|<span data-ttu-id="80809-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="80809-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="80809-110">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="80809-110">certificateValidationMode</span></span>|<span data-ttu-id="80809-111"><xref:System.ServiceModel.Security.X509CertificateValidationMode>Valor que especifica el modo de validación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="80809-111">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="80809-112">El valor predeterminado es "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="80809-112">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="80809-113">Para especificar un validador personalizado, establezca este atributo en "Custom" y especifique el validador mediante el [\<certificateValidator>](certificatevalidator.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="80809-113">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="80809-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="80809-114">Optional.</span></span>|  
|<span data-ttu-id="80809-115">revocationMode</span><span class="sxs-lookup"><span data-stu-id="80809-115">revocationMode</span></span>|<span data-ttu-id="80809-116"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>Valor que especifica el modo de revocación que se va a usar para el certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="80809-116">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="80809-117">El valor predeterminado es "online".</span><span class="sxs-lookup"><span data-stu-id="80809-117">The default value is "Online".</span></span> <span data-ttu-id="80809-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="80809-118">Optional.</span></span>|  
|<span data-ttu-id="80809-119">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="80809-119">trustedStoreLocation</span></span>|<span data-ttu-id="80809-120"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>Valor que especifica el almacén de certificados X. 509.</span><span class="sxs-lookup"><span data-stu-id="80809-120">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="80809-121">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="80809-121">The default value is "LocalMachine".</span></span> <span data-ttu-id="80809-122">Opcional.</span><span class="sxs-lookup"><span data-stu-id="80809-122">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80809-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="80809-123">Child Elements</span></span>  
  
|<span data-ttu-id="80809-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="80809-124">Element</span></span>|<span data-ttu-id="80809-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="80809-125">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateValidator>](certificatevalidator.md)|<span data-ttu-id="80809-126">Especifica un tipo personalizado para la validación del certificado.</span><span class="sxs-lookup"><span data-stu-id="80809-126">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="80809-127">Este tipo solo se utiliza si el `certificateValidationMode` atributo del [\<certificateValidation>](certificatevalidation.md) elemento se establece en "Custom".</span><span class="sxs-lookup"><span data-stu-id="80809-127">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80809-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="80809-128">Parent Elements</span></span>  
  
|<span data-ttu-id="80809-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="80809-129">Element</span></span>|<span data-ttu-id="80809-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="80809-130">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="80809-131">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="80809-131">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="80809-132">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="80809-132">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80809-133">Observaciones</span><span class="sxs-lookup"><span data-stu-id="80809-133">Remarks</span></span>  

 <span data-ttu-id="80809-134">Un `<certificateValidation>` elemento se puede especificar en el nivel de servicio bajo el `<identityConfiguration>` elemento o en el nivel de colección de controladores de tokens de seguridad bajo el `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="80809-134">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="80809-135">La configuración de una colección de controladores de tokens invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="80809-135">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="80809-136">Algunos controladores de token permiten especificar la configuración de validación de certificados en la configuración.</span><span class="sxs-lookup"><span data-stu-id="80809-136">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="80809-137">La configuración de los controladores de token individuales invalida los especificados tanto en el nivel de servicio como en la colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="80809-137">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80809-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="80809-138">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```

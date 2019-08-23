---
title: Esquema de configuración de Windows Identity Foundation
ms.date: 03/30/2017
ms.assetid: 4d4f6d76-49a5-4bad-b345-097b2e2844e9
author: BrucePerlerMS
ms.openlocfilehash: fddff8428da7efad2823f068e89c6f621283183f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942678"
---
# <a name="windows-identity-foundation-configuration-schema"></a><span data-ttu-id="36108-102">Esquema de configuración de Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="36108-102">Windows Identity Foundation Configuration Schema</span></span>
<span data-ttu-id="36108-103">En los temas de esta sección se proporciona información sobre el esquema de configuración de Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="36108-103">The topics in this section provide information about the Windows Identity Foundation (WIF) configuration schema.</span></span> <span data-ttu-id="36108-104">También puede configurar una aplicación para usar WIF a través de las clases expuestas por el marco.</span><span class="sxs-lookup"><span data-stu-id="36108-104">You can also configure an application to use WIF through classes exposed by the framework.</span></span> <span data-ttu-id="36108-105">Estas clases se indican en las secciones que tratan sobre los elementos correspondientes del esquema.</span><span class="sxs-lookup"><span data-stu-id="36108-105">These classes are noted in the sections that treat relevant elements in the schema.</span></span> <span data-ttu-id="36108-106">A continuación se muestra la estructura básica de etiquetas XML expuesta por el esquema de configuración de WIF.</span><span class="sxs-lookup"><span data-stu-id="36108-106">The following shows the basic XML tag structure exposed by the WIF configuration schema.</span></span> <span data-ttu-id="36108-107">Los atributos se omiten.</span><span class="sxs-lookup"><span data-stu-id="36108-107">Attributes are omitted.</span></span> <span data-ttu-id="36108-108">Los comentarios resaltados indican los componentes principales del esquema.</span><span class="sxs-lookup"><span data-stu-id="36108-108">Highlighted comments indicate major components of the schema.</span></span>  
  
```xml  
<system.identityModel>  
    <!-- Service Configuration -->  
    <identityConfiguration>  
        <caches>  
            <sessionSecurityTokenCache />  
            <tokenReplayCache />  
        </caches>  
  
        <certificateValidation>  
            <certificateValidator />   
        </certificateValidation>  
  
        <claimsAuthenticationManager />  
  
        <claimsAuthorizationManager>  
            <optionalConfigurationElement>  
        </claimsAuthorizationManager>  
  
        <claimTypeRequired>  
            <claimType />   
        </claimTypeRequired>  
  
        <tokenReplayDetection />  
  
        <!-- Security Token Handler Collection Configuration -->  
        <securityTokenHandlers>  
            <add>  
                <!-- Can take an optional configuration element which can be one of  
                     the following or a custom element -->  
                <samlSecurityTokenHandlerRequirement>  
                    <nameClaimType>  
                    <roleClaimType>   
                </samlSecurityTokenHandlerRequirement>  
  
                <sessionSecurityTokenHandlerRequirement />  
                <x509SecurityTokenHandlerRequirement />  
                <userNameSecurityTokenHandlerRequirement />  
            </add>  
            <clear />  
            <remove />  
            <securityTokenHandlerConfiguration>  
                <audienceUris>  
                    <add>  
                    <clear>  
                    <remove>  
                </audienceUris>  
  
                <caches>  
                    <sessionSecurityTokenCache />  
                    <tokenReplayCache />  
                </caches>  
  
                <certificateValidation>  
                    <certificateValidator>   
                </certificateValidation>  
  
                <issuerNameRegistry>  
                    <!-- Can take an optional configuration element which can be   
                         the <trustedIssuers> element to configure a configuration-based  
                         issuer name registry or can be a custom element -->  
                    <trustedIssuers>  
                        <add>  
                        <clear>  
                        <remove>  
                    </trustedIssuers>  
                </issuerNameRegistry>  
  
                <issuerTokenResolver />  
                <serviceTokenResolver />  
                <tokenReplayDetection />  
            </securityTokenHandlerConfiguration>  
        </securityTokenHandlers>  
    </identityConfiguration>  
</system.identityModel>  
  
<system.identityModel.services>  
    <!-- Federation Authentication Configuration -->  
    <federatedAuthentication>  
        <cookieHandler>  
            <chunkedCookieHandler />  
            <customCookieHandler />  
        </cookieHandler>  
  
        <serviceCertificate>  
            <certificateReference>  
        </serviceCertificate>  
  
        <wsFederation />  
    </federatedAuthentication>  
</system.identityModel.services>  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="36108-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="36108-109">In This Section</span></span>  
 <span data-ttu-id="36108-110">En [\<system.identityModel>](system-identitymodel.md) se proporciona la configuración necesaria para habilitar opciones de WIF en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="36108-110">[\<system.identityModel>](system-identitymodel.md) Provides configuration for enabling WIF options in applications.</span></span>  
  
 <span data-ttu-id="36108-111">En [\<system.identityModel.services>](system-identitymodel-services.md) se proporciona la configuración necesaria para la federación pasiva mediante WIF.</span><span class="sxs-lookup"><span data-stu-id="36108-111">[\<system.identityModel.services>](system-identitymodel-services.md) Provides configuration for passive federation using WIF.</span></span> <span data-ttu-id="36108-112">Configura el módulo de autenticación de sesión (SAM) y el módulo de autenticación federada (WSFAM).</span><span class="sxs-lookup"><span data-stu-id="36108-112">Configures the Session Authentication Module (SAM) and the Federated Authentication Module (WSFAM).</span></span>

---
title: Esquema de configuración de Windows Identity Foundation
ms.date: 03/30/2017
ms.assetid: 4d4f6d76-49a5-4bad-b345-097b2e2844e9
author: BrucePerlerMS
ms.openlocfilehash: 9c8009b4d95e5aa2c3d9bb8a8958040127a9e628
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791674"
---
# <a name="windows-identity-foundation-configuration-schema"></a><span data-ttu-id="2ae26-102">Esquema de configuración de Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="2ae26-102">Windows Identity Foundation Configuration Schema</span></span>
<span data-ttu-id="2ae26-103">En los temas de esta sección se proporciona información sobre el esquema de configuración de Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="2ae26-103">The topics in this section provide information about the Windows Identity Foundation (WIF) configuration schema.</span></span> <span data-ttu-id="2ae26-104">También puede configurar una aplicación para usar WIF a través de las clases expuestas por el marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2ae26-104">You can also configure an application to use WIF through classes exposed by the framework.</span></span> <span data-ttu-id="2ae26-105">Estas clases se indican en las secciones que tratan sobre los elementos correspondientes del esquema.</span><span class="sxs-lookup"><span data-stu-id="2ae26-105">These classes are noted in the sections that treat relevant elements in the schema.</span></span> <span data-ttu-id="2ae26-106">A continuación se muestra la estructura básica de etiquetas XML expuesta por el esquema de configuración de WIF.</span><span class="sxs-lookup"><span data-stu-id="2ae26-106">The following shows the basic XML tag structure exposed by the WIF configuration schema.</span></span> <span data-ttu-id="2ae26-107">Los atributos se omiten.</span><span class="sxs-lookup"><span data-stu-id="2ae26-107">Attributes are omitted.</span></span> <span data-ttu-id="2ae26-108">Los comentarios resaltados indican los componentes principales del esquema.</span><span class="sxs-lookup"><span data-stu-id="2ae26-108">Highlighted comments indicate major components of the schema.</span></span>  
  
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
  
## <a name="in-this-section"></a><span data-ttu-id="2ae26-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2ae26-109">In This Section</span></span>  
 <span data-ttu-id="2ae26-110">En [\<system.identityModel>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) se proporciona la configuración necesaria para habilitar opciones de WIF en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="2ae26-110">[\<system.identityModel>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) Provides configuration for enabling WIF options in applications.</span></span>  
  
 <span data-ttu-id="2ae26-111">En [\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) se proporciona la configuración necesaria para la federación pasiva mediante WIF.</span><span class="sxs-lookup"><span data-stu-id="2ae26-111">[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) Provides configuration for passive federation using WIF.</span></span> <span data-ttu-id="2ae26-112">Configura el módulo de autenticación de sesión (SAM) y el módulo de autenticación federada (WSFAM).</span><span class="sxs-lookup"><span data-stu-id="2ae26-112">Configures the Session Authentication Module (SAM) and the Federated Authentication Module (WSFAM).</span></span>

---
title: Esquema de configuración de Windows Identity Foundation
ms.date: 03/30/2017
ms.assetid: 4d4f6d76-49a5-4bad-b345-097b2e2844e9
author: BrucePerlerMS
ms.openlocfilehash: c081e582f4c509843c04c292ecf13b2bff2fef06
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47173140"
---
# <a name="windows-identity-foundation-configuration-schema"></a><span data-ttu-id="d3041-102">Esquema de configuración de Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="d3041-102">Windows Identity Foundation Configuration Schema</span></span>
<span data-ttu-id="d3041-103">En los temas de esta sección se proporciona información sobre el esquema de configuración de Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="d3041-103">The topics in this section provide information about the Windows Identity Foundation (WIF) configuration schema.</span></span> <span data-ttu-id="d3041-104">También puede configurar una aplicación para usar WIF a través de clases que expone el marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d3041-104">You can also configure an application to use WIF through classes exposed by the framework,.</span></span> <span data-ttu-id="d3041-105">Estas clases se indican en las secciones que tratan sobre los elementos correspondientes del esquema.</span><span class="sxs-lookup"><span data-stu-id="d3041-105">These classes are noted in the sections that treat relevant elements in the schema.</span></span> <span data-ttu-id="d3041-106">A continuación se muestra la estructura básica de etiquetas XML expuesta por el esquema de configuración de WIF.</span><span class="sxs-lookup"><span data-stu-id="d3041-106">The following shows the basic XML tag structure exposed by the WIF configuration schema.</span></span> <span data-ttu-id="d3041-107">Los atributos se omiten.</span><span class="sxs-lookup"><span data-stu-id="d3041-107">Attributes are omitted.</span></span> <span data-ttu-id="d3041-108">Los comentarios resaltados indican los componentes principales del esquema.</span><span class="sxs-lookup"><span data-stu-id="d3041-108">Highlighted comments indicate major components of the schema.</span></span>  
  
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
  
## <a name="in-this-section"></a><span data-ttu-id="d3041-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d3041-109">In This Section</span></span>  
 <span data-ttu-id="d3041-110">En [\<system.identityModel>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) se proporciona la configuración necesaria para habilitar opciones de WIF en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d3041-110">[\<system.identityModel>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) Provides configuration for enabling WIF options in applications.</span></span>  
  
 <span data-ttu-id="d3041-111">En [\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) se proporciona la configuración necesaria para la federación pasiva mediante WIF.</span><span class="sxs-lookup"><span data-stu-id="d3041-111">[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) Provides configuration for passive federation using WIF.</span></span> <span data-ttu-id="d3041-112">Configura el módulo de autenticación de sesión (SAM) y el módulo de autenticación federada (WSFAM).</span><span class="sxs-lookup"><span data-stu-id="d3041-112">Configures the Session Authentication Module (SAM) and the Federated Authentication Module (WSFAM).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d3041-113">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="d3041-113">Related Sections</span></span>  
 <span data-ttu-id="d3041-114">En [Configuration, Administration, And Management](https://msdn.microsoft.com/library/1e03c389-de2c-4096-aaff-86b087e1bea0) (Configuración, administración y dirección) se describe cómo configurar y administrar aplicaciones y servicios de WIF.</span><span class="sxs-lookup"><span data-stu-id="d3041-114">[Configuration, Administration, And Management](https://msdn.microsoft.com/library/1e03c389-de2c-4096-aaff-86b087e1bea0) Describes how to configure and manage WIF applications and services.</span></span>

---
title: '&lt;Memorias caché&gt;'
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: a91a389e53354e4f5b26e1510fc2f025300d65cc
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47192685"
---
# <a name="ltcachesgt"></a><span data-ttu-id="76f05-102">&lt;Memorias caché&gt;</span><span class="sxs-lookup"><span data-stu-id="76f05-102">&lt;caches&gt;</span></span>
<span data-ttu-id="76f05-103">Registra las memorias caché utilizadas para la detección de reproducción de tokens y los tokens de sesión.</span><span class="sxs-lookup"><span data-stu-id="76f05-103">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="76f05-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="76f05-104">\<system.identityModel></span></span>  
<span data-ttu-id="76f05-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="76f05-105">\<identityConfiguration></span></span>  
<span data-ttu-id="76f05-106">\<las memorias caché ></span><span class="sxs-lookup"><span data-stu-id="76f05-106">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76f05-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76f05-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76f05-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="76f05-108">Attributes and Elements</span></span>  
 <span data-ttu-id="76f05-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="76f05-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76f05-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="76f05-110">Attributes</span></span>  
 <span data-ttu-id="76f05-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="76f05-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="76f05-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="76f05-112">Child Elements</span></span>  
  
|<span data-ttu-id="76f05-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="76f05-113">Element</span></span>|<span data-ttu-id="76f05-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="76f05-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76f05-115">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="76f05-115">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="76f05-116">Registra una memoria caché de tokens de sesión con un servicio o una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="76f05-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="76f05-117">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="76f05-117">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="76f05-118">Registra una caché de reproducción de tokens con un servicio o una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="76f05-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="76f05-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="76f05-119">Parent Elements</span></span>  
  
|<span data-ttu-id="76f05-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="76f05-120">Element</span></span>|<span data-ttu-id="76f05-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="76f05-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76f05-122">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="76f05-122">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="76f05-123">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="76f05-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="76f05-124">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="76f05-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="76f05-125">Proporciona la configuración para una colección de seguridad controladores de token.</span><span class="sxs-lookup"><span data-stu-id="76f05-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76f05-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="76f05-126">Remarks</span></span>  
 <span data-ttu-id="76f05-127">Un `<caches>` elemento puede especificarse en el nivel de servicio bajo la `<identityConfiguration>` elemento o en el nivel de colección de controladores de token de seguridad bajo el `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="76f05-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="76f05-128">La configuración en una colección de controladores de token invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="76f05-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="76f05-129">El `<caches>` elemento representado por la <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> clase.</span><span class="sxs-lookup"><span data-stu-id="76f05-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="76f05-130">Memorias caché configuradas se representan mediante el <xref:System.IdentityModel.Configuration.IdentityModelCaches> clase.</span><span class="sxs-lookup"><span data-stu-id="76f05-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76f05-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76f05-131">Example</span></span>  
 <span data-ttu-id="76f05-132">El siguiente XML muestra la configuración de una caché personalizada para almacenar los tokens de seguridad de sesión (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="76f05-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="76f05-133">La configuración se toma de la `ClaimsAwareWebFarm` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="76f05-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```

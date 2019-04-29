---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: b1d04280ef993297102d446ba5a7db54e8404dd8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750792"
---
# <a name="caches"></a><span data-ttu-id="047b6-101">\<caches></span><span class="sxs-lookup"><span data-stu-id="047b6-101">\<caches></span></span>
<span data-ttu-id="047b6-102">Registra las memorias caché utilizadas para la detección de reproducción de tokens y los tokens de sesión.</span><span class="sxs-lookup"><span data-stu-id="047b6-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="047b6-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="047b6-103">\<system.identityModel></span></span>  
<span data-ttu-id="047b6-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="047b6-104">\<identityConfiguration></span></span>  
<span data-ttu-id="047b6-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="047b6-105">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="047b6-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="047b6-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="047b6-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="047b6-107">Attributes and Elements</span></span>  
 <span data-ttu-id="047b6-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="047b6-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="047b6-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="047b6-109">Attributes</span></span>  
 <span data-ttu-id="047b6-110">Ninguna</span><span class="sxs-lookup"><span data-stu-id="047b6-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="047b6-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="047b6-111">Child Elements</span></span>  
  
|<span data-ttu-id="047b6-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="047b6-112">Element</span></span>|<span data-ttu-id="047b6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="047b6-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="047b6-114">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="047b6-114">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="047b6-115">Registra una memoria caché de tokens de sesión con un servicio o una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="047b6-115">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="047b6-116">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="047b6-116">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="047b6-117">Registra una caché de reproducción de tokens con un servicio o una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="047b6-117">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="047b6-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="047b6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="047b6-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="047b6-119">Element</span></span>|<span data-ttu-id="047b6-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="047b6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="047b6-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="047b6-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="047b6-122">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="047b6-122">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="047b6-123">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="047b6-123">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="047b6-124">Proporciona la configuración para una colección de seguridad controladores de token.</span><span class="sxs-lookup"><span data-stu-id="047b6-124">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="047b6-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="047b6-125">Remarks</span></span>  
 <span data-ttu-id="047b6-126">Un `<caches>` elemento puede especificarse en el nivel de servicio bajo la `<identityConfiguration>` elemento o en el nivel de colección de controladores de token de seguridad bajo el `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="047b6-126">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="047b6-127">La configuración en una colección de controladores de token invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="047b6-127">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="047b6-128">El `<caches>` elemento representado por la <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> clase.</span><span class="sxs-lookup"><span data-stu-id="047b6-128">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="047b6-129">Memorias caché configuradas se representan mediante el <xref:System.IdentityModel.Configuration.IdentityModelCaches> clase.</span><span class="sxs-lookup"><span data-stu-id="047b6-129">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="047b6-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="047b6-130">Example</span></span>  
 <span data-ttu-id="047b6-131">El siguiente XML muestra la configuración de una caché personalizada para almacenar los tokens de seguridad de sesión (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="047b6-131">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="047b6-132">La configuración se toma de la `ClaimsAwareWebFarm` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="047b6-132">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```

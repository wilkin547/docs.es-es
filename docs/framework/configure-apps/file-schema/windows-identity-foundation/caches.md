---
title: "&lt;almacena en memoria caché&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: b9dfa7b2f0952f3f9e224ad51fd4d9c0c263ce04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltcachesgt"></a><span data-ttu-id="a364d-102">&lt;almacena en memoria caché&gt;</span><span class="sxs-lookup"><span data-stu-id="a364d-102">&lt;caches&gt;</span></span>
<span data-ttu-id="a364d-103">Registra las memorias caché que se utiliza para la detección de reproducción de tokens y símbolos de sesión.</span><span class="sxs-lookup"><span data-stu-id="a364d-103">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="a364d-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="a364d-104">\<system.identityModel></span></span>  
<span data-ttu-id="a364d-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a364d-105">\<identityConfiguration></span></span>  
<span data-ttu-id="a364d-106">\<almacena en memoria caché ></span><span class="sxs-lookup"><span data-stu-id="a364d-106">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a364d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a364d-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a364d-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a364d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a364d-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a364d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a364d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a364d-110">Attributes</span></span>  
 <span data-ttu-id="a364d-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="a364d-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a364d-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a364d-112">Child Elements</span></span>  
  
|<span data-ttu-id="a364d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="a364d-113">Element</span></span>|<span data-ttu-id="a364d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a364d-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a364d-115">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="a364d-115">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="a364d-116">Registra una memoria caché de símbolos de sesión con un servicio o una colección de controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a364d-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="a364d-117">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="a364d-117">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="a364d-118">Registra una caché de respuesta de token con un servicio o una colección de controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a364d-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a364d-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a364d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a364d-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="a364d-120">Element</span></span>|<span data-ttu-id="a364d-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="a364d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a364d-122">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a364d-122">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="a364d-123">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="a364d-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="a364d-124">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a364d-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="a364d-125">Proporciona la configuración para una colección de seguridad controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="a364d-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a364d-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a364d-126">Remarks</span></span>  
 <span data-ttu-id="a364d-127">A `<caches>` elemento puede especificarse en el nivel de servicio en la `<identityConfiguration>` elemento o en el nivel de colección de controlador de token de seguridad en el `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="a364d-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="a364d-128">La configuración en una colección de controlador de token invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="a364d-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="a364d-129">El `<caches>` elemento representado por la <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> clase.</span><span class="sxs-lookup"><span data-stu-id="a364d-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="a364d-130">Las memorias caché configuradas se representan mediante la <xref:System.IdentityModel.Configuration.IdentityModelCaches> clase.</span><span class="sxs-lookup"><span data-stu-id="a364d-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a364d-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a364d-131">Example</span></span>  
 <span data-ttu-id="a364d-132">El siguiente código XML muestra la configuración de una caché personalizado para almacenar los tokens de seguridad de sesión (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="a364d-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="a364d-133">La configuración se toma de la `ClaimsAwareWebFarm` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a364d-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```

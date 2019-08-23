---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 5ad75ae18772d6e7c724f2cbf40c1e3083d5c345
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941964"
---
# <a name="caches"></a><span data-ttu-id="85f31-101">\<caches></span><span class="sxs-lookup"><span data-stu-id="85f31-101">\<caches></span></span>
<span data-ttu-id="85f31-102">Registra las cachés utilizadas para los tokens de sesión y la detección de reproducción de tokens.</span><span class="sxs-lookup"><span data-stu-id="85f31-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="85f31-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="85f31-103">\<system.identityModel></span></span>  
<span data-ttu-id="85f31-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="85f31-104">\<identityConfiguration></span></span>  
<span data-ttu-id="85f31-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="85f31-105">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85f31-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85f31-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85f31-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="85f31-107">Attributes and Elements</span></span>  
 <span data-ttu-id="85f31-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="85f31-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85f31-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="85f31-109">Attributes</span></span>  
 <span data-ttu-id="85f31-110">None</span><span class="sxs-lookup"><span data-stu-id="85f31-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="85f31-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="85f31-111">Child Elements</span></span>  
  
|<span data-ttu-id="85f31-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="85f31-112">Element</span></span>|<span data-ttu-id="85f31-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="85f31-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85f31-114">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="85f31-114">\<sessionSecurityTokenCache></span></span>](sessionsecuritytokencache.md)|<span data-ttu-id="85f31-115">Registra una memoria caché para los tokens de sesión con un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="85f31-115">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="85f31-116">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="85f31-116">\<tokenReplayCache></span></span>](tokenreplaycache.md)|<span data-ttu-id="85f31-117">Registra una memoria caché de reproducción de tokens con un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="85f31-117">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="85f31-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="85f31-118">Parent Elements</span></span>  
  
|<span data-ttu-id="85f31-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="85f31-119">Element</span></span>|<span data-ttu-id="85f31-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="85f31-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85f31-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="85f31-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="85f31-122">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="85f31-122">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="85f31-123">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="85f31-123">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="85f31-124">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="85f31-124">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85f31-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="85f31-125">Remarks</span></span>  
 <span data-ttu-id="85f31-126">Un `<caches>` elemento se puede especificar en el nivel de servicio bajo `<identityConfiguration>` el elemento o en el nivel de colección de controladores de `<securityTokenHandlerConfiguration>` tokens de seguridad bajo el elemento.</span><span class="sxs-lookup"><span data-stu-id="85f31-126">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="85f31-127">La configuración de una colección de controladores de tokens invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="85f31-127">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="85f31-128">El elemento se representa mediante la <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> clase. `<caches>`</span><span class="sxs-lookup"><span data-stu-id="85f31-128">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="85f31-129">La <xref:System.IdentityModel.Configuration.IdentityModelCaches> clase representa las memorias caché configuradas.</span><span class="sxs-lookup"><span data-stu-id="85f31-129">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85f31-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="85f31-130">Example</span></span>  
 <span data-ttu-id="85f31-131">El siguiente XML muestra la configuración de una caché personalizada para contener los tokens de seguridad<xref:System.IdentityModel.Tokens.SessionSecurityToken>de la sesión ().</span><span class="sxs-lookup"><span data-stu-id="85f31-131">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="85f31-132">La configuración se toma `ClaimsAwareWebFarm` del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="85f31-132">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
